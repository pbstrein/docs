
---
title: "ReportDefinition"
block_external_search_index: true
---

Manages Cost and Usage Report Definitions.

> *NOTE:* The AWS Cost and Usage Report service is only available in `us-east-1` currently.

> *NOTE:* If AWS Organizations is enabled, only the master account can use this resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleCurReportDefinition = new aws.cur.ReportDefinition("example_cur_report_definition", {
    additionalArtifacts: [
        "REDSHIFT",
        "QUICKSIGHT",
    ],
    additionalSchemaElements: ["RESOURCES"],
    compression: "GZIP",
    format: "textORcsv",
    reportName: "example-cur-report-definition",
    s3Bucket: "example-bucket-name",
    s3Region: "us-east-1",
    timeUnit: "HOURLY",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/cur_report_definition.html.markdown.



## Create a ReportDefinition Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cur/#ReportDefinition">ReportDefinition</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cur/#ReportDefinitionArgs">ReportDefinitionArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">ReportDefinition</span><span class="p">(resource_name, opts=None, </span>additional_artifacts=None<span class="p">, </span>additional_schema_elements=None<span class="p">, </span>compression=None<span class="p">, </span>format=None<span class="p">, </span>report_name=None<span class="p">, </span>s3_bucket=None<span class="p">, </span>s3_prefix=None<span class="p">, </span>s3_region=None<span class="p">, </span>time_unit=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewReportDefinition<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cur?tab=doc#ReportDefinitionArgs">ReportDefinitionArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cur?tab=doc#ReportDefinition">ReportDefinition</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cur.ReportDefinition.html">ReportDefinition</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cur.ReportDefinitionArgs.html">ReportDefinitionArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Additional<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of additional artifacts. Valid values are: REDSHIFT, QUICKSIGHT.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Additional<wbr>Schema<wbr>Elements<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of schema elements. Valid values are: RESOURCES.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Compression<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Compression format for report. Valid values are: GZIP, ZIP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Format<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Format for report. Valid values are: textORcsv.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Report<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique name for the report. Must start with a number/letter and is case sensitive. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Report path prefix. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">S3Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Region of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Time<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The frequency on which report data are measured and displayed.  Valid values are: HOURLY, DAILY.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Additional<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of additional artifacts. Valid values are: REDSHIFT, QUICKSIGHT.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Additional<wbr>Schema<wbr>Elements<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of schema elements. Valid values are: RESOURCES.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Compression<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Compression format for report. Valid values are: GZIP, ZIP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Format<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Format for report. Valid values are: textORcsv.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Report<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique name for the report. Must start with a number/letter and is case sensitive. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Report path prefix. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">S3Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Region of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Time<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The frequency on which report data are measured and displayed.  Valid values are: HOURLY, DAILY.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">additional<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of additional artifacts. Valid values are: REDSHIFT, QUICKSIGHT.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">additional<wbr>Schema<wbr>Elements<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of schema elements. Valid values are: RESOURCES.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">compression<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Compression format for report. Valid values are: GZIP, ZIP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">format<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Format for report. Valid values are: textORcsv.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">report<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique name for the report. Must start with a number/letter and is case sensitive. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">s3Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Report path prefix. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">s3Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Region of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">time<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The frequency on which report data are measured and displayed.  Valid values are: HOURLY, DAILY.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">additional_<wbr>artifacts<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of additional artifacts. Valid values are: REDSHIFT, QUICKSIGHT.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">additional_<wbr>schema_<wbr>elements<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of schema elements. Valid values are: RESOURCES.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">compression<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Compression format for report. Valid values are: GZIP, ZIP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">format<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Format for report. Valid values are: textORcsv.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">report_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Unique name for the report. Must start with a number/letter and is case sensitive. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">s3_<wbr>bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Report path prefix. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">s3_<wbr>region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Region of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">time_<wbr>unit<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The frequency on which report data are measured and displayed.  Valid values are: HOURLY, DAILY.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## ReportDefinition Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Additional<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of additional artifacts. Valid values are: REDSHIFT, QUICKSIGHT.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Additional<wbr>Schema<wbr>Elements<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of schema elements. Valid values are: RESOURCES.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Compression<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Compression format for report. Valid values are: GZIP, ZIP.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Format<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Format for report. Valid values are: textORcsv.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Report<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique name for the report. Must start with a number/letter and is case sensitive. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Report path prefix. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Region of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Time<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The frequency on which report data are measured and displayed.  Valid values are: HOURLY, DAILY.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Additional<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of additional artifacts. Valid values are: REDSHIFT, QUICKSIGHT.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Additional<wbr>Schema<wbr>Elements<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of schema elements. Valid values are: RESOURCES.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Compression<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Compression format for report. Valid values are: GZIP, ZIP.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Format<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Format for report. Valid values are: textORcsv.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Report<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique name for the report. Must start with a number/letter and is case sensitive. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Report path prefix. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Region of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Time<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The frequency on which report data are measured and displayed.  Valid values are: HOURLY, DAILY.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">additional<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of additional artifacts. Valid values are: REDSHIFT, QUICKSIGHT.
{{% /md %}}</dd>

    <dt class="property-"
            title="">additional<wbr>Schema<wbr>Elements<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of schema elements. Valid values are: RESOURCES.
{{% /md %}}</dd>

    <dt class="property-"
            title="">compression<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Compression format for report. Valid values are: GZIP, ZIP.
{{% /md %}}</dd>

    <dt class="property-"
            title="">format<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Format for report. Valid values are: textORcsv.
{{% /md %}}</dd>

    <dt class="property-"
            title="">report<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique name for the report. Must start with a number/letter and is case sensitive. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Report path prefix. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Region of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-"
            title="">time<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The frequency on which report data are measured and displayed.  Valid values are: HOURLY, DAILY.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">additional_<wbr>artifacts<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of additional artifacts. Valid values are: REDSHIFT, QUICKSIGHT.
{{% /md %}}</dd>

    <dt class="property-"
            title="">additional_<wbr>schema_<wbr>elements<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of schema elements. Valid values are: RESOURCES.
{{% /md %}}</dd>

    <dt class="property-"
            title="">compression<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Compression format for report. Valid values are: GZIP, ZIP.
{{% /md %}}</dd>

    <dt class="property-"
            title="">format<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Format for report. Valid values are: textORcsv.
{{% /md %}}</dd>

    <dt class="property-"
            title="">report_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Unique name for the report. Must start with a number/letter and is case sensitive. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3_<wbr>bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Report path prefix. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3_<wbr>region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Region of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-"
            title="">time_<wbr>unit<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The frequency on which report data are measured and displayed.  Valid values are: HOURLY, DAILY.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing ReportDefinition Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cur/#ReportDefinitionState">ReportDefinitionState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cur/#ReportDefinition">ReportDefinition</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>additional_artifacts=None<span class="p">, </span>additional_schema_elements=None<span class="p">, </span>compression=None<span class="p">, </span>format=None<span class="p">, </span>report_name=None<span class="p">, </span>s3_bucket=None<span class="p">, </span>s3_prefix=None<span class="p">, </span>s3_region=None<span class="p">, </span>time_unit=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetReportDefinition<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cur?tab=doc#ReportDefinitionState">ReportDefinitionState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cur?tab=doc#ReportDefinition">ReportDefinition</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cur.ReportDefinition.html">ReportDefinition</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cur.ReportDefinitionState.html">ReportDefinitionState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing ReportDefinition resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Additional<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of additional artifacts. Valid values are: REDSHIFT, QUICKSIGHT.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Additional<wbr>Schema<wbr>Elements<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of schema elements. Valid values are: RESOURCES.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compression<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Compression format for report. Valid values are: GZIP, ZIP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Format for report. Valid values are: textORcsv.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Report<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Unique name for the report. Must start with a number/letter and is case sensitive. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Report path prefix. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Region of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Time<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The frequency on which report data are measured and displayed.  Valid values are: HOURLY, DAILY.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Additional<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of additional artifacts. Valid values are: REDSHIFT, QUICKSIGHT.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Additional<wbr>Schema<wbr>Elements<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of schema elements. Valid values are: RESOURCES.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compression<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Compression format for report. Valid values are: GZIP, ZIP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Format<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Format for report. Valid values are: textORcsv.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Report<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Unique name for the report. Must start with a number/letter and is case sensitive. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Report path prefix. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Region<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Region of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Time<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The frequency on which report data are measured and displayed.  Valid values are: HOURLY, DAILY.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">additional<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of additional artifacts. Valid values are: REDSHIFT, QUICKSIGHT.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">additional<wbr>Schema<wbr>Elements<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of schema elements. Valid values are: RESOURCES.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compression<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Compression format for report. Valid values are: GZIP, ZIP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Format for report. Valid values are: textORcsv.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">report<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Unique name for the report. Must start with a number/letter and is case sensitive. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Report path prefix. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Region of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">time<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The frequency on which report data are measured and displayed.  Valid values are: HOURLY, DAILY.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">additional_<wbr>artifacts<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of additional artifacts. Valid values are: REDSHIFT, QUICKSIGHT.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">additional_<wbr>schema_<wbr>elements<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of schema elements. Valid values are: RESOURCES.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compression<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Compression format for report. Valid values are: GZIP, ZIP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">format<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Format for report. Valid values are: textORcsv.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">report_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Unique name for the report. Must start with a number/letter and is case sensitive. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Report path prefix. Limited to 256 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Region of the existing S3 bucket to hold generated reports.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">time_<wbr>unit<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The frequency on which report data are measured and displayed.  Valid values are: HOURLY, DAILY.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







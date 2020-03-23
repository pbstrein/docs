
---
title: "AnalyticsApplication"
block_external_search_index: true
---

Provides a Kinesis Analytics Application resource. Kinesis Analytics is a managed service that
allows processing and analyzing streaming data using standard SQL.

For more details, see the [Amazon Kinesis Analytics Documentation][1].

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const testStream = new aws.kinesis.Stream("test_stream", {
    shardCount: 1,
});
const testApplication = new aws.kinesis.AnalyticsApplication("test_application", {
    inputs: {
        kinesisStream: {
            resourceArn: testStream.arn,
            roleArn: aws_iam_role_test.arn,
        },
        namePrefix: "test_prefix",
        parallelism: {
            count: 1,
        },
        schema: {
            recordColumns: [{
                mapping: "$.test",
                name: "test",
                sqlType: "VARCHAR(8)",
            }],
            recordEncoding: "UTF-8",
            recordFormat: {
                mappingParameters: {
                    json: {
                        recordRowPath: "$",
                    },
                },
            },
        },
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/kinesis_analytics_application.html.markdown.



## Create a AnalyticsApplication Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/kinesis/#AnalyticsApplication">AnalyticsApplication</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/kinesis/#AnalyticsApplicationArgs">AnalyticsApplicationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">AnalyticsApplication</span><span class="p">(resource_name, opts=None, </span>cloudwatch_logging_options=None<span class="p">, </span>code=None<span class="p">, </span>description=None<span class="p">, </span>inputs=None<span class="p">, </span>name=None<span class="p">, </span>outputs=None<span class="p">, </span>reference_data_sources=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewAnalyticsApplication<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationArgs">AnalyticsApplicationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplication">AnalyticsApplication</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplication.html">AnalyticsApplication</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationArgs.html">AnalyticsApplicationArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Cloudwatch<wbr>Logging<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationcloudwatchloggingoptions">Analytics<wbr>Application<wbr>Cloudwatch<wbr>Logging<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The CloudWatch log stream options to monitor application errors.
See CloudWatch Logging Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}SQL Code to transform input data, and generate output.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Inputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputs">Analytics<wbr>Application<wbr>Inputs<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Input configuration of the application. See Inputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Outputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutput">List&lt;Analytics<wbr>Application<wbr>Output<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Output destination configuration of the application. See Outputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reference<wbr>Data<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasources">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}An S3 Reference Data Source for the application.
See Reference Data Sources below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of tags for the Kinesis Analytics Application.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cloudwatch<wbr>Logging<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationcloudwatchloggingoptions">*Analytics<wbr>Application<wbr>Cloudwatch<wbr>Logging<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}The CloudWatch log stream options to monitor application errors.
See CloudWatch Logging Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Code<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}SQL Code to transform input data, and generate output.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Inputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputs">*Analytics<wbr>Application<wbr>Inputs</a></span>
    </dt>
    <dd>{{% md %}}Input configuration of the application. See Inputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Outputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutput">[]Analytics<wbr>Application<wbr>Output</a></span>
    </dt>
    <dd>{{% md %}}Output destination configuration of the application. See Outputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reference<wbr>Data<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasources">*Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources</a></span>
    </dt>
    <dd>{{% md %}}An S3 Reference Data Source for the application.
See Reference Data Sources below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of tags for the Kinesis Analytics Application.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cloudwatch<wbr>Logging<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationcloudwatchloggingoptions">Analytics<wbr>Application<wbr>Cloudwatch<wbr>Logging<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}The CloudWatch log stream options to monitor application errors.
See CloudWatch Logging Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}SQL Code to transform input data, and generate output.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">inputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputs">Analytics<wbr>Application<wbr>Inputs?</a></span>
    </dt>
    <dd>{{% md %}}Input configuration of the application. See Inputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">outputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutput">Analytics<wbr>Application<wbr>Output[]?</a></span>
    </dt>
    <dd>{{% md %}}Output destination configuration of the application. See Outputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reference<wbr>Data<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasources">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources?</a></span>
    </dt>
    <dd>{{% md %}}An S3 Reference Data Source for the application.
See Reference Data Sources below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of tags for the Kinesis Analytics Application.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cloudwatch_<wbr>logging_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationcloudwatchloggingoptions">Dict[Analytics<wbr>Application<wbr>Cloudwatch<wbr>Logging<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}The CloudWatch log stream options to monitor application errors.
See CloudWatch Logging Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}SQL Code to transform input data, and generate output.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">inputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputs">Dict[Analytics<wbr>Application<wbr>Inputs]</a></span>
    </dt>
    <dd>{{% md %}}Input configuration of the application. See Inputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">outputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutput">List[Analytics<wbr>Application<wbr>Output]</a></span>
    </dt>
    <dd>{{% md %}}Output destination configuration of the application. See Outputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reference_<wbr>data_<wbr>sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasources">Dict[Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources]</a></span>
    </dt>
    <dd>{{% md %}}An S3 Reference Data Source for the application.
See Reference Data Sources below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of tags for the Kinesis Analytics Application.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## AnalyticsApplication Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Appliation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cloudwatch<wbr>Logging<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationcloudwatchloggingoptions">Analytics<wbr>Application<wbr>Cloudwatch<wbr>Logging<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}The CloudWatch log stream options to monitor application errors.
See CloudWatch Logging Options below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}SQL Code to transform input data, and generate output.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Create<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application version was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Inputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputs">Analytics<wbr>Application<wbr>Inputs?</a></span>
    </dt>
    <dd>{{% md %}}Input configuration of the application. See Inputs below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Update<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application was last updated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Outputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutput">List&lt;Analytics<wbr>Application<wbr>Output&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Output destination configuration of the application. See Outputs below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Reference<wbr>Data<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasources">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources?</a></span>
    </dt>
    <dd>{{% md %}}An S3 Reference Data Source for the application.
See Reference Data Sources below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Status of the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of tags for the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The Version of the application.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Appliation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cloudwatch<wbr>Logging<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationcloudwatchloggingoptions">*Analytics<wbr>Application<wbr>Cloudwatch<wbr>Logging<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}The CloudWatch log stream options to monitor application errors.
See CloudWatch Logging Options below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Code<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}SQL Code to transform input data, and generate output.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Create<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application version was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Inputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputs">*Analytics<wbr>Application<wbr>Inputs</a></span>
    </dt>
    <dd>{{% md %}}Input configuration of the application. See Inputs below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Update<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application was last updated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Outputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutput">[]Analytics<wbr>Application<wbr>Output</a></span>
    </dt>
    <dd>{{% md %}}Output destination configuration of the application. See Outputs below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Reference<wbr>Data<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasources">*Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources</a></span>
    </dt>
    <dd>{{% md %}}An S3 Reference Data Source for the application.
See Reference Data Sources below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Status of the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of tags for the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The Version of the application.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">ARN</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Appliation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cloudwatch<wbr>Logging<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationcloudwatchloggingoptions">Analytics<wbr>Application<wbr>Cloudwatch<wbr>Logging<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}The CloudWatch log stream options to monitor application errors.
See CloudWatch Logging Options below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}SQL Code to transform input data, and generate output.
{{% /md %}}</dd>

    <dt class="property-"
            title="">create<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application version was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">inputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputs">Analytics<wbr>Application<wbr>Inputs?</a></span>
    </dt>
    <dd>{{% md %}}Input configuration of the application. See Inputs below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last<wbr>Update<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application was last updated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">outputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutput">Analytics<wbr>Application<wbr>Output[]?</a></span>
    </dt>
    <dd>{{% md %}}Output destination configuration of the application. See Outputs below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">reference<wbr>Data<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasources">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources?</a></span>
    </dt>
    <dd>{{% md %}}An S3 Reference Data Source for the application.
See Reference Data Sources below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Status of the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of tags for the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The Version of the application.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Appliation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cloudwatch_<wbr>logging_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationcloudwatchloggingoptions">Dict[Analytics<wbr>Application<wbr>Cloudwatch<wbr>Logging<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}The CloudWatch log stream options to monitor application errors.
See CloudWatch Logging Options below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}SQL Code to transform input data, and generate output.
{{% /md %}}</dd>

    <dt class="property-"
            title="">create_<wbr>timestamp<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application version was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">inputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputs">Dict[Analytics<wbr>Application<wbr>Inputs]</a></span>
    </dt>
    <dd>{{% md %}}Input configuration of the application. See Inputs below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last_<wbr>update_<wbr>timestamp<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application was last updated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">outputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutput">List[Analytics<wbr>Application<wbr>Output]</a></span>
    </dt>
    <dd>{{% md %}}Output destination configuration of the application. See Outputs below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">reference_<wbr>data_<wbr>sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasources">Dict[Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources]</a></span>
    </dt>
    <dd>{{% md %}}An S3 Reference Data Source for the application.
See Reference Data Sources below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Status of the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of tags for the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The Version of the application.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing AnalyticsApplication Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/kinesis/#AnalyticsApplicationState">AnalyticsApplicationState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/kinesis/#AnalyticsApplication">AnalyticsApplication</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>cloudwatch_logging_options=None<span class="p">, </span>code=None<span class="p">, </span>create_timestamp=None<span class="p">, </span>description=None<span class="p">, </span>inputs=None<span class="p">, </span>last_update_timestamp=None<span class="p">, </span>name=None<span class="p">, </span>outputs=None<span class="p">, </span>reference_data_sources=None<span class="p">, </span>status=None<span class="p">, </span>tags=None<span class="p">, </span>version=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAnalyticsApplication<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationState">AnalyticsApplicationState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplication">AnalyticsApplication</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplication.html">AnalyticsApplication</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationState.html">AnalyticsApplicationState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing AnalyticsApplication resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The ARN of the Kinesis Analytics Appliation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloudwatch<wbr>Logging<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationcloudwatchloggingoptions">Analytics<wbr>Application<wbr>Cloudwatch<wbr>Logging<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The CloudWatch log stream options to monitor application errors.
See CloudWatch Logging Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}SQL Code to transform input data, and generate output.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Create<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application version was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Inputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputs">Analytics<wbr>Application<wbr>Inputs<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Input configuration of the application. See Inputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Update<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application was last updated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Outputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutput">List&lt;Analytics<wbr>Application<wbr>Output<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Output destination configuration of the application. See Outputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reference<wbr>Data<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasources">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}An S3 Reference Data Source for the application.
See Reference Data Sources below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Status of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of tags for the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The Version of the application.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Appliation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloudwatch<wbr>Logging<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationcloudwatchloggingoptions">*Analytics<wbr>Application<wbr>Cloudwatch<wbr>Logging<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}The CloudWatch log stream options to monitor application errors.
See CloudWatch Logging Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Code<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}SQL Code to transform input data, and generate output.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Create<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application version was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Inputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputs">*Analytics<wbr>Application<wbr>Inputs</a></span>
    </dt>
    <dd>{{% md %}}Input configuration of the application. See Inputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Update<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application was last updated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Outputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutput">[]Analytics<wbr>Application<wbr>Output</a></span>
    </dt>
    <dd>{{% md %}}Output destination configuration of the application. See Outputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reference<wbr>Data<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasources">*Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources</a></span>
    </dt>
    <dd>{{% md %}}An S3 Reference Data Source for the application.
See Reference Data Sources below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Status of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of tags for the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The Version of the application.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">ARN?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Appliation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloudwatch<wbr>Logging<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationcloudwatchloggingoptions">Analytics<wbr>Application<wbr>Cloudwatch<wbr>Logging<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}The CloudWatch log stream options to monitor application errors.
See CloudWatch Logging Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}SQL Code to transform input data, and generate output.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">create<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application version was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">inputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputs">Analytics<wbr>Application<wbr>Inputs?</a></span>
    </dt>
    <dd>{{% md %}}Input configuration of the application. See Inputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last<wbr>Update<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application was last updated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">outputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutput">Analytics<wbr>Application<wbr>Output[]?</a></span>
    </dt>
    <dd>{{% md %}}Output destination configuration of the application. See Outputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reference<wbr>Data<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasources">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources?</a></span>
    </dt>
    <dd>{{% md %}}An S3 Reference Data Source for the application.
See Reference Data Sources below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Status of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of tags for the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The Version of the application.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Appliation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloudwatch_<wbr>logging_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationcloudwatchloggingoptions">Dict[Analytics<wbr>Application<wbr>Cloudwatch<wbr>Logging<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}The CloudWatch log stream options to monitor application errors.
See CloudWatch Logging Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}SQL Code to transform input data, and generate output.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">create_<wbr>timestamp<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application version was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">inputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputs">Dict[Analytics<wbr>Application<wbr>Inputs]</a></span>
    </dt>
    <dd>{{% md %}}Input configuration of the application. See Inputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last_<wbr>update_<wbr>timestamp<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Timestamp when the application was last updated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">outputs<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutput">List[Analytics<wbr>Application<wbr>Output]</a></span>
    </dt>
    <dd>{{% md %}}Output destination configuration of the application. See Outputs below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reference_<wbr>data_<wbr>sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasources">Dict[Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources]</a></span>
    </dt>
    <dd>{{% md %}}An S3 Reference Data Source for the application.
See Reference Data Sources below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Status of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of tags for the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The Version of the application.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### AnalyticsApplicationCloudwatchLoggingOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationCloudwatchLoggingOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationCloudwatchLoggingOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationCloudwatchLoggingOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationCloudwatchLoggingOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationCloudwatchLoggingOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationCloudwatchLoggingOptions.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Log<wbr>Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Log<wbr>Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">log<wbr>Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">log<wbr>Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationInputs
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationInputs">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationInputs">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputs.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<wbr>Firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputskinesisfirehose">Analytics<wbr>Application<wbr>Inputs<wbr>Kinesis<wbr>Firehose<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<wbr>Stream<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputskinesisstream">Analytics<wbr>Application<wbr>Inputs<wbr>Kinesis<wbr>Stream<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parallelism<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsparallelism">Analytics<wbr>Application<wbr>Inputs<wbr>Parallelism<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Processing<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsprocessingconfiguration">Analytics<wbr>Application<wbr>Inputs<wbr>Processing<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Schema<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschema">Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Starting<wbr>Position<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsstartingpositionconfiguration">List&lt;Analytics<wbr>Application<wbr>Inputs<wbr>Starting<wbr>Position<wbr>Configuration<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<wbr>Firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputskinesisfirehose">*Analytics<wbr>Application<wbr>Inputs<wbr>Kinesis<wbr>Firehose</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<wbr>Stream<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputskinesisstream">*Analytics<wbr>Application<wbr>Inputs<wbr>Kinesis<wbr>Stream</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parallelism<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsparallelism">*Analytics<wbr>Application<wbr>Inputs<wbr>Parallelism</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Processing<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsprocessingconfiguration">*Analytics<wbr>Application<wbr>Inputs<wbr>Processing<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Schema<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschema">Analytics<wbr>Application<wbr>Inputs<wbr>Schema</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Starting<wbr>Position<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsstartingpositionconfiguration">[]Analytics<wbr>Application<wbr>Inputs<wbr>Starting<wbr>Position<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis<wbr>Firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputskinesisfirehose">Analytics<wbr>Application<wbr>Inputs<wbr>Kinesis<wbr>Firehose?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis<wbr>Stream<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputskinesisstream">Analytics<wbr>Application<wbr>Inputs<wbr>Kinesis<wbr>Stream?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parallelism<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsparallelism">Analytics<wbr>Application<wbr>Inputs<wbr>Parallelism?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">processing<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsprocessingconfiguration">Analytics<wbr>Application<wbr>Inputs<wbr>Processing<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">schema<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschema">Analytics<wbr>Application<wbr>Inputs<wbr>Schema</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">starting<wbr>Position<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsstartingpositionconfiguration">Analytics<wbr>Application<wbr>Inputs<wbr>Starting<wbr>Position<wbr>Configuration[]?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis<wbr>Firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputskinesisfirehose">Dict[Analytics<wbr>Application<wbr>Inputs<wbr>Kinesis<wbr>Firehose]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis<wbr>Stream<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputskinesisstream">Dict[Analytics<wbr>Application<wbr>Inputs<wbr>Kinesis<wbr>Stream]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parallelism<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsparallelism">Dict[Analytics<wbr>Application<wbr>Inputs<wbr>Parallelism]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">processing<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsprocessingconfiguration">Dict[Analytics<wbr>Application<wbr>Inputs<wbr>Processing<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">schema<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschema">Dict[Analytics<wbr>Application<wbr>Inputs<wbr>Schema]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">starting<wbr>Position<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsstartingpositionconfiguration">List[Analytics<wbr>Application<wbr>Inputs<wbr>Starting<wbr>Position<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationInputsKinesisFirehose
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationInputsKinesisFirehose">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationInputsKinesisFirehose">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsKinesisFirehoseArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsKinesisFirehoseOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsKinesisFirehoseArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsKinesisFirehose.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationInputsKinesisStream
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationInputsKinesisStream">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationInputsKinesisStream">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsKinesisStreamArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsKinesisStreamOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsKinesisStreamArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsKinesisStream.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationInputsParallelism
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationInputsParallelism">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationInputsParallelism">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsParallelismArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsParallelismOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsParallelismArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsParallelism.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">count<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationInputsProcessingConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationInputsProcessingConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationInputsProcessingConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsProcessingConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsProcessingConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsProcessingConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsProcessingConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Lambda<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsprocessingconfigurationlambda">Analytics<wbr>Application<wbr>Inputs<wbr>Processing<wbr>Configuration<wbr>Lambda<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Lambda<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsprocessingconfigurationlambda">Analytics<wbr>Application<wbr>Inputs<wbr>Processing<wbr>Configuration<wbr>Lambda</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">lambda<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsprocessingconfigurationlambda">Analytics<wbr>Application<wbr>Inputs<wbr>Processing<wbr>Configuration<wbr>Lambda</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">lambda_<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsprocessingconfigurationlambda">Dict[Analytics<wbr>Application<wbr>Inputs<wbr>Processing<wbr>Configuration<wbr>Lambda]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationInputsProcessingConfigurationLambda
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationInputsProcessingConfigurationLambda">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationInputsProcessingConfigurationLambda">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsProcessingConfigurationLambdaArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsProcessingConfigurationLambdaOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsProcessingConfigurationLambdaArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsProcessingConfigurationLambda.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationInputsSchema
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationInputsSchema">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationInputsSchema">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsSchemaArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsSchemaOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsSchemaArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsSchema.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Record<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordcolumn">List&lt;Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Column<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Record<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Record<wbr>Format<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformat">Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Record<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordcolumn">[]Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Column</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Record<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Record<wbr>Format<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformat">Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">record<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordcolumn">Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Column[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">record<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">record<wbr>Format<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformat">Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">record<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordcolumn">List[Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Column]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">record<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">record<wbr>Format<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformat">Dict[Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationInputsSchemaRecordColumn
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationInputsSchemaRecordColumn">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationInputsSchemaRecordColumn">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsSchemaRecordColumnArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsSchemaRecordColumnOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsSchemaRecordColumnArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsSchemaRecordColumn.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Mapping<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sql<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Mapping<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sql<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">mapping<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sql<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">mapping<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sql<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationInputsSchemaRecordFormat
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationInputsSchemaRecordFormat">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationInputsSchemaRecordFormat">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsSchemaRecordFormatArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsSchemaRecordFormatOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsSchemaRecordFormatArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsSchemaRecordFormat.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Mapping<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformatmappingparameters">Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Record<wbr>Format<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Mapping<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformatmappingparameters">*Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Record<wbr>Format<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">mapping<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformatmappingparameters">Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">record<wbr>Format<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">mapping<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformatmappingparameters">Dict[Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">record<wbr>Format<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationInputsSchemaRecordFormatMappingParameters
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationInputsSchemaRecordFormatMappingParameters">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationInputsSchemaRecordFormatMappingParameters">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsSchemaRecordFormatMappingParametersArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsSchemaRecordFormatMappingParametersOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsSchemaRecordFormatMappingParametersArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsSchemaRecordFormatMappingParameters.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Csv<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformatmappingparameterscsv">Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Csv<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Json<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformatmappingparametersjson">Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Json<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Csv<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformatmappingparameterscsv">*Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Csv</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Json<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformatmappingparametersjson">*Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Json</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">csv<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformatmappingparameterscsv">Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Csv?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">json<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformatmappingparametersjson">Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Json?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">csv<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformatmappingparameterscsv">Dict[Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Csv]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">json<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationinputsschemarecordformatmappingparametersjson">Dict[Analytics<wbr>Application<wbr>Inputs<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Json]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationInputsSchemaRecordFormatMappingParametersCsv
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationInputsSchemaRecordFormatMappingParametersCsv">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationInputsSchemaRecordFormatMappingParametersCsv">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsSchemaRecordFormatMappingParametersCsvArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsSchemaRecordFormatMappingParametersCsvOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsSchemaRecordFormatMappingParametersCsvArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsSchemaRecordFormatMappingParametersCsv.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Record<wbr>Column<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Record<wbr>Row<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Record<wbr>Column<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Record<wbr>Row<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">record<wbr>Column<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">record<wbr>Row<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">record<wbr>Column<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">record<wbr>Row<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationInputsSchemaRecordFormatMappingParametersJson
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationInputsSchemaRecordFormatMappingParametersJson">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationInputsSchemaRecordFormatMappingParametersJson">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsSchemaRecordFormatMappingParametersJsonArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsSchemaRecordFormatMappingParametersJsonOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsSchemaRecordFormatMappingParametersJsonArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsSchemaRecordFormatMappingParametersJson.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Record<wbr>Row<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Record<wbr>Row<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">record<wbr>Row<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">record<wbr>Row<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationInputsStartingPositionConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationInputsStartingPositionConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationInputsStartingPositionConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsStartingPositionConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationInputsStartingPositionConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsStartingPositionConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationInputsStartingPositionConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Starting<wbr>Position<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Starting<wbr>Position<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">starting<wbr>Position<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">starting_<wbr>position<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationOutput
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationOutput">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationOutputArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationOutputOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationOutputArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationOutput.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<wbr>Firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputkinesisfirehose">Analytics<wbr>Application<wbr>Output<wbr>Kinesis<wbr>Firehose<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<wbr>Stream<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputkinesisstream">Analytics<wbr>Application<wbr>Output<wbr>Kinesis<wbr>Stream<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputlambda">Analytics<wbr>Application<wbr>Output<wbr>Lambda<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Schema<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputschema">Analytics<wbr>Application<wbr>Output<wbr>Schema<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<wbr>Firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputkinesisfirehose">*Analytics<wbr>Application<wbr>Output<wbr>Kinesis<wbr>Firehose</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<wbr>Stream<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputkinesisstream">*Analytics<wbr>Application<wbr>Output<wbr>Kinesis<wbr>Stream</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputlambda">*Analytics<wbr>Application<wbr>Output<wbr>Lambda</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Schema<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputschema">Analytics<wbr>Application<wbr>Output<wbr>Schema</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis<wbr>Firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputkinesisfirehose">Analytics<wbr>Application<wbr>Output<wbr>Kinesis<wbr>Firehose?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis<wbr>Stream<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputkinesisstream">Analytics<wbr>Application<wbr>Output<wbr>Kinesis<wbr>Stream?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputlambda">Analytics<wbr>Application<wbr>Output<wbr>Lambda?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">schema<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputschema">Analytics<wbr>Application<wbr>Output<wbr>Schema</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis<wbr>Firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputkinesisfirehose">Dict[Analytics<wbr>Application<wbr>Output<wbr>Kinesis<wbr>Firehose]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis<wbr>Stream<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputkinesisstream">Dict[Analytics<wbr>Application<wbr>Output<wbr>Kinesis<wbr>Stream]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputlambda">Dict[Analytics<wbr>Application<wbr>Output<wbr>Lambda]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">schema<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationoutputschema">Dict[Analytics<wbr>Application<wbr>Output<wbr>Schema]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationOutputKinesisFirehose
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationOutputKinesisFirehose">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationOutputKinesisFirehose">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationOutputKinesisFirehoseArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationOutputKinesisFirehoseOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationOutputKinesisFirehoseArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationOutputKinesisFirehose.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationOutputKinesisStream
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationOutputKinesisStream">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationOutputKinesisStream">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationOutputKinesisStreamArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationOutputKinesisStreamOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationOutputKinesisStreamArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationOutputKinesisStream.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationOutputLambda
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationOutputLambda">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationOutputLambda">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationOutputLambdaArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationOutputLambdaOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationOutputLambdaArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationOutputLambda.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationOutputSchema
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationOutputSchema">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationOutputSchema">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationOutputSchemaArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationOutputSchemaOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationOutputSchemaArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationOutputSchema.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Record<wbr>Format<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Record<wbr>Format<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">record<wbr>Format<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">record<wbr>Format<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationReferenceDataSources
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationReferenceDataSources">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationReferenceDataSources">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSourcesArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSources.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">S3<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcess3">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>S3Args</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Schema<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschema">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Table<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">S3<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcess3">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>S3</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Schema<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschema">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Table<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">s3<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcess3">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>S3</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">schema<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschema">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">table<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">s3<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcess3">Dict[Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>S3]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">schema<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschema">Dict[Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">table_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationReferenceDataSourcesS3
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationReferenceDataSourcesS3">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationReferenceDataSourcesS3">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesS3Args">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesS3Output">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSourcesS3Args.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSourcesS3.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Bucket<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">File<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Bucket<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">File<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">file<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">file<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationReferenceDataSourcesSchema
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationReferenceDataSourcesSchema">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationReferenceDataSourcesSchema">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesSchemaArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesSchemaOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSourcesSchemaArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSourcesSchema.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Record<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordcolumn">List&lt;Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Column<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Record<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Record<wbr>Format<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformat">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Record<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordcolumn">[]Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Column</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Record<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Record<wbr>Format<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformat">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">record<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordcolumn">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Column[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">record<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">record<wbr>Format<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformat">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">record<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordcolumn">List[Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Column]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">record<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">record<wbr>Format<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformat">Dict[Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationReferenceDataSourcesSchemaRecordColumn
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationReferenceDataSourcesSchemaRecordColumn">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationReferenceDataSourcesSchemaRecordColumn">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesSchemaRecordColumnArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesSchemaRecordColumnOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSourcesSchemaRecordColumnArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSourcesSchemaRecordColumn.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Mapping<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sql<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Mapping<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sql<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">mapping<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sql<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">mapping<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the Kinesis Analytics Application.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sql<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationReferenceDataSourcesSchemaRecordFormat
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormat">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormat">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSourcesSchemaRecordFormat.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Mapping<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformatmappingparameters">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Record<wbr>Format<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Mapping<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformatmappingparameters">*Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Record<wbr>Format<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">mapping<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformatmappingparameters">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">record<wbr>Format<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">mapping<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformatmappingparameters">Dict[Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">record<wbr>Format<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParameters
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParameters">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParameters">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParameters.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Csv<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformatmappingparameterscsv">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Csv<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Json<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformatmappingparametersjson">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Json<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Csv<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformatmappingparameterscsv">*Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Csv</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Json<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformatmappingparametersjson">*Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Json</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">csv<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformatmappingparameterscsv">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Csv?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">json<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformatmappingparametersjson">Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Json?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">csv<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformatmappingparameterscsv">Dict[Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Csv]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">json<span class="property-indicator"></span>
        <span class="property-type"><a href="#analyticsapplicationreferencedatasourcesschemarecordformatmappingparametersjson">Dict[Analytics<wbr>Application<wbr>Reference<wbr>Data<wbr>Sources<wbr>Schema<wbr>Record<wbr>Format<wbr>Mapping<wbr>Parameters<wbr>Json]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersCsv
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersCsv">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersCsv">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersCsvArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersCsvOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersCsvArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersCsv.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Record<wbr>Column<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Record<wbr>Row<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Record<wbr>Column<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Record<wbr>Row<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">record<wbr>Column<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">record<wbr>Row<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">record<wbr>Column<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">record<wbr>Row<wbr>Delimiter<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersJson
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersJson">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersJson">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersJsonArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/kinesis?tab=doc#AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersJsonOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersJsonArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Kinesis.AnalyticsApplicationReferenceDataSourcesSchemaRecordFormatMappingParametersJson.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Record<wbr>Row<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Record<wbr>Row<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">record<wbr>Row<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">record<wbr>Row<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}









---
title: "Crawler"
block_external_search_index: true
---

Manages a Glue Crawler. More information can be found in the [AWS Glue Developer Guide](https://docs.aws.amazon.com/glue/latest/dg/add-crawler.html)

## Example Usage

### DynamoDB Target

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.glue.Crawler("example", {
    databaseName: aws_glue_catalog_database_example.name,
    dynamodbTargets: [{
        path: "table-name",
    }],
    role: aws_iam_role_example.arn,
});
```

### JDBC Target

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.glue.Crawler("example", {
    databaseName: aws_glue_catalog_database_example.name,
    jdbcTargets: [{
        connectionName: aws_glue_connection_example.name,
        path: "database-name/%",
    }],
    role: aws_iam_role_example.arn,
});
```

### S3 Target

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.glue.Crawler("example", {
    databaseName: aws_glue_catalog_database_example.name,
    role: aws_iam_role_example.arn,
    s3Targets: [{
        path: pulumi.interpolate`s3://${aws_s3_bucket_example.bucket}`,
    }],
});
```


### Catalog Target

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.glue.Crawler("example", {
    catalogTargets: [{
        databaseName: aws_glue_catalog_database_example.name,
        tables: [aws_glue_catalog_table_example.name],
    }],
    configuration: `{
  "Version":1.0,
  "Grouping": {
    "TableGroupingPolicy": "CombineCompatibleSchemas"
  }
}
`,
    databaseName: aws_glue_catalog_database_example.name,
    role: aws_iam_role_example.arn,
    schemaChangePolicy: {
        deleteBehavior: "LOG",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/glue_crawler.html.markdown.



## Create a Crawler Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#Crawler">Crawler</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#CrawlerArgs">CrawlerArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Crawler</span><span class="p">(resource_name, opts=None, </span>catalog_targets=None<span class="p">, </span>classifiers=None<span class="p">, </span>configuration=None<span class="p">, </span>database_name=None<span class="p">, </span>description=None<span class="p">, </span>dynamodb_targets=None<span class="p">, </span>jdbc_targets=None<span class="p">, </span>name=None<span class="p">, </span>role=None<span class="p">, </span>s3_targets=None<span class="p">, </span>schedule=None<span class="p">, </span>schema_change_policy=None<span class="p">, </span>security_configuration=None<span class="p">, </span>table_prefix=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewCrawler<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CrawlerArgs">CrawlerArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#Crawler">Crawler</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.Crawler.html">Crawler</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CrawlerArgs.html">CrawlerArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Catalog<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlercatalogtarget">List&lt;Crawler<wbr>Catalog<wbr>Target<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Classifiers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of custom classifiers. By default, all AWS classifiers are included in a crawl, but these custom classifiers always override the default classifiers for a given classification.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}JSON string of configuration information.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the crawler.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dynamodb<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerdynamodbtarget">List&lt;Crawler<wbr>Dynamodb<wbr>Target<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List of nested DynamoDB target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jdbc<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerjdbctarget">List&lt;Crawler<wbr>Jdbc<wbr>Target<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List of nested JBDC target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the crawler.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM role friendly name (including path without leading slash), or ARN of an IAM role, used by the crawler to access other resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlers3target">List&lt;Crawler<wbr>S3Target<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List nested Amazon S3 target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schedule<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cron expression used to specify the schedule. For more information, see [Time-Based Schedules for Jobs and Crawlers](https://docs.aws.amazon.com/glue/latest/dg/monitor-data-warehouse-schedule.html). For example, to run something every day at 12:15 UTC, you would specify: `cron(15 12 * * ? *)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schema<wbr>Change<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerschemachangepolicy">Crawler<wbr>Schema<wbr>Change<wbr>Policy<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Policy for the crawler&#39;s update and deletion behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of Security Configuration to be used by the crawler
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Table<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The table prefix used for catalog tables that are created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Catalog<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlercatalogtarget">[]Crawler<wbr>Catalog<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Classifiers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of custom classifiers. By default, all AWS classifiers are included in a crawl, but these custom classifiers always override the default classifiers for a given classification.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}JSON string of configuration information.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the crawler.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dynamodb<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerdynamodbtarget">[]Crawler<wbr>Dynamodb<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}List of nested DynamoDB target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jdbc<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerjdbctarget">[]Crawler<wbr>Jdbc<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}List of nested JBDC target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the crawler.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM role friendly name (including path without leading slash), or ARN of an IAM role, used by the crawler to access other resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlers3target">[]Crawler<wbr>S3Target</a></span>
    </dt>
    <dd>{{% md %}}List nested Amazon S3 target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schedule<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A cron expression used to specify the schedule. For more information, see [Time-Based Schedules for Jobs and Crawlers](https://docs.aws.amazon.com/glue/latest/dg/monitor-data-warehouse-schedule.html). For example, to run something every day at 12:15 UTC, you would specify: `cron(15 12 * * ? *)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schema<wbr>Change<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerschemachangepolicy">*Crawler<wbr>Schema<wbr>Change<wbr>Policy</a></span>
    </dt>
    <dd>{{% md %}}Policy for the crawler&#39;s update and deletion behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of Security Configuration to be used by the crawler
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Table<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The table prefix used for catalog tables that are created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">catalog<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlercatalogtarget">Crawler<wbr>Catalog<wbr>Target[]?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">classifiers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of custom classifiers. By default, all AWS classifiers are included in a crawl, but these custom classifiers always override the default classifiers for a given classification.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}JSON string of configuration information.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the crawler.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dynamodb<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerdynamodbtarget">Crawler<wbr>Dynamodb<wbr>Target[]?</a></span>
    </dt>
    <dd>{{% md %}}List of nested DynamoDB target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jdbc<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerjdbctarget">Crawler<wbr>Jdbc<wbr>Target[]?</a></span>
    </dt>
    <dd>{{% md %}}List of nested JBDC target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the crawler.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM role friendly name (including path without leading slash), or ARN of an IAM role, used by the crawler to access other resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlers3target">Crawler<wbr>S3Target[]?</a></span>
    </dt>
    <dd>{{% md %}}List nested Amazon S3 target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schedule<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cron expression used to specify the schedule. For more information, see [Time-Based Schedules for Jobs and Crawlers](https://docs.aws.amazon.com/glue/latest/dg/monitor-data-warehouse-schedule.html). For example, to run something every day at 12:15 UTC, you would specify: `cron(15 12 * * ? *)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schema<wbr>Change<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerschemachangepolicy">Crawler<wbr>Schema<wbr>Change<wbr>Policy?</a></span>
    </dt>
    <dd>{{% md %}}Policy for the crawler&#39;s update and deletion behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of Security Configuration to be used by the crawler
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">table<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The table prefix used for catalog tables that are created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">catalog_<wbr>targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlercatalogtarget">List[Crawler<wbr>Catalog<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">classifiers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of custom classifiers. By default, all AWS classifiers are included in a crawl, but these custom classifiers always override the default classifiers for a given classification.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}JSON string of configuration information.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">database_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the crawler.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dynamodb_<wbr>targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerdynamodbtarget">List[Crawler<wbr>Dynamodb<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}List of nested DynamoDB target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jdbc_<wbr>targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerjdbctarget">List[Crawler<wbr>Jdbc<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}List of nested JBDC target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the crawler.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM role friendly name (including path without leading slash), or ARN of an IAM role, used by the crawler to access other resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlers3target">List[Crawler<wbr>S3Target]</a></span>
    </dt>
    <dd>{{% md %}}List nested Amazon S3 target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schedule<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A cron expression used to specify the schedule. For more information, see [Time-Based Schedules for Jobs and Crawlers](https://docs.aws.amazon.com/glue/latest/dg/monitor-data-warehouse-schedule.html). For example, to run something every day at 12:15 UTC, you would specify: `cron(15 12 * * ? *)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schema_<wbr>change_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerschemachangepolicy">Dict[Crawler<wbr>Schema<wbr>Change<wbr>Policy]</a></span>
    </dt>
    <dd>{{% md %}}Policy for the crawler&#39;s update and deletion behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of Security Configuration to be used by the crawler
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">table_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The table prefix used for catalog tables that are created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Crawler Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the crawler 
{{% /md %}}</dd>

    <dt class="property-"
            title="">Catalog<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlercatalogtarget">List&lt;Crawler<wbr>Catalog<wbr>Target&gt;?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Classifiers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of custom classifiers. By default, all AWS classifiers are included in a crawl, but these custom classifiers always override the default classifiers for a given classification.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}JSON string of configuration information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the crawler.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dynamodb<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerdynamodbtarget">List&lt;Crawler<wbr>Dynamodb<wbr>Target&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List of nested DynamoDB target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Jdbc<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerjdbctarget">List&lt;Crawler<wbr>Jdbc<wbr>Target&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List of nested JBDC target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the crawler.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM role friendly name (including path without leading slash), or ARN of an IAM role, used by the crawler to access other resources.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlers3target">List&lt;Crawler<wbr>S3Target&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List nested Amazon S3 target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Schedule<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cron expression used to specify the schedule. For more information, see [Time-Based Schedules for Jobs and Crawlers](https://docs.aws.amazon.com/glue/latest/dg/monitor-data-warehouse-schedule.html). For example, to run something every day at 12:15 UTC, you would specify: `cron(15 12 * * ? *)`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Schema<wbr>Change<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerschemachangepolicy">Crawler<wbr>Schema<wbr>Change<wbr>Policy?</a></span>
    </dt>
    <dd>{{% md %}}Policy for the crawler&#39;s update and deletion behavior.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of Security Configuration to be used by the crawler
{{% /md %}}</dd>

    <dt class="property-"
            title="">Table<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The table prefix used for catalog tables that are created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the crawler 
{{% /md %}}</dd>

    <dt class="property-"
            title="">Catalog<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlercatalogtarget">[]Crawler<wbr>Catalog<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Classifiers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of custom classifiers. By default, all AWS classifiers are included in a crawl, but these custom classifiers always override the default classifiers for a given classification.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}JSON string of configuration information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the crawler.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dynamodb<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerdynamodbtarget">[]Crawler<wbr>Dynamodb<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}List of nested DynamoDB target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Jdbc<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerjdbctarget">[]Crawler<wbr>Jdbc<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}List of nested JBDC target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the crawler.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM role friendly name (including path without leading slash), or ARN of an IAM role, used by the crawler to access other resources.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlers3target">[]Crawler<wbr>S3Target</a></span>
    </dt>
    <dd>{{% md %}}List nested Amazon S3 target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Schedule<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A cron expression used to specify the schedule. For more information, see [Time-Based Schedules for Jobs and Crawlers](https://docs.aws.amazon.com/glue/latest/dg/monitor-data-warehouse-schedule.html). For example, to run something every day at 12:15 UTC, you would specify: `cron(15 12 * * ? *)`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Schema<wbr>Change<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerschemachangepolicy">*Crawler<wbr>Schema<wbr>Change<wbr>Policy</a></span>
    </dt>
    <dd>{{% md %}}Policy for the crawler&#39;s update and deletion behavior.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of Security Configuration to be used by the crawler
{{% /md %}}</dd>

    <dt class="property-"
            title="">Table<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The table prefix used for catalog tables that are created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the crawler 
{{% /md %}}</dd>

    <dt class="property-"
            title="">catalog<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlercatalogtarget">Crawler<wbr>Catalog<wbr>Target[]?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">classifiers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of custom classifiers. By default, all AWS classifiers are included in a crawl, but these custom classifiers always override the default classifiers for a given classification.
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}JSON string of configuration information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the crawler.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dynamodb<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerdynamodbtarget">Crawler<wbr>Dynamodb<wbr>Target[]?</a></span>
    </dt>
    <dd>{{% md %}}List of nested DynamoDB target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">jdbc<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerjdbctarget">Crawler<wbr>Jdbc<wbr>Target[]?</a></span>
    </dt>
    <dd>{{% md %}}List of nested JBDC target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the crawler.
{{% /md %}}</dd>

    <dt class="property-"
            title="">role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM role friendly name (including path without leading slash), or ARN of an IAM role, used by the crawler to access other resources.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlers3target">Crawler<wbr>S3Target[]?</a></span>
    </dt>
    <dd>{{% md %}}List nested Amazon S3 target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">schedule<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cron expression used to specify the schedule. For more information, see [Time-Based Schedules for Jobs and Crawlers](https://docs.aws.amazon.com/glue/latest/dg/monitor-data-warehouse-schedule.html). For example, to run something every day at 12:15 UTC, you would specify: `cron(15 12 * * ? *)`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">schema<wbr>Change<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerschemachangepolicy">Crawler<wbr>Schema<wbr>Change<wbr>Policy?</a></span>
    </dt>
    <dd>{{% md %}}Policy for the crawler&#39;s update and deletion behavior.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of Security Configuration to be used by the crawler
{{% /md %}}</dd>

    <dt class="property-"
            title="">table<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The table prefix used for catalog tables that are created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the crawler 
{{% /md %}}</dd>

    <dt class="property-"
            title="">catalog_<wbr>targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlercatalogtarget">List[Crawler<wbr>Catalog<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">classifiers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of custom classifiers. By default, all AWS classifiers are included in a crawl, but these custom classifiers always override the default classifiers for a given classification.
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}JSON string of configuration information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">database_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the crawler.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dynamodb_<wbr>targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerdynamodbtarget">List[Crawler<wbr>Dynamodb<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}List of nested DynamoDB target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">jdbc_<wbr>targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerjdbctarget">List[Crawler<wbr>Jdbc<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}List of nested JBDC target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the crawler.
{{% /md %}}</dd>

    <dt class="property-"
            title="">role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM role friendly name (including path without leading slash), or ARN of an IAM role, used by the crawler to access other resources.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3_<wbr>targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlers3target">List[Crawler<wbr>S3Target]</a></span>
    </dt>
    <dd>{{% md %}}List nested Amazon S3 target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">schedule<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A cron expression used to specify the schedule. For more information, see [Time-Based Schedules for Jobs and Crawlers](https://docs.aws.amazon.com/glue/latest/dg/monitor-data-warehouse-schedule.html). For example, to run something every day at 12:15 UTC, you would specify: `cron(15 12 * * ? *)`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">schema_<wbr>change_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerschemachangepolicy">Dict[Crawler<wbr>Schema<wbr>Change<wbr>Policy]</a></span>
    </dt>
    <dd>{{% md %}}Policy for the crawler&#39;s update and deletion behavior.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of Security Configuration to be used by the crawler
{{% /md %}}</dd>

    <dt class="property-"
            title="">table_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The table prefix used for catalog tables that are created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Crawler Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#CrawlerState">CrawlerState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#Crawler">Crawler</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>catalog_targets=None<span class="p">, </span>classifiers=None<span class="p">, </span>configuration=None<span class="p">, </span>database_name=None<span class="p">, </span>description=None<span class="p">, </span>dynamodb_targets=None<span class="p">, </span>jdbc_targets=None<span class="p">, </span>name=None<span class="p">, </span>role=None<span class="p">, </span>s3_targets=None<span class="p">, </span>schedule=None<span class="p">, </span>schema_change_policy=None<span class="p">, </span>security_configuration=None<span class="p">, </span>table_prefix=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetCrawler<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CrawlerState">CrawlerState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#Crawler">Crawler</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.Crawler.html">Crawler</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CrawlerState.html">CrawlerState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Crawler resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The ARN of the crawler 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Catalog<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlercatalogtarget">List&lt;Crawler<wbr>Catalog<wbr>Target<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Classifiers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of custom classifiers. By default, all AWS classifiers are included in a crawl, but these custom classifiers always override the default classifiers for a given classification.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}JSON string of configuration information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the crawler.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dynamodb<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerdynamodbtarget">List&lt;Crawler<wbr>Dynamodb<wbr>Target<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List of nested DynamoDB target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jdbc<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerjdbctarget">List&lt;Crawler<wbr>Jdbc<wbr>Target<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List of nested JBDC target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the crawler.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role friendly name (including path without leading slash), or ARN of an IAM role, used by the crawler to access other resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlers3target">List&lt;Crawler<wbr>S3Target<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List nested Amazon S3 target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schedule<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cron expression used to specify the schedule. For more information, see [Time-Based Schedules for Jobs and Crawlers](https://docs.aws.amazon.com/glue/latest/dg/monitor-data-warehouse-schedule.html). For example, to run something every day at 12:15 UTC, you would specify: `cron(15 12 * * ? *)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schema<wbr>Change<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerschemachangepolicy">Crawler<wbr>Schema<wbr>Change<wbr>Policy<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Policy for the crawler&#39;s update and deletion behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of Security Configuration to be used by the crawler
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Table<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The table prefix used for catalog tables that are created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the crawler 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Catalog<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlercatalogtarget">[]Crawler<wbr>Catalog<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Classifiers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of custom classifiers. By default, all AWS classifiers are included in a crawl, but these custom classifiers always override the default classifiers for a given classification.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}JSON string of configuration information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the crawler.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dynamodb<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerdynamodbtarget">[]Crawler<wbr>Dynamodb<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}List of nested DynamoDB target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jdbc<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerjdbctarget">[]Crawler<wbr>Jdbc<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}List of nested JBDC target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the crawler.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Role<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM role friendly name (including path without leading slash), or ARN of an IAM role, used by the crawler to access other resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlers3target">[]Crawler<wbr>S3Target</a></span>
    </dt>
    <dd>{{% md %}}List nested Amazon S3 target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schedule<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A cron expression used to specify the schedule. For more information, see [Time-Based Schedules for Jobs and Crawlers](https://docs.aws.amazon.com/glue/latest/dg/monitor-data-warehouse-schedule.html). For example, to run something every day at 12:15 UTC, you would specify: `cron(15 12 * * ? *)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schema<wbr>Change<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerschemachangepolicy">*Crawler<wbr>Schema<wbr>Change<wbr>Policy</a></span>
    </dt>
    <dd>{{% md %}}Policy for the crawler&#39;s update and deletion behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of Security Configuration to be used by the crawler
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Table<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The table prefix used for catalog tables that are created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the crawler 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">catalog<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlercatalogtarget">Crawler<wbr>Catalog<wbr>Target[]?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">classifiers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of custom classifiers. By default, all AWS classifiers are included in a crawl, but these custom classifiers always override the default classifiers for a given classification.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}JSON string of configuration information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the crawler.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dynamodb<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerdynamodbtarget">Crawler<wbr>Dynamodb<wbr>Target[]?</a></span>
    </dt>
    <dd>{{% md %}}List of nested DynamoDB target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jdbc<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerjdbctarget">Crawler<wbr>Jdbc<wbr>Target[]?</a></span>
    </dt>
    <dd>{{% md %}}List of nested JBDC target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the crawler.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role friendly name (including path without leading slash), or ARN of an IAM role, used by the crawler to access other resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlers3target">Crawler<wbr>S3Target[]?</a></span>
    </dt>
    <dd>{{% md %}}List nested Amazon S3 target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schedule<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cron expression used to specify the schedule. For more information, see [Time-Based Schedules for Jobs and Crawlers](https://docs.aws.amazon.com/glue/latest/dg/monitor-data-warehouse-schedule.html). For example, to run something every day at 12:15 UTC, you would specify: `cron(15 12 * * ? *)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schema<wbr>Change<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerschemachangepolicy">Crawler<wbr>Schema<wbr>Change<wbr>Policy?</a></span>
    </dt>
    <dd>{{% md %}}Policy for the crawler&#39;s update and deletion behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of Security Configuration to be used by the crawler
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">table<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The table prefix used for catalog tables that are created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the crawler 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">catalog_<wbr>targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlercatalogtarget">List[Crawler<wbr>Catalog<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">classifiers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of custom classifiers. By default, all AWS classifiers are included in a crawl, but these custom classifiers always override the default classifiers for a given classification.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}JSON string of configuration information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">database_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the crawler.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dynamodb_<wbr>targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerdynamodbtarget">List[Crawler<wbr>Dynamodb<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}List of nested DynamoDB target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jdbc_<wbr>targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerjdbctarget">List[Crawler<wbr>Jdbc<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}List of nested JBDC target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the crawler.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM role friendly name (including path without leading slash), or ARN of an IAM role, used by the crawler to access other resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlers3target">List[Crawler<wbr>S3Target]</a></span>
    </dt>
    <dd>{{% md %}}List nested Amazon S3 target arguments. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schedule<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A cron expression used to specify the schedule. For more information, see [Time-Based Schedules for Jobs and Crawlers](https://docs.aws.amazon.com/glue/latest/dg/monitor-data-warehouse-schedule.html). For example, to run something every day at 12:15 UTC, you would specify: `cron(15 12 * * ? *)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schema_<wbr>change_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#crawlerschemachangepolicy">Dict[Crawler<wbr>Schema<wbr>Change<wbr>Policy]</a></span>
    </dt>
    <dd>{{% md %}}Policy for the crawler&#39;s update and deletion behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of Security Configuration to be used by the crawler
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">table_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The table prefix used for catalog tables that are created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### CrawlerCatalogTarget
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CrawlerCatalogTarget">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CrawlerCatalogTarget">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CrawlerCatalogTargetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CrawlerCatalogTargetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CrawlerCatalogTargetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CrawlerCatalogTarget.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Tables<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of catalog tables to be synchronized.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Tables<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of catalog tables to be synchronized.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">tables<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of catalog tables to be synchronized.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">database_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Glue database to be synchronized.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">tables<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of catalog tables to be synchronized.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### CrawlerDynamodbTarget
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CrawlerDynamodbTarget">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CrawlerDynamodbTarget">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CrawlerDynamodbTargetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CrawlerDynamodbTargetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CrawlerDynamodbTargetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CrawlerDynamodbTarget.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The path to the Amazon S3 target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The path to the Amazon S3 target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The path to the Amazon S3 target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The path to the Amazon S3 target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### CrawlerJdbcTarget
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CrawlerJdbcTarget">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CrawlerJdbcTarget">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CrawlerJdbcTargetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CrawlerJdbcTargetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CrawlerJdbcTargetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CrawlerJdbcTarget.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Connection<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the connection to use to connect to the JDBC target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Exclusions<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of glob patterns used to exclude from the crawl.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The path to the Amazon S3 target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Connection<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the connection to use to connect to the JDBC target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Exclusions<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of glob patterns used to exclude from the crawl.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The path to the Amazon S3 target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">connection<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the connection to use to connect to the JDBC target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">exclusions<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of glob patterns used to exclude from the crawl.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The path to the Amazon S3 target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">connection<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the connection to use to connect to the JDBC target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">exclusions<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of glob patterns used to exclude from the crawl.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The path to the Amazon S3 target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### CrawlerS3Target
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CrawlerS3Target">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CrawlerS3Target">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CrawlerS3TargetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CrawlerS3TargetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CrawlerS3TargetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CrawlerS3Target.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Exclusions<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of glob patterns used to exclude from the crawl.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The path to the Amazon S3 target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Exclusions<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of glob patterns used to exclude from the crawl.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The path to the Amazon S3 target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">exclusions<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of glob patterns used to exclude from the crawl.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The path to the Amazon S3 target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">exclusions<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of glob patterns used to exclude from the crawl.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The path to the Amazon S3 target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### CrawlerSchemaChangePolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CrawlerSchemaChangePolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CrawlerSchemaChangePolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CrawlerSchemaChangePolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CrawlerSchemaChangePolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CrawlerSchemaChangePolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CrawlerSchemaChangePolicy.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The deletion behavior when the crawler finds a deleted object. Valid values: `LOG`, `DELETE_FROM_DATABASE`, or `DEPRECATE_IN_DATABASE`. Defaults to `DEPRECATE_IN_DATABASE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Update<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The update behavior when the crawler finds a changed schema. Valid values: `LOG` or `UPDATE_IN_DATABASE`. Defaults to `UPDATE_IN_DATABASE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The deletion behavior when the crawler finds a deleted object. Valid values: `LOG`, `DELETE_FROM_DATABASE`, or `DEPRECATE_IN_DATABASE`. Defaults to `DEPRECATE_IN_DATABASE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Update<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The update behavior when the crawler finds a changed schema. Valid values: `LOG` or `UPDATE_IN_DATABASE`. Defaults to `UPDATE_IN_DATABASE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">delete<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The deletion behavior when the crawler finds a deleted object. Valid values: `LOG`, `DELETE_FROM_DATABASE`, or `DEPRECATE_IN_DATABASE`. Defaults to `DEPRECATE_IN_DATABASE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">update<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The update behavior when the crawler finds a changed schema. Valid values: `LOG` or `UPDATE_IN_DATABASE`. Defaults to `UPDATE_IN_DATABASE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">delete<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The deletion behavior when the crawler finds a deleted object. Valid values: `LOG`, `DELETE_FROM_DATABASE`, or `DEPRECATE_IN_DATABASE`. Defaults to `DEPRECATE_IN_DATABASE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">update<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The update behavior when the crawler finds a changed schema. Valid values: `LOG` or `UPDATE_IN_DATABASE`. Defaults to `UPDATE_IN_DATABASE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








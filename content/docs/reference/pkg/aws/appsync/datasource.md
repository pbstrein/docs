
---
title: "DataSource"
block_external_search_index: true
---

Provides an AppSync DataSource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleTable = new aws.dynamodb.Table("example", {
    attributes: [{
        name: "UserId",
        type: "S",
    }],
    hashKey: "UserId",
    readCapacity: 1,
    writeCapacity: 1,
});
const exampleRole = new aws.iam.Role("example", {
    assumeRolePolicy: `{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": "sts:AssumeRole",
      "Principal": {
        "Service": "appsync.amazonaws.com"
      },
      "Effect": "Allow"
    }
  ]
}
`,
});
const exampleRolePolicy = new aws.iam.RolePolicy("example", {
    policy: pulumi.interpolate`{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": [
        "dynamodb:*"
      ],
      "Effect": "Allow",
      "Resource": [
        "${exampleTable.arn}"
      ]
    }
  ]
}
`,
    role: exampleRole.id,
});
const exampleGraphQLApi = new aws.appsync.GraphQLApi("example", {
    authenticationType: "API_KEY",
});
const exampleDataSource = new aws.appsync.DataSource("example", {
    apiId: exampleGraphQLApi.id,
    dynamodbConfig: {
        tableName: exampleTable.name,
    },
    serviceRoleArn: exampleRole.arn,
    type: "AMAZON_DYNAMODB",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/appsync_datasource.html.markdown.



## Create a DataSource Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appsync/#DataSource">DataSource</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appsync/#DataSourceArgs">DataSourceArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">DataSource</span><span class="p">(resource_name, opts=None, </span>api_id=None<span class="p">, </span>description=None<span class="p">, </span>dynamodb_config=None<span class="p">, </span>elasticsearch_config=None<span class="p">, </span>http_config=None<span class="p">, </span>lambda_config=None<span class="p">, </span>name=None<span class="p">, </span>service_role_arn=None<span class="p">, </span>type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDataSource<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#DataSourceArgs">DataSourceArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#DataSource">DataSource</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.DataSource.html">DataSource</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.DataSourceArgs.html">DataSourceArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dynamodb<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcedynamodbconfig">Data<wbr>Source<wbr>Dynamodb<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}DynamoDB settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elasticsearch<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourceelasticsearchconfig">Data<wbr>Source<wbr>Elasticsearch<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Amazon Elasticsearch settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcehttpconfig">Data<wbr>Source<wbr>Http<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}HTTP settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcelambdaconfig">Data<wbr>Source<wbr>Lambda<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}AWS Lambda settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM service role ARN for the data source.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the DataSource. Valid values: `AWS_LAMBDA`, `AMAZON_DYNAMODB`, `AMAZON_ELASTICSEARCH`, `HTTP`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A description of the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dynamodb<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcedynamodbconfig">*Data<wbr>Source<wbr>Dynamodb<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}DynamoDB settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elasticsearch<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourceelasticsearchconfig">*Data<wbr>Source<wbr>Elasticsearch<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Amazon Elasticsearch settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcehttpconfig">*Data<wbr>Source<wbr>Http<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}HTTP settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcelambdaconfig">*Data<wbr>Source<wbr>Lambda<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}AWS Lambda settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM service role ARN for the data source.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the DataSource. Valid values: `AWS_LAMBDA`, `AMAZON_DYNAMODB`, `AMAZON_ELASTICSEARCH`, `HTTP`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dynamodb<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcedynamodbconfig">Data<wbr>Source<wbr>Dynamodb<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}DynamoDB settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elasticsearch<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourceelasticsearchconfig">Data<wbr>Source<wbr>Elasticsearch<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Amazon Elasticsearch settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcehttpconfig">Data<wbr>Source<wbr>Http<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}HTTP settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcelambdaconfig">Data<wbr>Source<wbr>Lambda<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}AWS Lambda settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM service role ARN for the data source.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the DataSource. Valid values: `AWS_LAMBDA`, `AMAZON_DYNAMODB`, `AMAZON_ELASTICSEARCH`, `HTTP`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">api_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A description of the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dynamodb_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcedynamodbconfig">Dict[Data<wbr>Source<wbr>Dynamodb<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}DynamoDB settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elasticsearch_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourceelasticsearchconfig">Dict[Data<wbr>Source<wbr>Elasticsearch<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Amazon Elasticsearch settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcehttpconfig">Dict[Data<wbr>Source<wbr>Http<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}HTTP settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcelambdaconfig">Dict[Data<wbr>Source<wbr>Lambda<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}AWS Lambda settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM service role ARN for the data source.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the DataSource. Valid values: `AWS_LAMBDA`, `AMAZON_DYNAMODB`, `AMAZON_ELASTICSEARCH`, `HTTP`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## DataSource Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API for the DataSource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the DataSource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dynamodb<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcedynamodbconfig">Data<wbr>Source<wbr>Dynamodb<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}DynamoDB settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elasticsearch<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourceelasticsearchconfig">Data<wbr>Source<wbr>Elasticsearch<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Amazon Elasticsearch settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcehttpconfig">Data<wbr>Source<wbr>Http<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}HTTP settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcelambdaconfig">Data<wbr>Source<wbr>Lambda<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}AWS Lambda settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the DataSource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM service role ARN for the data source.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the DataSource. Valid values: `AWS_LAMBDA`, `AMAZON_DYNAMODB`, `AMAZON_ELASTICSEARCH`, `HTTP`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API for the DataSource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A description of the DataSource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dynamodb<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcedynamodbconfig">*Data<wbr>Source<wbr>Dynamodb<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}DynamoDB settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elasticsearch<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourceelasticsearchconfig">*Data<wbr>Source<wbr>Elasticsearch<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Amazon Elasticsearch settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcehttpconfig">*Data<wbr>Source<wbr>Http<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}HTTP settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcelambdaconfig">*Data<wbr>Source<wbr>Lambda<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}AWS Lambda settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the DataSource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM service role ARN for the data source.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the DataSource. Valid values: `AWS_LAMBDA`, `AMAZON_DYNAMODB`, `AMAZON_ELASTICSEARCH`, `HTTP`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API for the DataSource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the DataSource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dynamodb<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcedynamodbconfig">Data<wbr>Source<wbr>Dynamodb<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}DynamoDB settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">elasticsearch<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourceelasticsearchconfig">Data<wbr>Source<wbr>Elasticsearch<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Amazon Elasticsearch settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">http<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcehttpconfig">Data<wbr>Source<wbr>Http<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}HTTP settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcelambdaconfig">Data<wbr>Source<wbr>Lambda<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}AWS Lambda settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the DataSource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM service role ARN for the data source.
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the DataSource. Valid values: `AWS_LAMBDA`, `AMAZON_DYNAMODB`, `AMAZON_ELASTICSEARCH`, `HTTP`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">api_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API for the DataSource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A description of the DataSource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dynamodb_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcedynamodbconfig">Dict[Data<wbr>Source<wbr>Dynamodb<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}DynamoDB settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">elasticsearch_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourceelasticsearchconfig">Dict[Data<wbr>Source<wbr>Elasticsearch<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Amazon Elasticsearch settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">http_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcehttpconfig">Dict[Data<wbr>Source<wbr>Http<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}HTTP settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcelambdaconfig">Dict[Data<wbr>Source<wbr>Lambda<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}AWS Lambda settings. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the DataSource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM service role ARN for the data source.
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the DataSource. Valid values: `AWS_LAMBDA`, `AMAZON_DYNAMODB`, `AMAZON_ELASTICSEARCH`, `HTTP`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing DataSource Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appsync/#DataSourceState">DataSourceState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appsync/#DataSource">DataSource</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>api_id=None<span class="p">, </span>arn=None<span class="p">, </span>description=None<span class="p">, </span>dynamodb_config=None<span class="p">, </span>elasticsearch_config=None<span class="p">, </span>http_config=None<span class="p">, </span>lambda_config=None<span class="p">, </span>name=None<span class="p">, </span>service_role_arn=None<span class="p">, </span>type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDataSource<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#DataSourceState">DataSourceState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#DataSource">DataSource</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.DataSource.html">DataSource</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.DataSourceState.html">DataSourceState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing DataSource resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dynamodb<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcedynamodbconfig">Data<wbr>Source<wbr>Dynamodb<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}DynamoDB settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elasticsearch<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourceelasticsearchconfig">Data<wbr>Source<wbr>Elasticsearch<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Amazon Elasticsearch settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcehttpconfig">Data<wbr>Source<wbr>Http<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}HTTP settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcelambdaconfig">Data<wbr>Source<wbr>Lambda<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}AWS Lambda settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM service role ARN for the data source.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the DataSource. Valid values: `AWS_LAMBDA`, `AMAZON_DYNAMODB`, `AMAZON_ELASTICSEARCH`, `HTTP`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A description of the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dynamodb<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcedynamodbconfig">*Data<wbr>Source<wbr>Dynamodb<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}DynamoDB settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elasticsearch<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourceelasticsearchconfig">*Data<wbr>Source<wbr>Elasticsearch<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Amazon Elasticsearch settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcehttpconfig">*Data<wbr>Source<wbr>Http<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}HTTP settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcelambdaconfig">*Data<wbr>Source<wbr>Lambda<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}AWS Lambda settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM service role ARN for the data source.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the DataSource. Valid values: `AWS_LAMBDA`, `AMAZON_DYNAMODB`, `AMAZON_ELASTICSEARCH`, `HTTP`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dynamodb<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcedynamodbconfig">Data<wbr>Source<wbr>Dynamodb<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}DynamoDB settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elasticsearch<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourceelasticsearchconfig">Data<wbr>Source<wbr>Elasticsearch<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Amazon Elasticsearch settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcehttpconfig">Data<wbr>Source<wbr>Http<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}HTTP settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcelambdaconfig">Data<wbr>Source<wbr>Lambda<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}AWS Lambda settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM service role ARN for the data source.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the DataSource. Valid values: `AWS_LAMBDA`, `AMAZON_DYNAMODB`, `AMAZON_ELASTICSEARCH`, `HTTP`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">api_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A description of the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dynamodb_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcedynamodbconfig">Dict[Data<wbr>Source<wbr>Dynamodb<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}DynamoDB settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elasticsearch_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourceelasticsearchconfig">Dict[Data<wbr>Source<wbr>Elasticsearch<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Amazon Elasticsearch settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcehttpconfig">Dict[Data<wbr>Source<wbr>Http<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}HTTP settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#datasourcelambdaconfig">Dict[Data<wbr>Source<wbr>Lambda<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}AWS Lambda settings. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the DataSource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM service role ARN for the data source.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the DataSource. Valid values: `AWS_LAMBDA`, `AMAZON_DYNAMODB`, `AMAZON_ELASTICSEARCH`, `HTTP`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### DataSourceDynamodbConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DataSourceDynamodbConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DataSourceDynamodbConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#DataSourceDynamodbConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#DataSourceDynamodbConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.DataSourceDynamodbConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.DataSourceDynamodbConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}AWS region of Elasticsearch domain. Defaults to current region.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Table<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the DynamoDB table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Caller<wbr>Credentials<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Set to `true` to use Amazon Cognito credentials with this data source.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Region<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}AWS region of Elasticsearch domain. Defaults to current region.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Table<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the DynamoDB table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Caller<wbr>Credentials<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Set to `true` to use Amazon Cognito credentials with this data source.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}AWS region of Elasticsearch domain. Defaults to current region.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">table<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the DynamoDB table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use<wbr>Caller<wbr>Credentials<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Set to `true` to use Amazon Cognito credentials with this data source.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}AWS region of Elasticsearch domain. Defaults to current region.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">table_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the DynamoDB table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use<wbr>Caller<wbr>Credentials<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Set to `true` to use Amazon Cognito credentials with this data source.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DataSourceElasticsearchConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DataSourceElasticsearchConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DataSourceElasticsearchConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#DataSourceElasticsearchConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#DataSourceElasticsearchConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.DataSourceElasticsearchConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.DataSourceElasticsearchConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}HTTP URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}AWS region of Elasticsearch domain. Defaults to current region.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}HTTP URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Region<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}AWS region of Elasticsearch domain. Defaults to current region.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}HTTP URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}AWS region of Elasticsearch domain. Defaults to current region.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}HTTP URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}AWS region of Elasticsearch domain. Defaults to current region.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DataSourceHttpConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DataSourceHttpConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DataSourceHttpConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#DataSourceHttpConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#DataSourceHttpConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.DataSourceHttpConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.DataSourceHttpConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}HTTP URL.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}HTTP URL.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}HTTP URL.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}HTTP URL.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DataSourceLambdaConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DataSourceLambdaConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DataSourceLambdaConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#DataSourceLambdaConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#DataSourceLambdaConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.DataSourceLambdaConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.DataSourceLambdaConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Function<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Function<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">function<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">function_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








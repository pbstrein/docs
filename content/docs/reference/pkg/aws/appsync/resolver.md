
---
title: "Resolver"
block_external_search_index: true
---

Provides an AppSync Resolver.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const testGraphQLApi = new aws.appsync.GraphQLApi("test", {
    authenticationType: "API_KEY",
    schema: `type Mutation {
	putPost(id: ID!, title: String!): Post
}

type Post {
	id: ID!
	title: String!
}

type Query {
	singlePost(id: ID!): Post
}

schema {
	query: Query
	mutation: Mutation
}
`,
});
const testDataSource = new aws.appsync.DataSource("test", {
    apiId: testGraphQLApi.id,
    httpConfig: {
        endpoint: "http://example.com",
    },
    type: "HTTP",
});
// UNIT type resolver (default)
const testResolver = new aws.appsync.Resolver("test", {
    apiId: testGraphQLApi.id,
    dataSource: testDataSource.name,
    field: "singlePost",
    requestTemplate: `{
    "version": "2018-05-29",
    "method": "GET",
    "resourcePath": "/",
    "params":{
        "headers": $utils.http.copyheaders($ctx.request.headers)
    }
}
`,
    responseTemplate: `#if($ctx.result.statusCode == 200)
    $ctx.result.body
#else
    $utils.appendError($ctx.result.body, $ctx.result.statusCode)
#end
`,
    type: "Query",
});
// PIPELINE type resolver
const mutationPipelineTest = new aws.appsync.Resolver("Mutation_pipelineTest", {
    apiId: testGraphQLApi.id,
    field: "pipelineTest",
    kind: "PIPELINE",
    pipelineConfig: {
        functions: [
            aws_appsync_function_test1.functionId,
            aws_appsync_function_test2.functionId,
            aws_appsync_function_test3.functionId,
        ],
    },
    requestTemplate: "{}",
    responseTemplate: "$util.toJson($ctx.result)",
    type: "Mutation",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/appsync_resolver.html.markdown.



## Create a Resolver Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appsync/#Resolver">Resolver</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appsync/#ResolverArgs">ResolverArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Resolver</span><span class="p">(resource_name, opts=None, </span>api_id=None<span class="p">, </span>data_source=None<span class="p">, </span>field=None<span class="p">, </span>kind=None<span class="p">, </span>pipeline_config=None<span class="p">, </span>request_template=None<span class="p">, </span>response_template=None<span class="p">, </span>type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewResolver<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#ResolverArgs">ResolverArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#Resolver">Resolver</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.Resolver.html">Resolver</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.ResolverArgs.html">ResolverArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
    <dd>{{% md %}}The API ID for the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DataSource name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Field<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The field name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kind<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The resolver type. Valid values are `UNIT` and `PIPELINE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pipeline<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#resolverpipelineconfig">Resolver<wbr>Pipeline<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The PipelineConfig. A `pipeline_config` block is documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Request<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The request mapping template for UNIT resolver or &#39;before mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Response<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The response mapping template for UNIT resolver or &#39;after mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The DataSource name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Field<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The field name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kind<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The resolver type. Valid values are `UNIT` and `PIPELINE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pipeline<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#resolverpipelineconfig">*Resolver<wbr>Pipeline<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The PipelineConfig. A `pipeline_config` block is documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Request<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The request mapping template for UNIT resolver or &#39;before mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Response<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The response mapping template for UNIT resolver or &#39;after mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DataSource name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">field<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The field name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kind<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The resolver type. Valid values are `UNIT` and `PIPELINE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pipeline<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#resolverpipelineconfig">Resolver<wbr>Pipeline<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The PipelineConfig. A `pipeline_config` block is documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">request<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The request mapping template for UNIT resolver or &#39;before mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">response<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The response mapping template for UNIT resolver or &#39;after mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">api_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data_<wbr>source<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DataSource name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">field<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The field name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kind<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resolver type. Valid values are `UNIT` and `PIPELINE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pipeline_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#resolverpipelineconfig">Dict[Resolver<wbr>Pipeline<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The PipelineConfig. A `pipeline_config` block is documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">request_<wbr>template<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The request mapping template for UNIT resolver or &#39;before mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">response_<wbr>template<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The response mapping template for UNIT resolver or &#39;after mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Resolver Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-"
            title="">Data<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DataSource name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Field<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The field name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kind<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The resolver type. Valid values are `UNIT` and `PIPELINE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Pipeline<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#resolverpipelineconfig">Resolver<wbr>Pipeline<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The PipelineConfig. A `pipeline_config` block is documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Request<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The request mapping template for UNIT resolver or &#39;before mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Response<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The response mapping template for UNIT resolver or &#39;after mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-"
            title="">Data<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The DataSource name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Field<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The field name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kind<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The resolver type. Valid values are `UNIT` and `PIPELINE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Pipeline<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#resolverpipelineconfig">*Resolver<wbr>Pipeline<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The PipelineConfig. A `pipeline_config` block is documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Request<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The request mapping template for UNIT resolver or &#39;before mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Response<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The response mapping template for UNIT resolver or &#39;after mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-"
            title="">data<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DataSource name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">field<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The field name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kind<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The resolver type. Valid values are `UNIT` and `PIPELINE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">pipeline<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#resolverpipelineconfig">Resolver<wbr>Pipeline<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The PipelineConfig. A `pipeline_config` block is documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">request<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The request mapping template for UNIT resolver or &#39;before mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-"
            title="">response<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The response mapping template for UNIT resolver or &#39;after mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">api_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-"
            title="">data_<wbr>source<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DataSource name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">field<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The field name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kind<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resolver type. Valid values are `UNIT` and `PIPELINE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">pipeline_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#resolverpipelineconfig">Dict[Resolver<wbr>Pipeline<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The PipelineConfig. A `pipeline_config` block is documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">request_<wbr>template<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The request mapping template for UNIT resolver or &#39;before mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-"
            title="">response_<wbr>template<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The response mapping template for UNIT resolver or &#39;after mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Resolver Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appsync/#ResolverState">ResolverState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appsync/#Resolver">Resolver</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>api_id=None<span class="p">, </span>arn=None<span class="p">, </span>data_source=None<span class="p">, </span>field=None<span class="p">, </span>kind=None<span class="p">, </span>pipeline_config=None<span class="p">, </span>request_template=None<span class="p">, </span>response_template=None<span class="p">, </span>type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetResolver<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#ResolverState">ResolverState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#Resolver">Resolver</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.Resolver.html">Resolver</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.ResolverState.html">ResolverState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Resolver resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The API ID for the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DataSource name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Field<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The field name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kind<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The resolver type. Valid values are `UNIT` and `PIPELINE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pipeline<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#resolverpipelineconfig">Resolver<wbr>Pipeline<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The PipelineConfig. A `pipeline_config` block is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The request mapping template for UNIT resolver or &#39;before mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Response<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The response mapping template for UNIT resolver or &#39;after mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The DataSource name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Field<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The field name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kind<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The resolver type. Valid values are `UNIT` and `PIPELINE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pipeline<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#resolverpipelineconfig">*Resolver<wbr>Pipeline<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The PipelineConfig. A `pipeline_config` block is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The request mapping template for UNIT resolver or &#39;before mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Response<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The response mapping template for UNIT resolver or &#39;after mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DataSource name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">field<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The field name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kind<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The resolver type. Valid values are `UNIT` and `PIPELINE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pipeline<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#resolverpipelineconfig">Resolver<wbr>Pipeline<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The PipelineConfig. A `pipeline_config` block is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The request mapping template for UNIT resolver or &#39;before mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">response<wbr>Template<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The response mapping template for UNIT resolver or &#39;after mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">api_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The API ID for the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data_<wbr>source<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DataSource name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">field<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The field name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kind<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resolver type. Valid values are `UNIT` and `PIPELINE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pipeline_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#resolverpipelineconfig">Dict[Resolver<wbr>Pipeline<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The PipelineConfig. A `pipeline_config` block is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request_<wbr>template<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The request mapping template for UNIT resolver or &#39;before mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">response_<wbr>template<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The response mapping template for UNIT resolver or &#39;after mapping template&#39; for PIPELINE resolver.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type name from the schema defined in the GraphQL API.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### ResolverPipelineConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ResolverPipelineConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ResolverPipelineConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#ResolverPipelineConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#ResolverPipelineConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.ResolverPipelineConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.ResolverPipelineConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Functions<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Functions<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">functions<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">functions<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








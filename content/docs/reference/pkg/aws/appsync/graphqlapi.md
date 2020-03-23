
---
title: "GraphQLApi"
block_external_search_index: true
---

Provides an AppSync GraphQL API.

## Example Usage

### API Key Authentication

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.appsync.GraphQLApi("example", {
    authenticationType: "API_KEY",
});
```

### AWS Cognito User Pool Authentication

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.appsync.GraphQLApi("example", {
    authenticationType: "AMAZON_COGNITO_USER_POOLS",
    userPoolConfig: {
        awsRegion: aws_region_current.name,
        defaultAction: "DENY",
        userPoolId: aws_cognito_user_pool_example.id,
    },
});
```

### AWS IAM Authentication

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.appsync.GraphQLApi("example", {
    authenticationType: "AWS_IAM",
});
```

### With Schema

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.appsync.GraphQLApi("example", {
    authenticationType: "AWS_IAM",
    schema: `schema {
	query: Query
}
type Query {
  test: Int
}
`,
});
```

### OpenID Connect Authentication

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.appsync.GraphQLApi("example", {
    authenticationType: "OPENID_CONNECT",
    openidConnectConfig: {
        issuer: "https://example.com",
    },
});
```

### With Multiple Authentication Providers

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.appsync.GraphQLApi("example", {
    additionalAuthenticationProviders: [{
        authenticationType: "AWS_IAM",
    }],
    authenticationType: "API_KEY",
});
```

### Enabling Logging

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleRole = new aws.iam.Role("example", {
    assumeRolePolicy: `{
    "Version": "2012-10-17",
    "Statement": [
        {
        "Effect": "Allow",
        "Principal": {
            "Service": "appsync.amazonaws.com"
        },
        "Action": "sts:AssumeRole"
        }
    ]
}
`,
});
const exampleRolePolicyAttachment = new aws.iam.RolePolicyAttachment("example", {
    policyArn: "arn:aws:iam::aws:policy/service-role/AWSAppSyncPushToCloudWatchLogs",
    role: exampleRole.name,
});
const exampleGraphQLApi = new aws.appsync.GraphQLApi("example", {
    logConfig: {
        cloudwatchLogsRoleArn: exampleRole.arn,
        fieldLogLevel: "ERROR",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/appsync_graphql_api.html.markdown.



## Create a GraphQLApi Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appsync/#GraphQLApi">GraphQLApi</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appsync/#GraphQLApiArgs">GraphQLApiArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">GraphQLApi</span><span class="p">(resource_name, opts=None, </span>additional_authentication_providers=None<span class="p">, </span>authentication_type=None<span class="p">, </span>log_config=None<span class="p">, </span>name=None<span class="p">, </span>openid_connect_config=None<span class="p">, </span>schema=None<span class="p">, </span>tags=None<span class="p">, </span>user_pool_config=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewGraphQLApi<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApiArgs">GraphQLApiArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApi">GraphQLApi</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApi.html">GraphQLApi</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApiArgs.html">GraphQLApiArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Additional<wbr>Authentication<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovider">List&lt;Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more additional authentication providers for the GraphqlApi. Defined below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Authentication<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapilogconfig">Graph<wbr>QLApi<wbr>Log<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing logging configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the GraphqlApi.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Openid<wbr>Connect<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiopenidconnectconfig">Graph<wbr>QLApi<wbr>Openid<wbr>Connect<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schema<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The schema definition, in GraphQL schema language format. This provider cannot perform drift detection of this configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Pool<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiuserpoolconfig">Graph<wbr>QLApi<wbr>User<wbr>Pool<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Additional<wbr>Authentication<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovider">[]Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider</a></span>
    </dt>
    <dd>{{% md %}}One or more additional authentication providers for the GraphqlApi. Defined below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Authentication<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapilogconfig">*Graph<wbr>QLApi<wbr>Log<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing logging configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the GraphqlApi.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Openid<wbr>Connect<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiopenidconnectconfig">*Graph<wbr>QLApi<wbr>Openid<wbr>Connect<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schema<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The schema definition, in GraphQL schema language format. This provider cannot perform drift detection of this configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Pool<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiuserpoolconfig">*Graph<wbr>QLApi<wbr>User<wbr>Pool<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">additional<wbr>Authentication<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovider">Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more additional authentication providers for the GraphqlApi. Defined below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">authentication<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapilogconfig">Graph<wbr>QLApi<wbr>Log<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing logging configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the GraphqlApi.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">openid<wbr>Connect<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiopenidconnectconfig">Graph<wbr>QLApi<wbr>Openid<wbr>Connect<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schema<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The schema definition, in GraphQL schema language format. This provider cannot perform drift detection of this configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<wbr>Pool<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiuserpoolconfig">Graph<wbr>QLApi<wbr>User<wbr>Pool<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">additional_<wbr>authentication_<wbr>providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovider">List[Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider]</a></span>
    </dt>
    <dd>{{% md %}}One or more additional authentication providers for the GraphqlApi. Defined below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">authentication_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapilogconfig">Dict[Graph<wbr>QLApi<wbr>Log<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing logging configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the GraphqlApi.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">openid_<wbr>connect_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiopenidconnectconfig">Dict[Graph<wbr>QLApi<wbr>Openid<wbr>Connect<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schema<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The schema definition, in GraphQL schema language format. This provider cannot perform drift detection of this configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user_<wbr>pool_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiuserpoolconfig">Dict[Graph<wbr>QLApi<wbr>User<wbr>Pool<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## GraphQLApi Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Additional<wbr>Authentication<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovider">List&lt;Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more additional authentication providers for the GraphqlApi. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-"
            title="">Authentication<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Log<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapilogconfig">Graph<wbr>QLApi<wbr>Log<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing logging configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the GraphqlApi.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Openid<wbr>Connect<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiopenidconnectconfig">Graph<wbr>QLApi<wbr>Openid<wbr>Connect<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Schema<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The schema definition, in GraphQL schema language format. This provider cannot perform drift detection of this configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Uris<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string></span>
    </dt>
    <dd>{{% md %}}Map of URIs associated with the API. e.g. `uris[&#34;GRAPHQL&#34;] = https://ID.appsync-api.REGION.amazonaws.com/graphql`
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Pool<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiuserpoolconfig">Graph<wbr>QLApi<wbr>User<wbr>Pool<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Additional<wbr>Authentication<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovider">[]Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider</a></span>
    </dt>
    <dd>{{% md %}}One or more additional authentication providers for the GraphqlApi. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-"
            title="">Authentication<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Log<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapilogconfig">*Graph<wbr>QLApi<wbr>Log<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing logging configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the GraphqlApi.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Openid<wbr>Connect<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiopenidconnectconfig">*Graph<wbr>QLApi<wbr>Openid<wbr>Connect<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Schema<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The schema definition, in GraphQL schema language format. This provider cannot perform drift detection of this configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Uris<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}Map of URIs associated with the API. e.g. `uris[&#34;GRAPHQL&#34;] = https://ID.appsync-api.REGION.amazonaws.com/graphql`
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Pool<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiuserpoolconfig">*Graph<wbr>QLApi<wbr>User<wbr>Pool<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">additional<wbr>Authentication<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovider">Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more additional authentication providers for the GraphqlApi. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-"
            title="">authentication<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-"
            title="">log<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapilogconfig">Graph<wbr>QLApi<wbr>Log<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing logging configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the GraphqlApi.
{{% /md %}}</dd>

    <dt class="property-"
            title="">openid<wbr>Connect<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiopenidconnectconfig">Graph<wbr>QLApi<wbr>Openid<wbr>Connect<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">schema<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The schema definition, in GraphQL schema language format. This provider cannot perform drift detection of this configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">uris<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}</span>
    </dt>
    <dd>{{% md %}}Map of URIs associated with the API. e.g. `uris[&#34;GRAPHQL&#34;] = https://ID.appsync-api.REGION.amazonaws.com/graphql`
{{% /md %}}</dd>

    <dt class="property-"
            title="">user<wbr>Pool<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiuserpoolconfig">Graph<wbr>QLApi<wbr>User<wbr>Pool<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">additional_<wbr>authentication_<wbr>providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovider">List[Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider]</a></span>
    </dt>
    <dd>{{% md %}}One or more additional authentication providers for the GraphqlApi. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-"
            title="">authentication_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-"
            title="">log_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapilogconfig">Dict[Graph<wbr>QLApi<wbr>Log<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing logging configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the GraphqlApi.
{{% /md %}}</dd>

    <dt class="property-"
            title="">openid_<wbr>connect_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiopenidconnectconfig">Dict[Graph<wbr>QLApi<wbr>Openid<wbr>Connect<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">schema<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The schema definition, in GraphQL schema language format. This provider cannot perform drift detection of this configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">uris<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}Map of URIs associated with the API. e.g. `uris[&#34;GRAPHQL&#34;] = https://ID.appsync-api.REGION.amazonaws.com/graphql`
{{% /md %}}</dd>

    <dt class="property-"
            title="">user_<wbr>pool_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiuserpoolconfig">Dict[Graph<wbr>QLApi<wbr>User<wbr>Pool<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing GraphQLApi Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appsync/#GraphQLApiState">GraphQLApiState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appsync/#GraphQLApi">GraphQLApi</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>additional_authentication_providers=None<span class="p">, </span>arn=None<span class="p">, </span>authentication_type=None<span class="p">, </span>log_config=None<span class="p">, </span>name=None<span class="p">, </span>openid_connect_config=None<span class="p">, </span>schema=None<span class="p">, </span>tags=None<span class="p">, </span>uris=None<span class="p">, </span>user_pool_config=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetGraphQLApi<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApiState">GraphQLApiState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApi">GraphQLApi</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApi.html">GraphQLApi</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApiState.html">GraphQLApiState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing GraphQLApi resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Additional<wbr>Authentication<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovider">List&lt;Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more additional authentication providers for the GraphqlApi. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authentication<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapilogconfig">Graph<wbr>QLApi<wbr>Log<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing logging configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the GraphqlApi.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Openid<wbr>Connect<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiopenidconnectconfig">Graph<wbr>QLApi<wbr>Openid<wbr>Connect<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schema<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The schema definition, in GraphQL schema language format. This provider cannot perform drift detection of this configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Uris<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}Map of URIs associated with the API. e.g. `uris[&#34;GRAPHQL&#34;] = https://ID.appsync-api.REGION.amazonaws.com/graphql`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Pool<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiuserpoolconfig">Graph<wbr>QLApi<wbr>User<wbr>Pool<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Additional<wbr>Authentication<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovider">[]Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider</a></span>
    </dt>
    <dd>{{% md %}}One or more additional authentication providers for the GraphqlApi. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authentication<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapilogconfig">*Graph<wbr>QLApi<wbr>Log<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing logging configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the GraphqlApi.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Openid<wbr>Connect<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiopenidconnectconfig">*Graph<wbr>QLApi<wbr>Openid<wbr>Connect<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schema<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The schema definition, in GraphQL schema language format. This provider cannot perform drift detection of this configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Uris<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}Map of URIs associated with the API. e.g. `uris[&#34;GRAPHQL&#34;] = https://ID.appsync-api.REGION.amazonaws.com/graphql`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Pool<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiuserpoolconfig">*Graph<wbr>QLApi<wbr>User<wbr>Pool<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">additional<wbr>Authentication<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovider">Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more additional authentication providers for the GraphqlApi. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authentication<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapilogconfig">Graph<wbr>QLApi<wbr>Log<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing logging configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the GraphqlApi.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">openid<wbr>Connect<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiopenidconnectconfig">Graph<wbr>QLApi<wbr>Openid<wbr>Connect<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schema<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The schema definition, in GraphQL schema language format. This provider cannot perform drift detection of this configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">uris<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}Map of URIs associated with the API. e.g. `uris[&#34;GRAPHQL&#34;] = https://ID.appsync-api.REGION.amazonaws.com/graphql`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<wbr>Pool<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiuserpoolconfig">Graph<wbr>QLApi<wbr>User<wbr>Pool<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">additional_<wbr>authentication_<wbr>providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovider">List[Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider]</a></span>
    </dt>
    <dd>{{% md %}}One or more additional authentication providers for the GraphqlApi. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authentication_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapilogconfig">Dict[Graph<wbr>QLApi<wbr>Log<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing logging configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A user-supplied name for the GraphqlApi.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">openid_<wbr>connect_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiopenidconnectconfig">Dict[Graph<wbr>QLApi<wbr>Openid<wbr>Connect<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schema<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The schema definition, in GraphQL schema language format. This provider cannot perform drift detection of this configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">uris<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}Map of URIs associated with the API. e.g. `uris[&#34;GRAPHQL&#34;] = https://ID.appsync-api.REGION.amazonaws.com/graphql`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user_<wbr>pool_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiuserpoolconfig">Dict[Graph<wbr>QLApi<wbr>User<wbr>Pool<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### GraphQLApiAdditionalAuthenticationProvider
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#GraphQLApiAdditionalAuthenticationProvider">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GraphQLApiAdditionalAuthenticationProvider">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApiAdditionalAuthenticationProviderArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApiAdditionalAuthenticationProviderOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApiAdditionalAuthenticationProviderArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApiAdditionalAuthenticationProvider.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Authentication<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Openid<wbr>Connect<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovideropenidconnectconfig">Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider<wbr>Openid<wbr>Connect<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Pool<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovideruserpoolconfig">Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider<wbr>User<wbr>Pool<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Authentication<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Openid<wbr>Connect<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovideropenidconnectconfig">*Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider<wbr>Openid<wbr>Connect<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Pool<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovideruserpoolconfig">*Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider<wbr>User<wbr>Pool<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">authentication<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">openid<wbr>Connect<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovideropenidconnectconfig">Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider<wbr>Openid<wbr>Connect<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<wbr>Pool<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovideruserpoolconfig">Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider<wbr>User<wbr>Pool<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">authentication_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The authentication type. Valid values: `API_KEY`, `AWS_IAM`, `AMAZON_COGNITO_USER_POOLS`, `OPENID_CONNECT`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">openid_<wbr>connect_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovideropenidconnectconfig">Dict[Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider<wbr>Openid<wbr>Connect<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing OpenID Connect configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user_<wbr>pool_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#graphqlapiadditionalauthenticationprovideruserpoolconfig">Dict[Graph<wbr>QLApi<wbr>Additional<wbr>Authentication<wbr>Provider<wbr>User<wbr>Pool<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Cognito User Pool configuration. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GraphQLApiAdditionalAuthenticationProviderOpenidConnectConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#GraphQLApiAdditionalAuthenticationProviderOpenidConnectConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GraphQLApiAdditionalAuthenticationProviderOpenidConnectConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApiAdditionalAuthenticationProviderOpenidConnectConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApiAdditionalAuthenticationProviderOpenidConnectConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApiAdditionalAuthenticationProviderOpenidConnectConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApiAdditionalAuthenticationProviderOpenidConnectConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Auth<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being authenticated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Client identifier of the Relying party at the OpenID identity provider. This identifier is typically obtained when the Relying party is registered with the OpenID identity provider. You can specify a regular expression so the AWS AppSync can validate against multiple client identifiers at a time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iat<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being issued to a user.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Issuer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Issuer for the OpenID Connect configuration. The issuer returned by discovery MUST exactly match the value of iss in the ID Token.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Auth<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being authenticated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Client identifier of the Relying party at the OpenID identity provider. This identifier is typically obtained when the Relying party is registered with the OpenID identity provider. You can specify a regular expression so the AWS AppSync can validate against multiple client identifiers at a time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iat<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being issued to a user.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Issuer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Issuer for the OpenID Connect configuration. The issuer returned by discovery MUST exactly match the value of iss in the ID Token.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">auth<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being authenticated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Client identifier of the Relying party at the OpenID identity provider. This identifier is typically obtained when the Relying party is registered with the OpenID identity provider. You can specify a regular expression so the AWS AppSync can validate against multiple client identifiers at a time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iat<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being issued to a user.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">issuer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Issuer for the OpenID Connect configuration. The issuer returned by discovery MUST exactly match the value of iss in the ID Token.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">auth<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being authenticated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Client identifier of the Relying party at the OpenID identity provider. This identifier is typically obtained when the Relying party is registered with the OpenID identity provider. You can specify a regular expression so the AWS AppSync can validate against multiple client identifiers at a time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iat<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being issued to a user.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">issuer<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Issuer for the OpenID Connect configuration. The issuer returned by discovery MUST exactly match the value of iss in the ID Token.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GraphQLApiAdditionalAuthenticationProviderUserPoolConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#GraphQLApiAdditionalAuthenticationProviderUserPoolConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GraphQLApiAdditionalAuthenticationProviderUserPoolConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApiAdditionalAuthenticationProviderUserPoolConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApiAdditionalAuthenticationProviderUserPoolConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApiAdditionalAuthenticationProviderUserPoolConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApiAdditionalAuthenticationProviderUserPoolConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">App<wbr>Id<wbr>Client<wbr>Regex<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A regular expression for validating the incoming Amazon Cognito User Pool app client ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS region in which the user pool was created.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user pool ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">App<wbr>Id<wbr>Client<wbr>Regex<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A regular expression for validating the incoming Amazon Cognito User Pool app client ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS region in which the user pool was created.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user pool ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">app<wbr>Id<wbr>Client<wbr>Regex<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A regular expression for validating the incoming Amazon Cognito User Pool app client ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS region in which the user pool was created.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user pool ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">app<wbr>Id<wbr>Client<wbr>Regex<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A regular expression for validating the incoming Amazon Cognito User Pool app client ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS region in which the user pool was created.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user_<wbr>pool_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The user pool ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GraphQLApiLogConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#GraphQLApiLogConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GraphQLApiLogConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApiLogConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApiLogConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApiLogConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApiLogConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cloudwatch<wbr>Logs<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the service role that AWS AppSync will assume to publish to Amazon CloudWatch logs in your account.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Field<wbr>Log<wbr>Level<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Field logging level. Valid values: `ALL`, `ERROR`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cloudwatch<wbr>Logs<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the service role that AWS AppSync will assume to publish to Amazon CloudWatch logs in your account.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Field<wbr>Log<wbr>Level<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Field logging level. Valid values: `ALL`, `ERROR`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cloudwatch<wbr>Logs<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the service role that AWS AppSync will assume to publish to Amazon CloudWatch logs in your account.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">field<wbr>Log<wbr>Level<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Field logging level. Valid values: `ALL`, `ERROR`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cloudwatch<wbr>Logs<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the service role that AWS AppSync will assume to publish to Amazon CloudWatch logs in your account.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">field<wbr>Log<wbr>Level<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Field logging level. Valid values: `ALL`, `ERROR`, `NONE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GraphQLApiOpenidConnectConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#GraphQLApiOpenidConnectConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GraphQLApiOpenidConnectConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApiOpenidConnectConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApiOpenidConnectConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApiOpenidConnectConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApiOpenidConnectConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Auth<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being authenticated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Client identifier of the Relying party at the OpenID identity provider. This identifier is typically obtained when the Relying party is registered with the OpenID identity provider. You can specify a regular expression so the AWS AppSync can validate against multiple client identifiers at a time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iat<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being issued to a user.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Issuer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Issuer for the OpenID Connect configuration. The issuer returned by discovery MUST exactly match the value of iss in the ID Token.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Auth<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being authenticated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Client identifier of the Relying party at the OpenID identity provider. This identifier is typically obtained when the Relying party is registered with the OpenID identity provider. You can specify a regular expression so the AWS AppSync can validate against multiple client identifiers at a time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iat<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being issued to a user.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Issuer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Issuer for the OpenID Connect configuration. The issuer returned by discovery MUST exactly match the value of iss in the ID Token.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">auth<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being authenticated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Client identifier of the Relying party at the OpenID identity provider. This identifier is typically obtained when the Relying party is registered with the OpenID identity provider. You can specify a regular expression so the AWS AppSync can validate against multiple client identifiers at a time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iat<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being issued to a user.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">issuer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Issuer for the OpenID Connect configuration. The issuer returned by discovery MUST exactly match the value of iss in the ID Token.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">auth<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being authenticated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Client identifier of the Relying party at the OpenID identity provider. This identifier is typically obtained when the Relying party is registered with the OpenID identity provider. You can specify a regular expression so the AWS AppSync can validate against multiple client identifiers at a time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iat<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Number of milliseconds a token is valid after being issued to a user.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">issuer<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Issuer for the OpenID Connect configuration. The issuer returned by discovery MUST exactly match the value of iss in the ID Token.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GraphQLApiUserPoolConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#GraphQLApiUserPoolConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GraphQLApiUserPoolConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApiUserPoolConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appsync?tab=doc#GraphQLApiUserPoolConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApiUserPoolConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appsync.GraphQLApiUserPoolConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">App<wbr>Id<wbr>Client<wbr>Regex<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A regular expression for validating the incoming Amazon Cognito User Pool app client ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS region in which the user pool was created.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Default<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The action that you want your GraphQL API to take when a request that uses Amazon Cognito User Pool authentication doesn&#39;t match the Amazon Cognito User Pool configuration. Valid: `ALLOW` and `DENY`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user pool ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">App<wbr>Id<wbr>Client<wbr>Regex<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A regular expression for validating the incoming Amazon Cognito User Pool app client ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS region in which the user pool was created.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Default<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The action that you want your GraphQL API to take when a request that uses Amazon Cognito User Pool authentication doesn&#39;t match the Amazon Cognito User Pool configuration. Valid: `ALLOW` and `DENY`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user pool ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">app<wbr>Id<wbr>Client<wbr>Regex<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A regular expression for validating the incoming Amazon Cognito User Pool app client ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS region in which the user pool was created.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">default<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The action that you want your GraphQL API to take when a request that uses Amazon Cognito User Pool authentication doesn&#39;t match the Amazon Cognito User Pool configuration. Valid: `ALLOW` and `DENY`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user pool ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">app<wbr>Id<wbr>Client<wbr>Regex<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A regular expression for validating the incoming Amazon Cognito User Pool app client ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS region in which the user pool was created.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">default_<wbr>action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The action that you want your GraphQL API to take when a request that uses Amazon Cognito User Pool authentication doesn&#39;t match the Amazon Cognito User Pool configuration. Valid: `ALLOW` and `DENY`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user_<wbr>pool_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The user pool ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}









---
title: "Integration"
block_external_search_index: true
---

Provides an HTTP Method Integration for an API Gateway Integration.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const myDemoAPI = new aws.apigateway.RestApi("MyDemoAPI", {
    description: "This is my API for demonstration purposes",
});
const myDemoResource = new aws.apigateway.Resource("MyDemoResource", {
    parentId: myDemoAPI.rootResourceId,
    pathPart: "mydemoresource",
    restApi: myDemoAPI.id,
});
const myDemoMethod = new aws.apigateway.Method("MyDemoMethod", {
    authorization: "NONE",
    httpMethod: "GET",
    resourceId: myDemoResource.id,
    restApi: myDemoAPI.id,
});
const myDemoIntegration = new aws.apigateway.Integration("MyDemoIntegration", {
    cacheKeyParameters: ["method.request.path.param"],
    cacheNamespace: "foobar",
    httpMethod: myDemoMethod.httpMethod,
    requestParameters: {
        "integration.request.header.X-Authorization": "'static'",
    },
    // Transforms the incoming XML request to JSON
    requestTemplates: {
        "application/xml": `{
   "body" : $input.json('$')
}
`,
    },
    resourceId: myDemoResource.id,
    restApi: myDemoAPI.id,
    timeoutMilliseconds: 29000,
    type: "MOCK",
});
```

## Lambda integration

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const config = new pulumi.Config();
// Variables
const myregion = config.require("myregion");
const accountId = config.require("accountId");

// API Gateway
const api = new aws.apigateway.RestApi("api", {});
const resource = new aws.apigateway.Resource("resource", {
    parentId: api.rootResourceId,
    pathPart: "resource",
    restApi: api.id,
});
const method = new aws.apigateway.Method("method", {
    authorization: "NONE",
    httpMethod: "GET",
    resourceId: resource.id,
    restApi: api.id,
});
// IAM
const role = new aws.iam.Role("role", {
    assumeRolePolicy: `{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": "sts:AssumeRole",
      "Principal": {
        "Service": "lambda.amazonaws.com"
      },
      "Effect": "Allow",
      "Sid": ""
    }
  ]
}
`,
});
const lambda = new aws.lambda.Function("lambda", {
    code: new pulumi.asset.FileArchive("lambda.zip"),
    handler: "lambda.lambda_handler",
    role: role.arn,
    runtime: "python2.7",
});
const integration = new aws.apigateway.Integration("integration", {
    httpMethod: method.httpMethod,
    integrationHttpMethod: "POST",
    resourceId: resource.id,
    restApi: api.id,
    type: "AWS_PROXY",
    uri: lambda.invokeArn,
});
// Lambda
const apigwLambda = new aws.lambda.Permission("apigw_lambda", {
    action: "lambda:InvokeFunction",
    function: lambda.functionName,
    principal: "apigateway.amazonaws.com",
    sourceArn: pulumi.interpolate`arn:aws:execute-api:${myregion}:${accountId}:${api.id}/*/${method.httpMethod}${resource.path}`,
});
```

## VPC Link

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const config = new pulumi.Config();
const name = config.require("name");
const subnetId = config.require("subnetId");

const testLoadBalancer = new aws.lb.LoadBalancer("test", {
    internal: true,
    loadBalancerType: "network",
    subnets: [subnetId],
});
const testVpcLink = new aws.apigateway.VpcLink("test", {
    targetArn: testLoadBalancer.arn,
});
const testRestApi = new aws.apigateway.RestApi("test", {});
const testResource = new aws.apigateway.Resource("test", {
    parentId: testRestApi.rootResourceId,
    pathPart: "test",
    restApi: testRestApi.id,
});
const testMethod = new aws.apigateway.Method("test", {
    authorization: "NONE",
    httpMethod: "GET",
    requestModels: {
        "application/json": "Error",
    },
    resourceId: testResource.id,
    restApi: testRestApi.id,
});
const testIntegration = new aws.apigateway.Integration("test", {
    connectionId: testVpcLink.id,
    connectionType: "VPC_LINK",
    contentHandling: "CONVERT_TO_TEXT",
    httpMethod: testMethod.httpMethod,
    integrationHttpMethod: "GET",
    passthroughBehavior: "WHEN_NO_MATCH",
    requestParameters: {
        "integration.request.header.X-Authorization": "'static'",
        "integration.request.header.X-Foo": "'Bar'",
    },
    requestTemplates: {
        "application/json": "",
        "application/xml": `#set($inputRoot = $input.path('$'))
{ }`,
    },
    resourceId: testResource.id,
    restApi: testRestApi.id,
    type: "HTTP",
    uri: "https://www.google.de",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/api_gateway_integration.html.markdown.



## Create a Integration Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#Integration">Integration</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#IntegrationArgs">IntegrationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Integration</span><span class="p">(resource_name, opts=None, </span>cache_key_parameters=None<span class="p">, </span>cache_namespace=None<span class="p">, </span>connection_id=None<span class="p">, </span>connection_type=None<span class="p">, </span>content_handling=None<span class="p">, </span>credentials=None<span class="p">, </span>http_method=None<span class="p">, </span>integration_http_method=None<span class="p">, </span>passthrough_behavior=None<span class="p">, </span>request_parameters=None<span class="p">, </span>request_templates=None<span class="p">, </span>resource_id=None<span class="p">, </span>rest_api=None<span class="p">, </span>timeout_milliseconds=None<span class="p">, </span>type=None<span class="p">, </span>uri=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewIntegration<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#IntegrationArgs">IntegrationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#Integration">Integration</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.Integration.html">Integration</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.IntegrationArgs.html">IntegrationArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Cache<wbr>Key<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of cache key parameters for the integration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Namespace<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration&#39;s cache namespace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the VpcLink used for the integration. **Required** if `connection_type` is `VPC_LINK`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [connectionType](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/#connectionType). Valid values are `INTERNET` (default for connections through the public routable internet), and `VPC_LINK` (for private connections between API Gateway and a network load balancer in a VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Handling<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies how to handle request payload content type conversions. Supported values are `CONVERT_TO_BINARY` and `CONVERT_TO_TEXT`. If this property is not defined, the request payload will be passed through from the method request to integration request without modification, provided that the passthroughBehaviors is configured to support payload pass-through.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Credentials<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The credentials required for the integration. For `AWS` integrations, 2 options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role&#39;s ARN. To require that the caller&#39;s identity be passed through from the request, specify the string `arn:aws:iam::\*:user/\*`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTP method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTION`, `ANY`)
when calling the associated resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Integration<wbr>Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration HTTP method
(`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONs`, `ANY`, `PATCH`) specifying how API Gateway will interact with the back end.
**Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
Not all methods are compatible with all `AWS` integrations.
e.g. Lambda function [can only be invoked](https://github.com/awslabs/aws-apigateway-importer/issues/9#issuecomment-129651005) via `POST`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Passthrough<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration passthrough behavior (`WHEN_NO_MATCH`, `WHEN_NO_TEMPLATES`, `NEVER`).  **Required** if `request_templates` is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of request query string parameters and headers that should be passed to the backend responder.
For example: `request_parameters = { &#34;integration.request.header.X-Some-Other-Header&#34; = &#34;method.request.header.X-Some-Header&#34; }`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Templates<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of the integration&#39;s request templates.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API resource ID.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<wbr>Milliseconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Custom timeout between 50 and 29,000 milliseconds. The default value is 29,000 milliseconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [type](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/). Valid values are `HTTP` (for HTTP backends), `MOCK` (not calling any real backend), `AWS` (for AWS services), `AWS_PROXY` (for Lambda proxy integration) and `HTTP_PROXY` (for HTTP proxy integration). An `HTTP` or `HTTP_PROXY` integration with a `connection_type` of `VPC_LINK` is referred to as a private integration and uses a VpcLink to connect API Gateway to a network load balancer of a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The input&#39;s URI. **Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the RFC-3986 specification . For AWS integrations, the URI should be of the form `arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`. `region`, `subdomain` and `service` are used to determine the right endpoint.
e.g. `arn:aws:apigateway:eu-west-1:lambda:path/2015-03-31/functions/arn:aws:lambda:eu-west-1:012345678901:function:my-func/invocations`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cache<wbr>Key<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of cache key parameters for the integration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Namespace<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The integration&#39;s cache namespace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The id of the VpcLink used for the integration. **Required** if `connection_type` is `VPC_LINK`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [connectionType](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/#connectionType). Valid values are `INTERNET` (default for connections through the public routable internet), and `VPC_LINK` (for private connections between API Gateway and a network load balancer in a VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Handling<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies how to handle request payload content type conversions. Supported values are `CONVERT_TO_BINARY` and `CONVERT_TO_TEXT`. If this property is not defined, the request payload will be passed through from the method request to integration request without modification, provided that the passthroughBehaviors is configured to support payload pass-through.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Credentials<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The credentials required for the integration. For `AWS` integrations, 2 options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role&#39;s ARN. To require that the caller&#39;s identity be passed through from the request, specify the string `arn:aws:iam::\*:user/\*`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTP method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTION`, `ANY`)
when calling the associated resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Integration<wbr>Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The integration HTTP method
(`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONs`, `ANY`, `PATCH`) specifying how API Gateway will interact with the back end.
**Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
Not all methods are compatible with all `AWS` integrations.
e.g. Lambda function [can only be invoked](https://github.com/awslabs/aws-apigateway-importer/issues/9#issuecomment-129651005) via `POST`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Passthrough<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The integration passthrough behavior (`WHEN_NO_MATCH`, `WHEN_NO_TEMPLATES`, `NEVER`).  **Required** if `request_templates` is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of request query string parameters and headers that should be passed to the backend responder.
For example: `request_parameters = { &#34;integration.request.header.X-Some-Other-Header&#34; = &#34;method.request.header.X-Some-Header&#34; }`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Templates<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of the integration&#39;s request templates.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API resource ID.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<wbr>Milliseconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Custom timeout between 50 and 29,000 milliseconds. The default value is 29,000 milliseconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [type](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/). Valid values are `HTTP` (for HTTP backends), `MOCK` (not calling any real backend), `AWS` (for AWS services), `AWS_PROXY` (for Lambda proxy integration) and `HTTP_PROXY` (for HTTP proxy integration). An `HTTP` or `HTTP_PROXY` integration with a `connection_type` of `VPC_LINK` is referred to as a private integration and uses a VpcLink to connect API Gateway to a network load balancer of a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Uri<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The input&#39;s URI. **Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the RFC-3986 specification . For AWS integrations, the URI should be of the form `arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`. `region`, `subdomain` and `service` are used to determine the right endpoint.
e.g. `arn:aws:apigateway:eu-west-1:lambda:path/2015-03-31/functions/arn:aws:lambda:eu-west-1:012345678901:function:my-func/invocations`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cache<wbr>Key<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of cache key parameters for the integration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache<wbr>Namespace<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration&#39;s cache namespace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the VpcLink used for the integration. **Required** if `connection_type` is `VPC_LINK`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [connectionType](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/#connectionType). Valid values are `INTERNET` (default for connections through the public routable internet), and `VPC_LINK` (for private connections between API Gateway and a network load balancer in a VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Handling<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies how to handle request payload content type conversions. Supported values are `CONVERT_TO_BINARY` and `CONVERT_TO_TEXT`. If this property is not defined, the request payload will be passed through from the method request to integration request without modification, provided that the passthroughBehaviors is configured to support payload pass-through.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">credentials<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The credentials required for the integration. For `AWS` integrations, 2 options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role&#39;s ARN. To require that the caller&#39;s identity be passed through from the request, specify the string `arn:aws:iam::\*:user/\*`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTP method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTION`, `ANY`)
when calling the associated resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">integration<wbr>Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration HTTP method
(`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONs`, `ANY`, `PATCH`) specifying how API Gateway will interact with the back end.
**Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
Not all methods are compatible with all `AWS` integrations.
e.g. Lambda function [can only be invoked](https://github.com/awslabs/aws-apigateway-importer/issues/9#issuecomment-129651005) via `POST`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">passthrough<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration passthrough behavior (`WHEN_NO_MATCH`, `WHEN_NO_TEMPLATES`, `NEVER`).  **Required** if `request_templates` is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of request query string parameters and headers that should be passed to the backend responder.
For example: `request_parameters = { &#34;integration.request.header.X-Some-Other-Header&#34; = &#34;method.request.header.X-Some-Header&#34; }`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request<wbr>Templates<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of the integration&#39;s request templates.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API resource ID.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string | RestApi</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<wbr>Milliseconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Custom timeout between 50 and 29,000 milliseconds. The default value is 29,000 milliseconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [type](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/). Valid values are `HTTP` (for HTTP backends), `MOCK` (not calling any real backend), `AWS` (for AWS services), `AWS_PROXY` (for Lambda proxy integration) and `HTTP_PROXY` (for HTTP proxy integration). An `HTTP` or `HTTP_PROXY` integration with a `connection_type` of `VPC_LINK` is referred to as a private integration and uses a VpcLink to connect API Gateway to a network load balancer of a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The input&#39;s URI. **Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the RFC-3986 specification . For AWS integrations, the URI should be of the form `arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`. `region`, `subdomain` and `service` are used to determine the right endpoint.
e.g. `arn:aws:apigateway:eu-west-1:lambda:path/2015-03-31/functions/arn:aws:lambda:eu-west-1:012345678901:function:my-func/invocations`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cache_<wbr>key_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of cache key parameters for the integration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache_<wbr>namespace<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The integration&#39;s cache namespace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the VpcLink used for the integration. **Required** if `connection_type` is `VPC_LINK`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [connectionType](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/#connectionType). Valid values are `INTERNET` (default for connections through the public routable internet), and `VPC_LINK` (for private connections between API Gateway and a network load balancer in a VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>handling<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies how to handle request payload content type conversions. Supported values are `CONVERT_TO_BINARY` and `CONVERT_TO_TEXT`. If this property is not defined, the request payload will be passed through from the method request to integration request without modification, provided that the passthroughBehaviors is configured to support payload pass-through.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">credentials<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The credentials required for the integration. For `AWS` integrations, 2 options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role&#39;s ARN. To require that the caller&#39;s identity be passed through from the request, specify the string `arn:aws:iam::\*:user/\*`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">http_<wbr>method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The HTTP method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTION`, `ANY`)
when calling the associated resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">integration_<wbr>http_<wbr>method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The integration HTTP method
(`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONs`, `ANY`, `PATCH`) specifying how API Gateway will interact with the back end.
**Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
Not all methods are compatible with all `AWS` integrations.
e.g. Lambda function [can only be invoked](https://github.com/awslabs/aws-apigateway-importer/issues/9#issuecomment-129651005) via `POST`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">passthrough_<wbr>behavior<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The integration passthrough behavior (`WHEN_NO_MATCH`, `WHEN_NO_TEMPLATES`, `NEVER`).  **Required** if `request_templates` is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of request query string parameters and headers that should be passed to the backend responder.
For example: `request_parameters = { &#34;integration.request.header.X-Some-Other-Header&#34; = &#34;method.request.header.X-Some-Header&#34; }`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request_<wbr>templates<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of the integration&#39;s request templates.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">resource_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The API resource ID.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rest_<wbr>api<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout_<wbr>milliseconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Custom timeout between 50 and 29,000 milliseconds. The default value is 29,000 milliseconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [type](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/). Valid values are `HTTP` (for HTTP backends), `MOCK` (not calling any real backend), `AWS` (for AWS services), `AWS_PROXY` (for Lambda proxy integration) and `HTTP_PROXY` (for HTTP proxy integration). An `HTTP` or `HTTP_PROXY` integration with a `connection_type` of `VPC_LINK` is referred to as a private integration and uses a VpcLink to connect API Gateway to a network load balancer of a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">uri<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The input&#39;s URI. **Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the RFC-3986 specification . For AWS integrations, the URI should be of the form `arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`. `region`, `subdomain` and `service` are used to determine the right endpoint.
e.g. `arn:aws:apigateway:eu-west-1:lambda:path/2015-03-31/functions/arn:aws:lambda:eu-west-1:012345678901:function:my-func/invocations`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Integration Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Cache<wbr>Key<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of cache key parameters for the integration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cache<wbr>Namespace<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The integration&#39;s cache namespace.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the VpcLink used for the integration. **Required** if `connection_type` is `VPC_LINK`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [connectionType](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/#connectionType). Valid values are `INTERNET` (default for connections through the public routable internet), and `VPC_LINK` (for private connections between API Gateway and a network load balancer in a VPC).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Handling<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies how to handle request payload content type conversions. Supported values are `CONVERT_TO_BINARY` and `CONVERT_TO_TEXT`. If this property is not defined, the request payload will be passed through from the method request to integration request without modification, provided that the passthroughBehaviors is configured to support payload pass-through.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Credentials<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The credentials required for the integration. For `AWS` integrations, 2 options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role&#39;s ARN. To require that the caller&#39;s identity be passed through from the request, specify the string `arn:aws:iam::\*:user/\*`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTP method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTION`, `ANY`)
when calling the associated resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Integration<wbr>Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration HTTP method
(`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONs`, `ANY`, `PATCH`) specifying how API Gateway will interact with the back end.
**Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
Not all methods are compatible with all `AWS` integrations.
e.g. Lambda function [can only be invoked](https://github.com/awslabs/aws-apigateway-importer/issues/9#issuecomment-129651005) via `POST`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Passthrough<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The integration passthrough behavior (`WHEN_NO_MATCH`, `WHEN_NO_TEMPLATES`, `NEVER`).  **Required** if `request_templates` is used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of request query string parameters and headers that should be passed to the backend responder.
For example: `request_parameters = { &#34;integration.request.header.X-Some-Other-Header&#34; = &#34;method.request.header.X-Some-Header&#34; }`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Request<wbr>Templates<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of the integration&#39;s request templates.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API resource ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Timeout<wbr>Milliseconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Custom timeout between 50 and 29,000 milliseconds. The default value is 29,000 milliseconds.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [type](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/). Valid values are `HTTP` (for HTTP backends), `MOCK` (not calling any real backend), `AWS` (for AWS services), `AWS_PROXY` (for Lambda proxy integration) and `HTTP_PROXY` (for HTTP proxy integration). An `HTTP` or `HTTP_PROXY` integration with a `connection_type` of `VPC_LINK` is referred to as a private integration and uses a VpcLink to connect API Gateway to a network load balancer of a VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The input&#39;s URI. **Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the RFC-3986 specification . For AWS integrations, the URI should be of the form `arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`. `region`, `subdomain` and `service` are used to determine the right endpoint.
e.g. `arn:aws:apigateway:eu-west-1:lambda:path/2015-03-31/functions/arn:aws:lambda:eu-west-1:012345678901:function:my-func/invocations`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Cache<wbr>Key<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of cache key parameters for the integration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cache<wbr>Namespace<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The integration&#39;s cache namespace.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The id of the VpcLink used for the integration. **Required** if `connection_type` is `VPC_LINK`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [connectionType](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/#connectionType). Valid values are `INTERNET` (default for connections through the public routable internet), and `VPC_LINK` (for private connections between API Gateway and a network load balancer in a VPC).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Handling<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies how to handle request payload content type conversions. Supported values are `CONVERT_TO_BINARY` and `CONVERT_TO_TEXT`. If this property is not defined, the request payload will be passed through from the method request to integration request without modification, provided that the passthroughBehaviors is configured to support payload pass-through.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Credentials<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The credentials required for the integration. For `AWS` integrations, 2 options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role&#39;s ARN. To require that the caller&#39;s identity be passed through from the request, specify the string `arn:aws:iam::\*:user/\*`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTP method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTION`, `ANY`)
when calling the associated resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Integration<wbr>Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The integration HTTP method
(`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONs`, `ANY`, `PATCH`) specifying how API Gateway will interact with the back end.
**Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
Not all methods are compatible with all `AWS` integrations.
e.g. Lambda function [can only be invoked](https://github.com/awslabs/aws-apigateway-importer/issues/9#issuecomment-129651005) via `POST`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Passthrough<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The integration passthrough behavior (`WHEN_NO_MATCH`, `WHEN_NO_TEMPLATES`, `NEVER`).  **Required** if `request_templates` is used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of request query string parameters and headers that should be passed to the backend responder.
For example: `request_parameters = { &#34;integration.request.header.X-Some-Other-Header&#34; = &#34;method.request.header.X-Some-Header&#34; }`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Request<wbr>Templates<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of the integration&#39;s request templates.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API resource ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Timeout<wbr>Milliseconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Custom timeout between 50 and 29,000 milliseconds. The default value is 29,000 milliseconds.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [type](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/). Valid values are `HTTP` (for HTTP backends), `MOCK` (not calling any real backend), `AWS` (for AWS services), `AWS_PROXY` (for Lambda proxy integration) and `HTTP_PROXY` (for HTTP proxy integration). An `HTTP` or `HTTP_PROXY` integration with a `connection_type` of `VPC_LINK` is referred to as a private integration and uses a VpcLink to connect API Gateway to a network load balancer of a VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Uri<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The input&#39;s URI. **Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the RFC-3986 specification . For AWS integrations, the URI should be of the form `arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`. `region`, `subdomain` and `service` are used to determine the right endpoint.
e.g. `arn:aws:apigateway:eu-west-1:lambda:path/2015-03-31/functions/arn:aws:lambda:eu-west-1:012345678901:function:my-func/invocations`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">cache<wbr>Key<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of cache key parameters for the integration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cache<wbr>Namespace<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The integration&#39;s cache namespace.
{{% /md %}}</dd>

    <dt class="property-"
            title="">connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the VpcLink used for the integration. **Required** if `connection_type` is `VPC_LINK`
{{% /md %}}</dd>

    <dt class="property-"
            title="">connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [connectionType](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/#connectionType). Valid values are `INTERNET` (default for connections through the public routable internet), and `VPC_LINK` (for private connections between API Gateway and a network load balancer in a VPC).
{{% /md %}}</dd>

    <dt class="property-"
            title="">content<wbr>Handling<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies how to handle request payload content type conversions. Supported values are `CONVERT_TO_BINARY` and `CONVERT_TO_TEXT`. If this property is not defined, the request payload will be passed through from the method request to integration request without modification, provided that the passthroughBehaviors is configured to support payload pass-through.
{{% /md %}}</dd>

    <dt class="property-"
            title="">credentials<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The credentials required for the integration. For `AWS` integrations, 2 options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role&#39;s ARN. To require that the caller&#39;s identity be passed through from the request, specify the string `arn:aws:iam::\*:user/\*`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTP method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTION`, `ANY`)
when calling the associated resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">integration<wbr>Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration HTTP method
(`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONs`, `ANY`, `PATCH`) specifying how API Gateway will interact with the back end.
**Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
Not all methods are compatible with all `AWS` integrations.
e.g. Lambda function [can only be invoked](https://github.com/awslabs/aws-apigateway-importer/issues/9#issuecomment-129651005) via `POST`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">passthrough<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The integration passthrough behavior (`WHEN_NO_MATCH`, `WHEN_NO_TEMPLATES`, `NEVER`).  **Required** if `request_templates` is used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of request query string parameters and headers that should be passed to the backend responder.
For example: `request_parameters = { &#34;integration.request.header.X-Some-Other-Header&#34; = &#34;method.request.header.X-Some-Header&#34; }`
{{% /md %}}</dd>

    <dt class="property-"
            title="">request<wbr>Templates<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of the integration&#39;s request templates.
{{% /md %}}</dd>

    <dt class="property-"
            title="">resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API resource ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">timeout<wbr>Milliseconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Custom timeout between 50 and 29,000 milliseconds. The default value is 29,000 milliseconds.
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [type](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/). Valid values are `HTTP` (for HTTP backends), `MOCK` (not calling any real backend), `AWS` (for AWS services), `AWS_PROXY` (for Lambda proxy integration) and `HTTP_PROXY` (for HTTP proxy integration). An `HTTP` or `HTTP_PROXY` integration with a `connection_type` of `VPC_LINK` is referred to as a private integration and uses a VpcLink to connect API Gateway to a network load balancer of a VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The input&#39;s URI. **Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the RFC-3986 specification . For AWS integrations, the URI should be of the form `arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`. `region`, `subdomain` and `service` are used to determine the right endpoint.
e.g. `arn:aws:apigateway:eu-west-1:lambda:path/2015-03-31/functions/arn:aws:lambda:eu-west-1:012345678901:function:my-func/invocations`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">cache_<wbr>key_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of cache key parameters for the integration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cache_<wbr>namespace<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The integration&#39;s cache namespace.
{{% /md %}}</dd>

    <dt class="property-"
            title="">connection_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the VpcLink used for the integration. **Required** if `connection_type` is `VPC_LINK`
{{% /md %}}</dd>

    <dt class="property-"
            title="">connection_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [connectionType](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/#connectionType). Valid values are `INTERNET` (default for connections through the public routable internet), and `VPC_LINK` (for private connections between API Gateway and a network load balancer in a VPC).
{{% /md %}}</dd>

    <dt class="property-"
            title="">content_<wbr>handling<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies how to handle request payload content type conversions. Supported values are `CONVERT_TO_BINARY` and `CONVERT_TO_TEXT`. If this property is not defined, the request payload will be passed through from the method request to integration request without modification, provided that the passthroughBehaviors is configured to support payload pass-through.
{{% /md %}}</dd>

    <dt class="property-"
            title="">credentials<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The credentials required for the integration. For `AWS` integrations, 2 options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role&#39;s ARN. To require that the caller&#39;s identity be passed through from the request, specify the string `arn:aws:iam::\*:user/\*`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">http_<wbr>method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The HTTP method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTION`, `ANY`)
when calling the associated resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">integration_<wbr>http_<wbr>method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The integration HTTP method
(`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONs`, `ANY`, `PATCH`) specifying how API Gateway will interact with the back end.
**Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
Not all methods are compatible with all `AWS` integrations.
e.g. Lambda function [can only be invoked](https://github.com/awslabs/aws-apigateway-importer/issues/9#issuecomment-129651005) via `POST`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">passthrough_<wbr>behavior<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The integration passthrough behavior (`WHEN_NO_MATCH`, `WHEN_NO_TEMPLATES`, `NEVER`).  **Required** if `request_templates` is used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">request_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of request query string parameters and headers that should be passed to the backend responder.
For example: `request_parameters = { &#34;integration.request.header.X-Some-Other-Header&#34; = &#34;method.request.header.X-Some-Header&#34; }`
{{% /md %}}</dd>

    <dt class="property-"
            title="">request_<wbr>templates<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of the integration&#39;s request templates.
{{% /md %}}</dd>

    <dt class="property-"
            title="">resource_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The API resource ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rest_<wbr>api<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">timeout_<wbr>milliseconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Custom timeout between 50 and 29,000 milliseconds. The default value is 29,000 milliseconds.
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [type](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/). Valid values are `HTTP` (for HTTP backends), `MOCK` (not calling any real backend), `AWS` (for AWS services), `AWS_PROXY` (for Lambda proxy integration) and `HTTP_PROXY` (for HTTP proxy integration). An `HTTP` or `HTTP_PROXY` integration with a `connection_type` of `VPC_LINK` is referred to as a private integration and uses a VpcLink to connect API Gateway to a network load balancer of a VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">uri<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The input&#39;s URI. **Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the RFC-3986 specification . For AWS integrations, the URI should be of the form `arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`. `region`, `subdomain` and `service` are used to determine the right endpoint.
e.g. `arn:aws:apigateway:eu-west-1:lambda:path/2015-03-31/functions/arn:aws:lambda:eu-west-1:012345678901:function:my-func/invocations`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Integration Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#IntegrationState">IntegrationState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#Integration">Integration</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>cache_key_parameters=None<span class="p">, </span>cache_namespace=None<span class="p">, </span>connection_id=None<span class="p">, </span>connection_type=None<span class="p">, </span>content_handling=None<span class="p">, </span>credentials=None<span class="p">, </span>http_method=None<span class="p">, </span>integration_http_method=None<span class="p">, </span>passthrough_behavior=None<span class="p">, </span>request_parameters=None<span class="p">, </span>request_templates=None<span class="p">, </span>resource_id=None<span class="p">, </span>rest_api=None<span class="p">, </span>timeout_milliseconds=None<span class="p">, </span>type=None<span class="p">, </span>uri=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetIntegration<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#IntegrationState">IntegrationState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#Integration">Integration</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.Integration.html">Integration</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.IntegrationState.html">IntegrationState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Integration resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Cache<wbr>Key<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of cache key parameters for the integration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Namespace<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration&#39;s cache namespace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the VpcLink used for the integration. **Required** if `connection_type` is `VPC_LINK`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [connectionType](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/#connectionType). Valid values are `INTERNET` (default for connections through the public routable internet), and `VPC_LINK` (for private connections between API Gateway and a network load balancer in a VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Handling<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies how to handle request payload content type conversions. Supported values are `CONVERT_TO_BINARY` and `CONVERT_TO_TEXT`. If this property is not defined, the request payload will be passed through from the method request to integration request without modification, provided that the passthroughBehaviors is configured to support payload pass-through.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Credentials<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The credentials required for the integration. For `AWS` integrations, 2 options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role&#39;s ARN. To require that the caller&#39;s identity be passed through from the request, specify the string `arn:aws:iam::\*:user/\*`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The HTTP method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTION`, `ANY`)
when calling the associated resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Integration<wbr>Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration HTTP method
(`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONs`, `ANY`, `PATCH`) specifying how API Gateway will interact with the back end.
**Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
Not all methods are compatible with all `AWS` integrations.
e.g. Lambda function [can only be invoked](https://github.com/awslabs/aws-apigateway-importer/issues/9#issuecomment-129651005) via `POST`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Passthrough<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration passthrough behavior (`WHEN_NO_MATCH`, `WHEN_NO_TEMPLATES`, `NEVER`).  **Required** if `request_templates` is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of request query string parameters and headers that should be passed to the backend responder.
For example: `request_parameters = { &#34;integration.request.header.X-Some-Other-Header&#34; = &#34;method.request.header.X-Some-Header&#34; }`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Templates<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of the integration&#39;s request templates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The API resource ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<wbr>Milliseconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Custom timeout between 50 and 29,000 milliseconds. The default value is 29,000 milliseconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [type](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/). Valid values are `HTTP` (for HTTP backends), `MOCK` (not calling any real backend), `AWS` (for AWS services), `AWS_PROXY` (for Lambda proxy integration) and `HTTP_PROXY` (for HTTP proxy integration). An `HTTP` or `HTTP_PROXY` integration with a `connection_type` of `VPC_LINK` is referred to as a private integration and uses a VpcLink to connect API Gateway to a network load balancer of a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The input&#39;s URI. **Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the RFC-3986 specification . For AWS integrations, the URI should be of the form `arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`. `region`, `subdomain` and `service` are used to determine the right endpoint.
e.g. `arn:aws:apigateway:eu-west-1:lambda:path/2015-03-31/functions/arn:aws:lambda:eu-west-1:012345678901:function:my-func/invocations`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cache<wbr>Key<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of cache key parameters for the integration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Namespace<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The integration&#39;s cache namespace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The id of the VpcLink used for the integration. **Required** if `connection_type` is `VPC_LINK`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [connectionType](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/#connectionType). Valid values are `INTERNET` (default for connections through the public routable internet), and `VPC_LINK` (for private connections between API Gateway and a network load balancer in a VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Handling<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies how to handle request payload content type conversions. Supported values are `CONVERT_TO_BINARY` and `CONVERT_TO_TEXT`. If this property is not defined, the request payload will be passed through from the method request to integration request without modification, provided that the passthroughBehaviors is configured to support payload pass-through.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Credentials<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The credentials required for the integration. For `AWS` integrations, 2 options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role&#39;s ARN. To require that the caller&#39;s identity be passed through from the request, specify the string `arn:aws:iam::\*:user/\*`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The HTTP method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTION`, `ANY`)
when calling the associated resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Integration<wbr>Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The integration HTTP method
(`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONs`, `ANY`, `PATCH`) specifying how API Gateway will interact with the back end.
**Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
Not all methods are compatible with all `AWS` integrations.
e.g. Lambda function [can only be invoked](https://github.com/awslabs/aws-apigateway-importer/issues/9#issuecomment-129651005) via `POST`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Passthrough<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The integration passthrough behavior (`WHEN_NO_MATCH`, `WHEN_NO_TEMPLATES`, `NEVER`).  **Required** if `request_templates` is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of request query string parameters and headers that should be passed to the backend responder.
For example: `request_parameters = { &#34;integration.request.header.X-Some-Other-Header&#34; = &#34;method.request.header.X-Some-Header&#34; }`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Templates<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of the integration&#39;s request templates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The API resource ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<wbr>Milliseconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Custom timeout between 50 and 29,000 milliseconds. The default value is 29,000 milliseconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [type](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/). Valid values are `HTTP` (for HTTP backends), `MOCK` (not calling any real backend), `AWS` (for AWS services), `AWS_PROXY` (for Lambda proxy integration) and `HTTP_PROXY` (for HTTP proxy integration). An `HTTP` or `HTTP_PROXY` integration with a `connection_type` of `VPC_LINK` is referred to as a private integration and uses a VpcLink to connect API Gateway to a network load balancer of a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Uri<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The input&#39;s URI. **Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the RFC-3986 specification . For AWS integrations, the URI should be of the form `arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`. `region`, `subdomain` and `service` are used to determine the right endpoint.
e.g. `arn:aws:apigateway:eu-west-1:lambda:path/2015-03-31/functions/arn:aws:lambda:eu-west-1:012345678901:function:my-func/invocations`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cache<wbr>Key<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of cache key parameters for the integration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache<wbr>Namespace<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration&#39;s cache namespace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the VpcLink used for the integration. **Required** if `connection_type` is `VPC_LINK`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [connectionType](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/#connectionType). Valid values are `INTERNET` (default for connections through the public routable internet), and `VPC_LINK` (for private connections between API Gateway and a network load balancer in a VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Handling<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies how to handle request payload content type conversions. Supported values are `CONVERT_TO_BINARY` and `CONVERT_TO_TEXT`. If this property is not defined, the request payload will be passed through from the method request to integration request without modification, provided that the passthroughBehaviors is configured to support payload pass-through.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">credentials<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The credentials required for the integration. For `AWS` integrations, 2 options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role&#39;s ARN. To require that the caller&#39;s identity be passed through from the request, specify the string `arn:aws:iam::\*:user/\*`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The HTTP method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTION`, `ANY`)
when calling the associated resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">integration<wbr>Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration HTTP method
(`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONs`, `ANY`, `PATCH`) specifying how API Gateway will interact with the back end.
**Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
Not all methods are compatible with all `AWS` integrations.
e.g. Lambda function [can only be invoked](https://github.com/awslabs/aws-apigateway-importer/issues/9#issuecomment-129651005) via `POST`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">passthrough<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration passthrough behavior (`WHEN_NO_MATCH`, `WHEN_NO_TEMPLATES`, `NEVER`).  **Required** if `request_templates` is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of request query string parameters and headers that should be passed to the backend responder.
For example: `request_parameters = { &#34;integration.request.header.X-Some-Other-Header&#34; = &#34;method.request.header.X-Some-Header&#34; }`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request<wbr>Templates<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of the integration&#39;s request templates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The API resource ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string | RestApi</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<wbr>Milliseconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Custom timeout between 50 and 29,000 milliseconds. The default value is 29,000 milliseconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [type](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/). Valid values are `HTTP` (for HTTP backends), `MOCK` (not calling any real backend), `AWS` (for AWS services), `AWS_PROXY` (for Lambda proxy integration) and `HTTP_PROXY` (for HTTP proxy integration). An `HTTP` or `HTTP_PROXY` integration with a `connection_type` of `VPC_LINK` is referred to as a private integration and uses a VpcLink to connect API Gateway to a network load balancer of a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The input&#39;s URI. **Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the RFC-3986 specification . For AWS integrations, the URI should be of the form `arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`. `region`, `subdomain` and `service` are used to determine the right endpoint.
e.g. `arn:aws:apigateway:eu-west-1:lambda:path/2015-03-31/functions/arn:aws:lambda:eu-west-1:012345678901:function:my-func/invocations`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cache_<wbr>key_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of cache key parameters for the integration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache_<wbr>namespace<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The integration&#39;s cache namespace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the VpcLink used for the integration. **Required** if `connection_type` is `VPC_LINK`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [connectionType](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/#connectionType). Valid values are `INTERNET` (default for connections through the public routable internet), and `VPC_LINK` (for private connections between API Gateway and a network load balancer in a VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>handling<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies how to handle request payload content type conversions. Supported values are `CONVERT_TO_BINARY` and `CONVERT_TO_TEXT`. If this property is not defined, the request payload will be passed through from the method request to integration request without modification, provided that the passthroughBehaviors is configured to support payload pass-through.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">credentials<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The credentials required for the integration. For `AWS` integrations, 2 options are available. To specify an IAM Role for Amazon API Gateway to assume, use the role&#39;s ARN. To require that the caller&#39;s identity be passed through from the request, specify the string `arn:aws:iam::\*:user/\*`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http_<wbr>method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The HTTP method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTION`, `ANY`)
when calling the associated resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">integration_<wbr>http_<wbr>method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The integration HTTP method
(`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONs`, `ANY`, `PATCH`) specifying how API Gateway will interact with the back end.
**Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
Not all methods are compatible with all `AWS` integrations.
e.g. Lambda function [can only be invoked](https://github.com/awslabs/aws-apigateway-importer/issues/9#issuecomment-129651005) via `POST`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">passthrough_<wbr>behavior<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The integration passthrough behavior (`WHEN_NO_MATCH`, `WHEN_NO_TEMPLATES`, `NEVER`).  **Required** if `request_templates` is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of request query string parameters and headers that should be passed to the backend responder.
For example: `request_parameters = { &#34;integration.request.header.X-Some-Other-Header&#34; = &#34;method.request.header.X-Some-Header&#34; }`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request_<wbr>templates<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of the integration&#39;s request templates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The API resource ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rest_<wbr>api<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout_<wbr>milliseconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Custom timeout between 50 and 29,000 milliseconds. The default value is 29,000 milliseconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The integration input&#39;s [type](https://docs.aws.amazon.com/apigateway/api-reference/resource/integration/). Valid values are `HTTP` (for HTTP backends), `MOCK` (not calling any real backend), `AWS` (for AWS services), `AWS_PROXY` (for Lambda proxy integration) and `HTTP_PROXY` (for HTTP proxy integration). An `HTTP` or `HTTP_PROXY` integration with a `connection_type` of `VPC_LINK` is referred to as a private integration and uses a VpcLink to connect API Gateway to a network load balancer of a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">uri<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The input&#39;s URI. **Required** if `type` is `AWS`, `AWS_PROXY`, `HTTP` or `HTTP_PROXY`.
For HTTP integrations, the URI must be a fully formed, encoded HTTP(S) URL according to the RFC-3986 specification . For AWS integrations, the URI should be of the form `arn:aws:apigateway:{region}:{subdomain.service|service}:{path|action}/{service_api}`. `region`, `subdomain` and `service` are used to determine the right endpoint.
e.g. `arn:aws:apigateway:eu-west-1:lambda:path/2015-03-31/functions/arn:aws:lambda:eu-west-1:012345678901:function:my-func/invocations`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







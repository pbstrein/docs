
---
title: "Method"
block_external_search_index: true
---

Provides a HTTP Method for an API Gateway Resource.

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
```

## Usage with Cognito User Pool Authorizer

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const config = new pulumi.Config();
const cognitoUserPoolName = config.require("cognitoUserPoolName");

const thisUserPools = aws.cognito.getUserPools({
    name: cognitoUserPoolName,
});
const thisRestApi = new aws.apigateway.RestApi("this", {});
const thisResource = new aws.apigateway.Resource("this", {
    parentId: thisRestApi.rootResourceId,
    pathPart: "{proxy+}",
    restApi: thisRestApi.id,
});
const thisAuthorizer = new aws.apigateway.Authorizer("this", {
    providerArns: thisUserPools.arns,
    restApi: thisRestApi.id,
    type: "COGNITO_USER_POOLS",
});
const any = new aws.apigateway.Method("any", {
    authorization: "COGNITO_USER_POOLS",
    authorizerId: thisAuthorizer.id,
    httpMethod: "ANY",
    requestParameters: {
        "method.request.path.proxy": true,
    },
    resourceId: thisResource.id,
    restApi: thisRestApi.id,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/api_gateway_method.html.markdown.



## Create a Method Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#Method">Method</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#MethodArgs">MethodArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Method</span><span class="p">(resource_name, opts=None, </span>api_key_required=None<span class="p">, </span>authorization=None<span class="p">, </span>authorization_scopes=None<span class="p">, </span>authorizer_id=None<span class="p">, </span>http_method=None<span class="p">, </span>request_models=None<span class="p">, </span>request_parameters=None<span class="p">, </span>request_validator_id=None<span class="p">, </span>resource_id=None<span class="p">, </span>rest_api=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewMethod<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#MethodArgs">MethodArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#Method">Method</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.Method.html">Method</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.MethodArgs.html">MethodArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Api<wbr>Key<wbr>Required<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specify if the method requires an API key
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Authorization<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of authorization used for the method (`NONE`, `CUSTOM`, `AWS_IAM`, `COGNITO_USER_POOLS`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authorization<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The authorization scopes used when the authorization is `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authorizer<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The authorizer id to be used when the authorization is `CUSTOM` or `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTP Method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONS`, `ANY`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Models<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of the API models used for the request&#39;s content type
where key is the content type (e.g. `application/json`)
and value is either `Error`, `Empty` (built-in models) or `aws.apigateway.Model`&#39;s `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, bool>?</span>
    </dt>
    <dd>{{% md %}}A map of request parameters (from the path, query string and headers) that should be passed to the integration. The boolean value indicates whether the parameter is required (`true`) or optional (`false`).
For example: `request_parameters = {&#34;method.request.header.X-Some-Header&#34; = true &#34;method.request.querystring.some-query-param&#34; = true}` would define that the header `X-Some-Header` and the query string `some-query-param` must be provided in the request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Validator<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of a `aws.apigateway.RequestValidator`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API resource ID
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Api<wbr>Key<wbr>Required<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specify if the method requires an API key
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Authorization<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of authorization used for the method (`NONE`, `CUSTOM`, `AWS_IAM`, `COGNITO_USER_POOLS`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authorization<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The authorization scopes used when the authorization is `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authorizer<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The authorizer id to be used when the authorization is `CUSTOM` or `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTP Method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONS`, `ANY`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Models<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of the API models used for the request&#39;s content type
where key is the content type (e.g. `application/json`)
and value is either `Error`, `Empty` (built-in models) or `aws.apigateway.Model`&#39;s `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">map[string]bool</span>
    </dt>
    <dd>{{% md %}}A map of request parameters (from the path, query string and headers) that should be passed to the integration. The boolean value indicates whether the parameter is required (`true`) or optional (`false`).
For example: `request_parameters = {&#34;method.request.header.X-Some-Header&#34; = true &#34;method.request.querystring.some-query-param&#34; = true}` would define that the header `X-Some-Header` and the query string `some-query-param` must be provided in the request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Validator<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of a `aws.apigateway.RequestValidator`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API resource ID
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">api<wbr>Key<wbr>Required<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specify if the method requires an API key
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">authorization<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of authorization used for the method (`NONE`, `CUSTOM`, `AWS_IAM`, `COGNITO_USER_POOLS`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authorization<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The authorization scopes used when the authorization is `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authorizer<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The authorizer id to be used when the authorization is `CUSTOM` or `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTP Method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONS`, `ANY`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request<wbr>Models<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of the API models used for the request&#39;s content type
where key is the content type (e.g. `application/json`)
and value is either `Error`, `Empty` (built-in models) or `aws.apigateway.Model`&#39;s `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: boolean}?</span>
    </dt>
    <dd>{{% md %}}A map of request parameters (from the path, query string and headers) that should be passed to the integration. The boolean value indicates whether the parameter is required (`true`) or optional (`false`).
For example: `request_parameters = {&#34;method.request.header.X-Some-Header&#34; = true &#34;method.request.querystring.some-query-param&#34; = true}` would define that the header `X-Some-Header` and the query string `some-query-param` must be provided in the request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request<wbr>Validator<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of a `aws.apigateway.RequestValidator`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API resource ID
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string | RestApi</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">api_<wbr>key_<wbr>required<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specify if the method requires an API key
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">authorization<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of authorization used for the method (`NONE`, `CUSTOM`, `AWS_IAM`, `COGNITO_USER_POOLS`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authorization_<wbr>scopes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The authorization scopes used when the authorization is `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authorizer_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The authorizer id to be used when the authorization is `CUSTOM` or `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">http_<wbr>method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The HTTP Method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONS`, `ANY`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request_<wbr>models<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of the API models used for the request&#39;s content type
where key is the content type (e.g. `application/json`)
and value is either `Error`, `Empty` (built-in models) or `aws.apigateway.Model`&#39;s `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Boolean]</span>
    </dt>
    <dd>{{% md %}}A map of request parameters (from the path, query string and headers) that should be passed to the integration. The boolean value indicates whether the parameter is required (`true`) or optional (`false`).
For example: `request_parameters = {&#34;method.request.header.X-Some-Header&#34; = true &#34;method.request.querystring.some-query-param&#34; = true}` would define that the header `X-Some-Header` and the query string `some-query-param` must be provided in the request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request_<wbr>validator_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of a `aws.apigateway.RequestValidator`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">resource_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The API resource ID
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rest_<wbr>api<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Method Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Api<wbr>Key<wbr>Required<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specify if the method requires an API key
{{% /md %}}</dd>

    <dt class="property-"
            title="">Authorization<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of authorization used for the method (`NONE`, `CUSTOM`, `AWS_IAM`, `COGNITO_USER_POOLS`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Authorization<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The authorization scopes used when the authorization is `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Authorizer<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The authorizer id to be used when the authorization is `CUSTOM` or `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTP Method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONS`, `ANY`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Request<wbr>Models<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of the API models used for the request&#39;s content type
where key is the content type (e.g. `application/json`)
and value is either `Error`, `Empty` (built-in models) or `aws.apigateway.Model`&#39;s `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, bool>?</span>
    </dt>
    <dd>{{% md %}}A map of request parameters (from the path, query string and headers) that should be passed to the integration. The boolean value indicates whether the parameter is required (`true`) or optional (`false`).
For example: `request_parameters = {&#34;method.request.header.X-Some-Header&#34; = true &#34;method.request.querystring.some-query-param&#34; = true}` would define that the header `X-Some-Header` and the query string `some-query-param` must be provided in the request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Request<wbr>Validator<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of a `aws.apigateway.RequestValidator`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API resource ID
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Api<wbr>Key<wbr>Required<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specify if the method requires an API key
{{% /md %}}</dd>

    <dt class="property-"
            title="">Authorization<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of authorization used for the method (`NONE`, `CUSTOM`, `AWS_IAM`, `COGNITO_USER_POOLS`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Authorization<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The authorization scopes used when the authorization is `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Authorizer<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The authorizer id to be used when the authorization is `CUSTOM` or `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTP Method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONS`, `ANY`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Request<wbr>Models<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of the API models used for the request&#39;s content type
where key is the content type (e.g. `application/json`)
and value is either `Error`, `Empty` (built-in models) or `aws.apigateway.Model`&#39;s `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">map[string]bool</span>
    </dt>
    <dd>{{% md %}}A map of request parameters (from the path, query string and headers) that should be passed to the integration. The boolean value indicates whether the parameter is required (`true`) or optional (`false`).
For example: `request_parameters = {&#34;method.request.header.X-Some-Header&#34; = true &#34;method.request.querystring.some-query-param&#34; = true}` would define that the header `X-Some-Header` and the query string `some-query-param` must be provided in the request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Request<wbr>Validator<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of a `aws.apigateway.RequestValidator`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API resource ID
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">api<wbr>Key<wbr>Required<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specify if the method requires an API key
{{% /md %}}</dd>

    <dt class="property-"
            title="">authorization<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of authorization used for the method (`NONE`, `CUSTOM`, `AWS_IAM`, `COGNITO_USER_POOLS`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">authorization<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The authorization scopes used when the authorization is `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-"
            title="">authorizer<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The authorizer id to be used when the authorization is `CUSTOM` or `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-"
            title="">http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTP Method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONS`, `ANY`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">request<wbr>Models<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of the API models used for the request&#39;s content type
where key is the content type (e.g. `application/json`)
and value is either `Error`, `Empty` (built-in models) or `aws.apigateway.Model`&#39;s `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: boolean}?</span>
    </dt>
    <dd>{{% md %}}A map of request parameters (from the path, query string and headers) that should be passed to the integration. The boolean value indicates whether the parameter is required (`true`) or optional (`false`).
For example: `request_parameters = {&#34;method.request.header.X-Some-Header&#34; = true &#34;method.request.querystring.some-query-param&#34; = true}` would define that the header `X-Some-Header` and the query string `some-query-param` must be provided in the request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">request<wbr>Validator<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of a `aws.apigateway.RequestValidator`
{{% /md %}}</dd>

    <dt class="property-"
            title="">resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The API resource ID
{{% /md %}}</dd>

    <dt class="property-"
            title="">rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">api_<wbr>key_<wbr>required<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specify if the method requires an API key
{{% /md %}}</dd>

    <dt class="property-"
            title="">authorization<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of authorization used for the method (`NONE`, `CUSTOM`, `AWS_IAM`, `COGNITO_USER_POOLS`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">authorization_<wbr>scopes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The authorization scopes used when the authorization is `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-"
            title="">authorizer_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The authorizer id to be used when the authorization is `CUSTOM` or `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-"
            title="">http_<wbr>method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The HTTP Method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONS`, `ANY`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">request_<wbr>models<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of the API models used for the request&#39;s content type
where key is the content type (e.g. `application/json`)
and value is either `Error`, `Empty` (built-in models) or `aws.apigateway.Model`&#39;s `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">request_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Boolean]</span>
    </dt>
    <dd>{{% md %}}A map of request parameters (from the path, query string and headers) that should be passed to the integration. The boolean value indicates whether the parameter is required (`true`) or optional (`false`).
For example: `request_parameters = {&#34;method.request.header.X-Some-Header&#34; = true &#34;method.request.querystring.some-query-param&#34; = true}` would define that the header `X-Some-Header` and the query string `some-query-param` must be provided in the request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">request_<wbr>validator_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of a `aws.apigateway.RequestValidator`
{{% /md %}}</dd>

    <dt class="property-"
            title="">resource_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The API resource ID
{{% /md %}}</dd>

    <dt class="property-"
            title="">rest_<wbr>api<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Method Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#MethodState">MethodState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#Method">Method</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>api_key_required=None<span class="p">, </span>authorization=None<span class="p">, </span>authorization_scopes=None<span class="p">, </span>authorizer_id=None<span class="p">, </span>http_method=None<span class="p">, </span>request_models=None<span class="p">, </span>request_parameters=None<span class="p">, </span>request_validator_id=None<span class="p">, </span>resource_id=None<span class="p">, </span>rest_api=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetMethod<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#MethodState">MethodState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#Method">Method</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.Method.html">Method</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.MethodState.html">MethodState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Method resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Api<wbr>Key<wbr>Required<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specify if the method requires an API key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authorization<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of authorization used for the method (`NONE`, `CUSTOM`, `AWS_IAM`, `COGNITO_USER_POOLS`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authorization<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The authorization scopes used when the authorization is `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authorizer<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The authorizer id to be used when the authorization is `CUSTOM` or `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The HTTP Method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONS`, `ANY`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Models<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of the API models used for the request&#39;s content type
where key is the content type (e.g. `application/json`)
and value is either `Error`, `Empty` (built-in models) or `aws.apigateway.Model`&#39;s `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, bool>?</span>
    </dt>
    <dd>{{% md %}}A map of request parameters (from the path, query string and headers) that should be passed to the integration. The boolean value indicates whether the parameter is required (`true`) or optional (`false`).
For example: `request_parameters = {&#34;method.request.header.X-Some-Header&#34; = true &#34;method.request.querystring.some-query-param&#34; = true}` would define that the header `X-Some-Header` and the query string `some-query-param` must be provided in the request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Validator<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of a `aws.apigateway.RequestValidator`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The API resource ID
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Api<wbr>Key<wbr>Required<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specify if the method requires an API key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authorization<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of authorization used for the method (`NONE`, `CUSTOM`, `AWS_IAM`, `COGNITO_USER_POOLS`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authorization<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The authorization scopes used when the authorization is `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authorizer<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The authorizer id to be used when the authorization is `CUSTOM` or `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The HTTP Method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONS`, `ANY`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Models<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of the API models used for the request&#39;s content type
where key is the content type (e.g. `application/json`)
and value is either `Error`, `Empty` (built-in models) or `aws.apigateway.Model`&#39;s `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">map[string]bool</span>
    </dt>
    <dd>{{% md %}}A map of request parameters (from the path, query string and headers) that should be passed to the integration. The boolean value indicates whether the parameter is required (`true`) or optional (`false`).
For example: `request_parameters = {&#34;method.request.header.X-Some-Header&#34; = true &#34;method.request.querystring.some-query-param&#34; = true}` would define that the header `X-Some-Header` and the query string `some-query-param` must be provided in the request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Validator<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of a `aws.apigateway.RequestValidator`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The API resource ID
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">api<wbr>Key<wbr>Required<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specify if the method requires an API key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authorization<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of authorization used for the method (`NONE`, `CUSTOM`, `AWS_IAM`, `COGNITO_USER_POOLS`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authorization<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The authorization scopes used when the authorization is `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authorizer<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The authorizer id to be used when the authorization is `CUSTOM` or `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The HTTP Method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONS`, `ANY`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request<wbr>Models<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of the API models used for the request&#39;s content type
where key is the content type (e.g. `application/json`)
and value is either `Error`, `Empty` (built-in models) or `aws.apigateway.Model`&#39;s `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: boolean}?</span>
    </dt>
    <dd>{{% md %}}A map of request parameters (from the path, query string and headers) that should be passed to the integration. The boolean value indicates whether the parameter is required (`true`) or optional (`false`).
For example: `request_parameters = {&#34;method.request.header.X-Some-Header&#34; = true &#34;method.request.querystring.some-query-param&#34; = true}` would define that the header `X-Some-Header` and the query string `some-query-param` must be provided in the request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request<wbr>Validator<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of a `aws.apigateway.RequestValidator`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The API resource ID
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string | RestApi</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">api_<wbr>key_<wbr>required<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specify if the method requires an API key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authorization<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of authorization used for the method (`NONE`, `CUSTOM`, `AWS_IAM`, `COGNITO_USER_POOLS`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authorization_<wbr>scopes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The authorization scopes used when the authorization is `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authorizer_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The authorizer id to be used when the authorization is `CUSTOM` or `COGNITO_USER_POOLS`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http_<wbr>method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The HTTP Method (`GET`, `POST`, `PUT`, `DELETE`, `HEAD`, `OPTIONS`, `ANY`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request_<wbr>models<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of the API models used for the request&#39;s content type
where key is the content type (e.g. `application/json`)
and value is either `Error`, `Empty` (built-in models) or `aws.apigateway.Model`&#39;s `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Boolean]</span>
    </dt>
    <dd>{{% md %}}A map of request parameters (from the path, query string and headers) that should be passed to the integration. The boolean value indicates whether the parameter is required (`true`) or optional (`false`).
For example: `request_parameters = {&#34;method.request.header.X-Some-Header&#34; = true &#34;method.request.querystring.some-query-param&#34; = true}` would define that the header `X-Some-Header` and the query string `some-query-param` must be provided in the request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request_<wbr>validator_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of a `aws.apigateway.RequestValidator`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The API resource ID
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rest_<wbr>api<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







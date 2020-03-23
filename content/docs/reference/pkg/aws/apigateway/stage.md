
---
title: "Stage"
block_external_search_index: true
---

Provides an API Gateway Stage.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const testRestApi = new aws.apigateway.RestApi("test", {
    description: "This is my API for demonstration purposes",
});
const testResource = new aws.apigateway.Resource("test", {
    parentId: testRestApi.rootResourceId,
    pathPart: "mytestresource",
    restApi: testRestApi.id,
});
const testMethod = new aws.apigateway.Method("test", {
    authorization: "NONE",
    httpMethod: "GET",
    resourceId: testResource.id,
    restApi: testRestApi.id,
});
const testIntegration = new aws.apigateway.Integration("test", {
    httpMethod: testMethod.httpMethod,
    resourceId: testResource.id,
    restApi: testRestApi.id,
    type: "MOCK",
});
const testDeployment = new aws.apigateway.Deployment("test", {
    restApi: testRestApi.id,
    stageName: "dev",
}, {dependsOn: [testIntegration]});
const testStage = new aws.apigateway.Stage("test", {
    deployment: testDeployment.id,
    restApi: testRestApi.id,
    stageName: "prod",
});
const methodSettings = new aws.apigateway.MethodSettings("s", {
    methodPath: pulumi.interpolate`${testResource.pathPart}/${testMethod.httpMethod}`,
    restApi: testRestApi.id,
    settings: {
        loggingLevel: "INFO",
        metricsEnabled: true,
    },
    stageName: testStage.stageName,
});
```

### Managing the API Logging CloudWatch Log Group

API Gateway provides the ability to [enable CloudWatch API logging](https://docs.aws.amazon.com/apigateway/latest/developerguide/set-up-logging.html). To manage the CloudWatch Log Group when this feature is enabled, the [`aws.cloudwatch.LogGroup` resource](https://www.terraform.io/docs/providers/aws/r/cloudwatch_log_group.html) can be used where the name matches the API Gateway naming convention. If the CloudWatch Log Group previously exists, the [`aws.cloudwatch.LogGroup` resource can be imported ](https://www.terraform.io/docs/providers/aws/r/cloudwatch_log_group.html#import) as a one time operation and recreation of the environment can occur without import.

> The below configuration uses [`depends_on`](https://www.terraform.io/docs/configuration/resources.html#depends_on-explicit-resource-dependencies) to prevent ordering issues with API Gateway automatically creating the log group first and a variable for naming consistency. Other ordering and naming methodologies may be more appropriate for your environment.

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const config = new pulumi.Config();
const stageName = config.get("stageName") || "example";

const exampleRestApi = new aws.apigateway.RestApi("example", {});
const exampleLogGroup = new aws.cloudwatch.LogGroup("example", {
    retentionInDays: 7,
});
const exampleStage = new aws.apigateway.Stage("example", {
    name: stageName,
}, {dependsOn: [exampleLogGroup]});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/api_gateway_stage.html.markdown.



## Create a Stage Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#Stage">Stage</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#StageArgs">StageArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Stage</span><span class="p">(resource_name, opts=None, </span>access_log_settings=None<span class="p">, </span>cache_cluster_enabled=None<span class="p">, </span>cache_cluster_size=None<span class="p">, </span>client_certificate_id=None<span class="p">, </span>deployment=None<span class="p">, </span>description=None<span class="p">, </span>documentation_version=None<span class="p">, </span>rest_api=None<span class="p">, </span>stage_name=None<span class="p">, </span>tags=None<span class="p">, </span>variables=None<span class="p">, </span>xray_tracing_enabled=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewStage<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#StageArgs">StageArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#Stage">Stage</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.Stage.html">Stage</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.StageArgs.html">StageArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Access<wbr>Log<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#stageaccesslogsettings">Stage<wbr>Access<wbr>Log<wbr>Settings<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Enables access logs for the API stage. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Cluster<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a cache cluster is enabled for the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Cluster<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The size of the cache cluster for the stage, if enabled.
Allowed values include `0.5`, `1.6`, `6.1`, `13.5`, `28.4`, `58.2`, `118` and `237`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of a client certificate for the stage.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Deployment<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the deployment that the stage points to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Documentation<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the associated API documentation
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stage<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Variables<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A map that defines the stage variables
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Xray<wbr>Tracing<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether active tracing with X-ray is enabled. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Access<wbr>Log<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#stageaccesslogsettings">*Stage<wbr>Access<wbr>Log<wbr>Settings</a></span>
    </dt>
    <dd>{{% md %}}Enables access logs for the API stage. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Cluster<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a cache cluster is enabled for the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Cluster<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The size of the cache cluster for the stage, if enabled.
Allowed values include `0.5`, `1.6`, `6.1`, `13.5`, `28.4`, `58.2`, `118` and `237`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The identifier of a client certificate for the stage.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Deployment<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}The ID of the deployment that the stage points to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Documentation<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version of the associated API documentation
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stage<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Variables<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A map that defines the stage variables
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Xray<wbr>Tracing<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether active tracing with X-ray is enabled. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access<wbr>Log<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#stageaccesslogsettings">Stage<wbr>Access<wbr>Log<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}Enables access logs for the API stage. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache<wbr>Cluster<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a cache cluster is enabled for the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache<wbr>Cluster<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The size of the cache cluster for the stage, if enabled.
Allowed values include `0.5`, `1.6`, `6.1`, `13.5`, `28.4`, `58.2`, `118` and `237`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of a client certificate for the stage.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">deployment<span class="property-indicator"></span>
        <span class="property-type">string | Deployment</span>
    </dt>
    <dd>{{% md %}}The ID of the deployment that the stage points to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">documentation<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the associated API documentation
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string | RestApi</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stage<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">variables<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A map that defines the stage variables
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">xray<wbr>Tracing<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether active tracing with X-ray is enabled. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access_<wbr>log_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#stageaccesslogsettings">Dict[Stage<wbr>Access<wbr>Log<wbr>Settings]</a></span>
    </dt>
    <dd>{{% md %}}Enables access logs for the API stage. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache_<wbr>cluster_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a cache cluster is enabled for the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache_<wbr>cluster_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The size of the cache cluster for the stage, if enabled.
Allowed values include `0.5`, `1.6`, `6.1`, `13.5`, `28.4`, `58.2`, `118` and `237`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client_<wbr>certificate_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier of a client certificate for the stage.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">deployment<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The ID of the deployment that the stage points to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">documentation_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of the associated API documentation
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rest_<wbr>api<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stage_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">variables<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A map that defines the stage variables
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">xray_<wbr>tracing_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether active tracing with X-ray is enabled. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Stage Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Access<wbr>Log<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#stageaccesslogsettings">Stage<wbr>Access<wbr>Log<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}Enables access logs for the API stage. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cache<wbr>Cluster<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a cache cluster is enabled for the stage
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cache<wbr>Cluster<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The size of the cache cluster for the stage, if enabled.
Allowed values include `0.5`, `1.6`, `6.1`, `13.5`, `28.4`, `58.2`, `118` and `237`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Client<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of a client certificate for the stage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the deployment that the stage points to
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the stage
{{% /md %}}</dd>

    <dt class="property-"
            title="">Documentation<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the associated API documentation
{{% /md %}}</dd>

    <dt class="property-"
            title="">Execution<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The execution ARN to be used in [`lambda_permission`](https://www.terraform.io/docs/providers/aws/r/lambda_permission.html)&#39;s `source_arn`
when allowing API Gateway to invoke a Lambda function,
e.g. `arn:aws:execute-api:eu-west-2:123456789012:z4675bid1j/prod`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Invoke<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URL to invoke the API pointing to the stage,
e.g. `https://z4675bid1j.execute-api.eu-west-2.amazonaws.com/prod`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stage<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the stage
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Variables<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A map that defines the stage variables
{{% /md %}}</dd>

    <dt class="property-"
            title="">Xray<wbr>Tracing<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether active tracing with X-ray is enabled. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Access<wbr>Log<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#stageaccesslogsettings">*Stage<wbr>Access<wbr>Log<wbr>Settings</a></span>
    </dt>
    <dd>{{% md %}}Enables access logs for the API stage. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cache<wbr>Cluster<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a cache cluster is enabled for the stage
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cache<wbr>Cluster<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The size of the cache cluster for the stage, if enabled.
Allowed values include `0.5`, `1.6`, `6.1`, `13.5`, `28.4`, `58.2`, `118` and `237`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Client<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The identifier of a client certificate for the stage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the deployment that the stage points to
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of the stage
{{% /md %}}</dd>

    <dt class="property-"
            title="">Documentation<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version of the associated API documentation
{{% /md %}}</dd>

    <dt class="property-"
            title="">Execution<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The execution ARN to be used in [`lambda_permission`](https://www.terraform.io/docs/providers/aws/r/lambda_permission.html)&#39;s `source_arn`
when allowing API Gateway to invoke a Lambda function,
e.g. `arn:aws:execute-api:eu-west-2:123456789012:z4675bid1j/prod`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Invoke<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URL to invoke the API pointing to the stage,
e.g. `https://z4675bid1j.execute-api.eu-west-2.amazonaws.com/prod`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stage<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the stage
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Variables<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A map that defines the stage variables
{{% /md %}}</dd>

    <dt class="property-"
            title="">Xray<wbr>Tracing<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether active tracing with X-ray is enabled. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">access<wbr>Log<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#stageaccesslogsettings">Stage<wbr>Access<wbr>Log<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}Enables access logs for the API stage. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-"
            title="">cache<wbr>Cluster<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a cache cluster is enabled for the stage
{{% /md %}}</dd>

    <dt class="property-"
            title="">cache<wbr>Cluster<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The size of the cache cluster for the stage, if enabled.
Allowed values include `0.5`, `1.6`, `6.1`, `13.5`, `28.4`, `58.2`, `118` and `237`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">client<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of a client certificate for the stage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the deployment that the stage points to
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the stage
{{% /md %}}</dd>

    <dt class="property-"
            title="">documentation<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the associated API documentation
{{% /md %}}</dd>

    <dt class="property-"
            title="">execution<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The execution ARN to be used in [`lambda_permission`](https://www.terraform.io/docs/providers/aws/r/lambda_permission.html)&#39;s `source_arn`
when allowing API Gateway to invoke a Lambda function,
e.g. `arn:aws:execute-api:eu-west-2:123456789012:z4675bid1j/prod`
{{% /md %}}</dd>

    <dt class="property-"
            title="">invoke<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URL to invoke the API pointing to the stage,
e.g. `https://z4675bid1j.execute-api.eu-west-2.amazonaws.com/prod`
{{% /md %}}</dd>

    <dt class="property-"
            title="">rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

    <dt class="property-"
            title="">stage<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the stage
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">variables<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A map that defines the stage variables
{{% /md %}}</dd>

    <dt class="property-"
            title="">xray<wbr>Tracing<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether active tracing with X-ray is enabled. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">access_<wbr>log_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#stageaccesslogsettings">Dict[Stage<wbr>Access<wbr>Log<wbr>Settings]</a></span>
    </dt>
    <dd>{{% md %}}Enables access logs for the API stage. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-"
            title="">cache_<wbr>cluster_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a cache cluster is enabled for the stage
{{% /md %}}</dd>

    <dt class="property-"
            title="">cache_<wbr>cluster_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The size of the cache cluster for the stage, if enabled.
Allowed values include `0.5`, `1.6`, `6.1`, `13.5`, `28.4`, `58.2`, `118` and `237`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">client_<wbr>certificate_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier of a client certificate for the stage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the deployment that the stage points to
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the stage
{{% /md %}}</dd>

    <dt class="property-"
            title="">documentation_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of the associated API documentation
{{% /md %}}</dd>

    <dt class="property-"
            title="">execution_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The execution ARN to be used in [`lambda_permission`](https://www.terraform.io/docs/providers/aws/r/lambda_permission.html)&#39;s `source_arn`
when allowing API Gateway to invoke a Lambda function,
e.g. `arn:aws:execute-api:eu-west-2:123456789012:z4675bid1j/prod`
{{% /md %}}</dd>

    <dt class="property-"
            title="">invoke_<wbr>url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The URL to invoke the API pointing to the stage,
e.g. `https://z4675bid1j.execute-api.eu-west-2.amazonaws.com/prod`
{{% /md %}}</dd>

    <dt class="property-"
            title="">rest_<wbr>api<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

    <dt class="property-"
            title="">stage_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the stage
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">variables<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A map that defines the stage variables
{{% /md %}}</dd>

    <dt class="property-"
            title="">xray_<wbr>tracing_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether active tracing with X-ray is enabled. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Stage Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#StageState">StageState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#Stage">Stage</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>access_log_settings=None<span class="p">, </span>arn=None<span class="p">, </span>cache_cluster_enabled=None<span class="p">, </span>cache_cluster_size=None<span class="p">, </span>client_certificate_id=None<span class="p">, </span>deployment=None<span class="p">, </span>description=None<span class="p">, </span>documentation_version=None<span class="p">, </span>execution_arn=None<span class="p">, </span>invoke_url=None<span class="p">, </span>rest_api=None<span class="p">, </span>stage_name=None<span class="p">, </span>tags=None<span class="p">, </span>variables=None<span class="p">, </span>xray_tracing_enabled=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetStage<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#StageState">StageState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#Stage">Stage</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.Stage.html">Stage</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.StageState.html">StageState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Stage resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Access<wbr>Log<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#stageaccesslogsettings">Stage<wbr>Access<wbr>Log<wbr>Settings<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Enables access logs for the API stage. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Cluster<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a cache cluster is enabled for the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Cluster<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The size of the cache cluster for the stage, if enabled.
Allowed values include `0.5`, `1.6`, `6.1`, `13.5`, `28.4`, `58.2`, `118` and `237`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of a client certificate for the stage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the deployment that the stage points to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Documentation<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the associated API documentation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Execution<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The execution ARN to be used in [`lambda_permission`](https://www.terraform.io/docs/providers/aws/r/lambda_permission.html)&#39;s `source_arn`
when allowing API Gateway to invoke a Lambda function,
e.g. `arn:aws:execute-api:eu-west-2:123456789012:z4675bid1j/prod`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Invoke<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The URL to invoke the API pointing to the stage,
e.g. `https://z4675bid1j.execute-api.eu-west-2.amazonaws.com/prod`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stage<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Variables<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A map that defines the stage variables
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Xray<wbr>Tracing<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether active tracing with X-ray is enabled. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Access<wbr>Log<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#stageaccesslogsettings">*Stage<wbr>Access<wbr>Log<wbr>Settings</a></span>
    </dt>
    <dd>{{% md %}}Enables access logs for the API stage. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Cluster<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a cache cluster is enabled for the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Cluster<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The size of the cache cluster for the stage, if enabled.
Allowed values include `0.5`, `1.6`, `6.1`, `13.5`, `28.4`, `58.2`, `118` and `237`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The identifier of a client certificate for the stage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}The ID of the deployment that the stage points to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Documentation<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version of the associated API documentation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Execution<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The execution ARN to be used in [`lambda_permission`](https://www.terraform.io/docs/providers/aws/r/lambda_permission.html)&#39;s `source_arn`
when allowing API Gateway to invoke a Lambda function,
e.g. `arn:aws:execute-api:eu-west-2:123456789012:z4675bid1j/prod`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Invoke<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The URL to invoke the API pointing to the stage,
e.g. `https://z4675bid1j.execute-api.eu-west-2.amazonaws.com/prod`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stage<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Variables<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A map that defines the stage variables
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Xray<wbr>Tracing<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether active tracing with X-ray is enabled. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access<wbr>Log<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#stageaccesslogsettings">Stage<wbr>Access<wbr>Log<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}Enables access logs for the API stage. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache<wbr>Cluster<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a cache cluster is enabled for the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache<wbr>Cluster<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The size of the cache cluster for the stage, if enabled.
Allowed values include `0.5`, `1.6`, `6.1`, `13.5`, `28.4`, `58.2`, `118` and `237`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of a client certificate for the stage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<span class="property-indicator"></span>
        <span class="property-type">string | Deployment</span>
    </dt>
    <dd>{{% md %}}The ID of the deployment that the stage points to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">documentation<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the associated API documentation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">execution<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The execution ARN to be used in [`lambda_permission`](https://www.terraform.io/docs/providers/aws/r/lambda_permission.html)&#39;s `source_arn`
when allowing API Gateway to invoke a Lambda function,
e.g. `arn:aws:execute-api:eu-west-2:123456789012:z4675bid1j/prod`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">invoke<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The URL to invoke the API pointing to the stage,
e.g. `https://z4675bid1j.execute-api.eu-west-2.amazonaws.com/prod`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rest<wbr>Api<span class="property-indicator"></span>
        <span class="property-type">string | RestApi</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stage<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">variables<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A map that defines the stage variables
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">xray<wbr>Tracing<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether active tracing with X-ray is enabled. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access_<wbr>log_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#stageaccesslogsettings">Dict[Stage<wbr>Access<wbr>Log<wbr>Settings]</a></span>
    </dt>
    <dd>{{% md %}}Enables access logs for the API stage. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache_<wbr>cluster_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a cache cluster is enabled for the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache_<wbr>cluster_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The size of the cache cluster for the stage, if enabled.
Allowed values include `0.5`, `1.6`, `6.1`, `13.5`, `28.4`, `58.2`, `118` and `237`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client_<wbr>certificate_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier of a client certificate for the stage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The ID of the deployment that the stage points to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">documentation_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of the associated API documentation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">execution_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The execution ARN to be used in [`lambda_permission`](https://www.terraform.io/docs/providers/aws/r/lambda_permission.html)&#39;s `source_arn`
when allowing API Gateway to invoke a Lambda function,
e.g. `arn:aws:execute-api:eu-west-2:123456789012:z4675bid1j/prod`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">invoke_<wbr>url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The URL to invoke the API pointing to the stage,
e.g. `https://z4675bid1j.execute-api.eu-west-2.amazonaws.com/prod`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rest_<wbr>api<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The ID of the associated REST API
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stage_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the stage
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">variables<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A map that defines the stage variables
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">xray_<wbr>tracing_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether active tracing with X-ray is enabled. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### StageAccessLogSettings
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#StageAccessLogSettings">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#StageAccessLogSettings">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#StageAccessLogSettingsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#StageAccessLogSettingsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.StageAccessLogSettingsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.StageAccessLogSettings.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Destination<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the CloudWatch Logs log group or Kinesis Data Firehose delivery stream to receive access logs. If you specify a Kinesis Data Firehose delivery stream, the stream name must begin with `amazon-apigateway-`. Automatically removes trailing `:*` if present.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Format<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The formatting and values recorded in the logs. 
For more information on configuring the log format rules visit the AWS [documentation](https://docs.aws.amazon.com/apigateway/latest/developerguide/set-up-logging.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Destination<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the CloudWatch Logs log group or Kinesis Data Firehose delivery stream to receive access logs. If you specify a Kinesis Data Firehose delivery stream, the stream name must begin with `amazon-apigateway-`. Automatically removes trailing `:*` if present.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Format<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The formatting and values recorded in the logs. 
For more information on configuring the log format rules visit the AWS [documentation](https://docs.aws.amazon.com/apigateway/latest/developerguide/set-up-logging.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">destination<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the CloudWatch Logs log group or Kinesis Data Firehose delivery stream to receive access logs. If you specify a Kinesis Data Firehose delivery stream, the stream name must begin with `amazon-apigateway-`. Automatically removes trailing `:*` if present.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">format<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The formatting and values recorded in the logs. 
For more information on configuring the log format rules visit the AWS [documentation](https://docs.aws.amazon.com/apigateway/latest/developerguide/set-up-logging.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">destination_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the CloudWatch Logs log group or Kinesis Data Firehose delivery stream to receive access logs. If you specify a Kinesis Data Firehose delivery stream, the stream name must begin with `amazon-apigateway-`. Automatically removes trailing `:*` if present.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">format<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The formatting and values recorded in the logs. 
For more information on configuring the log format rules visit the AWS [documentation](https://docs.aws.amazon.com/apigateway/latest/developerguide/set-up-logging.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








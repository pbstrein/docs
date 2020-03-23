
---
title: "Permission"
block_external_search_index: true
---

Creates a Lambda permission to allow external sources invoking the Lambda function
(e.g. CloudWatch Event Rule, SNS or S3).

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const iamForLambda = new aws.iam.Role("iam_for_lambda", {
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
const testLambda = new aws.lambda.Function("test_lambda", {
    code: new pulumi.asset.FileArchive("lambdatest.zip"),
    handler: "exports.handler",
    role: iamForLambda.arn,
    runtime: "nodejs8.10",
});
const testAlias = new aws.lambda.Alias("test_alias", {
    description: "a sample description",
    functionName: testLambda.functionName,
    functionVersion: "$LATEST",
});
const allowCloudwatch = new aws.lambda.Permission("allow_cloudwatch", {
    action: "lambda:InvokeFunction",
    function: testLambda.functionName,
    principal: "events.amazonaws.com",
    qualifier: testAlias.name,
    sourceArn: "arn:aws:events:eu-west-1:111122223333:rule/RunDaily",
});
```

## Usage with SNS

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const defaultTopic = new aws.sns.Topic("default", {});
const defaultRole = new aws.iam.Role("default", {
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
const func = new aws.lambda.Function("func", {
    code: new pulumi.asset.FileArchive("lambdatest.zip"),
    handler: "exports.handler",
    role: defaultRole.arn,
    runtime: "python2.7",
});
const withSns = new aws.lambda.Permission("with_sns", {
    action: "lambda:InvokeFunction",
    function: func.functionName,
    principal: "sns.amazonaws.com",
    sourceArn: defaultTopic.arn,
});
const lambda = new aws.sns.TopicSubscription("lambda", {
    endpoint: func.arn,
    protocol: "lambda",
    topic: defaultTopic.arn,
});
```

## Specify Lambda permissions for API Gateway REST API

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const myDemoAPI = new aws.apigateway.RestApi("MyDemoAPI", {
    description: "This is my API for demonstration purposes",
});
const lambdaPermission = new aws.lambda.Permission("lambda_permission", {
    action: "lambda:InvokeFunction",
    function: "MyDemoFunction",
    principal: "apigateway.amazonaws.com",
    sourceArn: pulumi.interpolate`${myDemoAPI.executionArn}/*/*/*`,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/lambda_permission.html.markdown.



## Create a Permission Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#Permission">Permission</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#PermissionArgs">PermissionArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Permission</span><span class="p">(resource_name, opts=None, </span>action=None<span class="p">, </span>event_source_token=None<span class="p">, </span>function=None<span class="p">, </span>principal=None<span class="p">, </span>qualifier=None<span class="p">, </span>source_account=None<span class="p">, </span>source_arn=None<span class="p">, </span>statement_id=None<span class="p">, </span>statement_id_prefix=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewPermission<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#PermissionArgs">PermissionArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#Permission">Permission</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.Permission.html">Permission</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.PermissionArgs.html">PermissionArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS Lambda action you want to allow in this statement. (e.g. `lambda:InvokeFunction`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Event<wbr>Source<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Event Source Token to validate.  Used with [Alexa Skills][1].
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Function<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Lambda function whose resource policy you are updating
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Principal<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The principal who is getting this permission.
e.g. `s3.amazonaws.com`, an AWS account ID, or any valid AWS service principal
such as `events.amazonaws.com` or `sns.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Query parameter to specify function version or alias name.
The permission will then apply to the specific qualified ARN.
e.g. `arn:aws:lambda:aws-region:acct-id:function:function-name:2`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}This parameter is used for S3 and SES. The AWS account ID (without a hyphen) of the source owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When granting Amazon S3 or CloudWatch Events permission to
invoke your function, you should specify this field with the Amazon Resource Name (ARN)
for the S3 Bucket or CloudWatch Events Rule as its value.  This ensures that only events
generated from the specified bucket or rule can invoke the function.
API Gateway ARNs have a unique structure described
[here](http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-control-access-using-iam-policies-to-invoke-api.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Statement<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique statement identifier. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Statement<wbr>Id<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A statement identifier prefix. This provider will generate a unique suffix. Conflicts with `statement_id`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS Lambda action you want to allow in this statement. (e.g. `lambda:InvokeFunction`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Event<wbr>Source<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Event Source Token to validate.  Used with [Alexa Skills][1].
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Function<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}Name of the Lambda function whose resource policy you are updating
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Principal<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The principal who is getting this permission.
e.g. `s3.amazonaws.com`, an AWS account ID, or any valid AWS service principal
such as `events.amazonaws.com` or `sns.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Qualifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Query parameter to specify function version or alias name.
The permission will then apply to the specific qualified ARN.
e.g. `arn:aws:lambda:aws-region:acct-id:function:function-name:2`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}This parameter is used for S3 and SES. The AWS account ID (without a hyphen) of the source owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}When granting Amazon S3 or CloudWatch Events permission to
invoke your function, you should specify this field with the Amazon Resource Name (ARN)
for the S3 Bucket or CloudWatch Events Rule as its value.  This ensures that only events
generated from the specified bucket or rule can invoke the function.
API Gateway ARNs have a unique structure described
[here](http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-control-access-using-iam-policies-to-invoke-api.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Statement<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A unique statement identifier. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Statement<wbr>Id<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A statement identifier prefix. This provider will generate a unique suffix. Conflicts with `statement_id`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS Lambda action you want to allow in this statement. (e.g. `lambda:InvokeFunction`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">event<wbr>Source<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Event Source Token to validate.  Used with [Alexa Skills][1].
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">function<span class="property-indicator"></span>
        <span class="property-type">string | Function</span>
    </dt>
    <dd>{{% md %}}Name of the Lambda function whose resource policy you are updating
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">principal<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The principal who is getting this permission.
e.g. `s3.amazonaws.com`, an AWS account ID, or any valid AWS service principal
such as `events.amazonaws.com` or `sns.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Query parameter to specify function version or alias name.
The permission will then apply to the specific qualified ARN.
e.g. `arn:aws:lambda:aws-region:acct-id:function:function-name:2`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}This parameter is used for S3 and SES. The AWS account ID (without a hyphen) of the source owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When granting Amazon S3 or CloudWatch Events permission to
invoke your function, you should specify this field with the Amazon Resource Name (ARN)
for the S3 Bucket or CloudWatch Events Rule as its value.  This ensures that only events
generated from the specified bucket or rule can invoke the function.
API Gateway ARNs have a unique structure described
[here](http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-control-access-using-iam-policies-to-invoke-api.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">statement<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique statement identifier. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">statement<wbr>Id<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A statement identifier prefix. This provider will generate a unique suffix. Conflicts with `statement_id`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS Lambda action you want to allow in this statement. (e.g. `lambda:InvokeFunction`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">event_<wbr>source_<wbr>token<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Event Source Token to validate.  Used with [Alexa Skills][1].
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">function<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Name of the Lambda function whose resource policy you are updating
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">principal<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The principal who is getting this permission.
e.g. `s3.amazonaws.com`, an AWS account ID, or any valid AWS service principal
such as `events.amazonaws.com` or `sns.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">qualifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Query parameter to specify function version or alias name.
The permission will then apply to the specific qualified ARN.
e.g. `arn:aws:lambda:aws-region:acct-id:function:function-name:2`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>account<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}This parameter is used for S3 and SES. The AWS account ID (without a hyphen) of the source owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When granting Amazon S3 or CloudWatch Events permission to
invoke your function, you should specify this field with the Amazon Resource Name (ARN)
for the S3 Bucket or CloudWatch Events Rule as its value.  This ensures that only events
generated from the specified bucket or rule can invoke the function.
API Gateway ARNs have a unique structure described
[here](http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-control-access-using-iam-policies-to-invoke-api.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">statement_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique statement identifier. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">statement_<wbr>id_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A statement identifier prefix. This provider will generate a unique suffix. Conflicts with `statement_id`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Permission Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS Lambda action you want to allow in this statement. (e.g. `lambda:InvokeFunction`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Event<wbr>Source<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Event Source Token to validate.  Used with [Alexa Skills][1].
{{% /md %}}</dd>

    <dt class="property-"
            title="">Function<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Lambda function whose resource policy you are updating
{{% /md %}}</dd>

    <dt class="property-"
            title="">Principal<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The principal who is getting this permission.
e.g. `s3.amazonaws.com`, an AWS account ID, or any valid AWS service principal
such as `events.amazonaws.com` or `sns.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Query parameter to specify function version or alias name.
The permission will then apply to the specific qualified ARN.
e.g. `arn:aws:lambda:aws-region:acct-id:function:function-name:2`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}This parameter is used for S3 and SES. The AWS account ID (without a hyphen) of the source owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When granting Amazon S3 or CloudWatch Events permission to
invoke your function, you should specify this field with the Amazon Resource Name (ARN)
for the S3 Bucket or CloudWatch Events Rule as its value.  This ensures that only events
generated from the specified bucket or rule can invoke the function.
API Gateway ARNs have a unique structure described
[here](http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-control-access-using-iam-policies-to-invoke-api.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Statement<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique statement identifier. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Statement<wbr>Id<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A statement identifier prefix. This provider will generate a unique suffix. Conflicts with `statement_id`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS Lambda action you want to allow in this statement. (e.g. `lambda:InvokeFunction`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Event<wbr>Source<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Event Source Token to validate.  Used with [Alexa Skills][1].
{{% /md %}}</dd>

    <dt class="property-"
            title="">Function<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Lambda function whose resource policy you are updating
{{% /md %}}</dd>

    <dt class="property-"
            title="">Principal<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The principal who is getting this permission.
e.g. `s3.amazonaws.com`, an AWS account ID, or any valid AWS service principal
such as `events.amazonaws.com` or `sns.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Qualifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Query parameter to specify function version or alias name.
The permission will then apply to the specific qualified ARN.
e.g. `arn:aws:lambda:aws-region:acct-id:function:function-name:2`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}This parameter is used for S3 and SES. The AWS account ID (without a hyphen) of the source owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}When granting Amazon S3 or CloudWatch Events permission to
invoke your function, you should specify this field with the Amazon Resource Name (ARN)
for the S3 Bucket or CloudWatch Events Rule as its value.  This ensures that only events
generated from the specified bucket or rule can invoke the function.
API Gateway ARNs have a unique structure described
[here](http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-control-access-using-iam-policies-to-invoke-api.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Statement<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique statement identifier. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Statement<wbr>Id<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A statement identifier prefix. This provider will generate a unique suffix. Conflicts with `statement_id`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS Lambda action you want to allow in this statement. (e.g. `lambda:InvokeFunction`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">event<wbr>Source<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Event Source Token to validate.  Used with [Alexa Skills][1].
{{% /md %}}</dd>

    <dt class="property-"
            title="">function<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Lambda function whose resource policy you are updating
{{% /md %}}</dd>

    <dt class="property-"
            title="">principal<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The principal who is getting this permission.
e.g. `s3.amazonaws.com`, an AWS account ID, or any valid AWS service principal
such as `events.amazonaws.com` or `sns.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Query parameter to specify function version or alias name.
The permission will then apply to the specific qualified ARN.
e.g. `arn:aws:lambda:aws-region:acct-id:function:function-name:2`
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}This parameter is used for S3 and SES. The AWS account ID (without a hyphen) of the source owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When granting Amazon S3 or CloudWatch Events permission to
invoke your function, you should specify this field with the Amazon Resource Name (ARN)
for the S3 Bucket or CloudWatch Events Rule as its value.  This ensures that only events
generated from the specified bucket or rule can invoke the function.
API Gateway ARNs have a unique structure described
[here](http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-control-access-using-iam-policies-to-invoke-api.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">statement<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique statement identifier. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">statement<wbr>Id<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A statement identifier prefix. This provider will generate a unique suffix. Conflicts with `statement_id`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS Lambda action you want to allow in this statement. (e.g. `lambda:InvokeFunction`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">event_<wbr>source_<wbr>token<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Event Source Token to validate.  Used with [Alexa Skills][1].
{{% /md %}}</dd>

    <dt class="property-"
            title="">function<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the Lambda function whose resource policy you are updating
{{% /md %}}</dd>

    <dt class="property-"
            title="">principal<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The principal who is getting this permission.
e.g. `s3.amazonaws.com`, an AWS account ID, or any valid AWS service principal
such as `events.amazonaws.com` or `sns.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">qualifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Query parameter to specify function version or alias name.
The permission will then apply to the specific qualified ARN.
e.g. `arn:aws:lambda:aws-region:acct-id:function:function-name:2`
{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>account<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}This parameter is used for S3 and SES. The AWS account ID (without a hyphen) of the source owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When granting Amazon S3 or CloudWatch Events permission to
invoke your function, you should specify this field with the Amazon Resource Name (ARN)
for the S3 Bucket or CloudWatch Events Rule as its value.  This ensures that only events
generated from the specified bucket or rule can invoke the function.
API Gateway ARNs have a unique structure described
[here](http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-control-access-using-iam-policies-to-invoke-api.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">statement_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique statement identifier. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">statement_<wbr>id_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A statement identifier prefix. This provider will generate a unique suffix. Conflicts with `statement_id`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Permission Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#PermissionState">PermissionState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#Permission">Permission</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>action=None<span class="p">, </span>event_source_token=None<span class="p">, </span>function=None<span class="p">, </span>principal=None<span class="p">, </span>qualifier=None<span class="p">, </span>source_account=None<span class="p">, </span>source_arn=None<span class="p">, </span>statement_id=None<span class="p">, </span>statement_id_prefix=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetPermission<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#PermissionState">PermissionState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#Permission">Permission</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.Permission.html">Permission</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.PermissionState.html">PermissionState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Permission resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Action<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Lambda action you want to allow in this statement. (e.g. `lambda:InvokeFunction`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Event<wbr>Source<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Event Source Token to validate.  Used with [Alexa Skills][1].
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Function<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the Lambda function whose resource policy you are updating
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Principal<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The principal who is getting this permission.
e.g. `s3.amazonaws.com`, an AWS account ID, or any valid AWS service principal
such as `events.amazonaws.com` or `sns.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Query parameter to specify function version or alias name.
The permission will then apply to the specific qualified ARN.
e.g. `arn:aws:lambda:aws-region:acct-id:function:function-name:2`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}This parameter is used for S3 and SES. The AWS account ID (without a hyphen) of the source owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When granting Amazon S3 or CloudWatch Events permission to
invoke your function, you should specify this field with the Amazon Resource Name (ARN)
for the S3 Bucket or CloudWatch Events Rule as its value.  This ensures that only events
generated from the specified bucket or rule can invoke the function.
API Gateway ARNs have a unique structure described
[here](http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-control-access-using-iam-policies-to-invoke-api.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Statement<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique statement identifier. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Statement<wbr>Id<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A statement identifier prefix. This provider will generate a unique suffix. Conflicts with `statement_id`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Action<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS Lambda action you want to allow in this statement. (e.g. `lambda:InvokeFunction`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Event<wbr>Source<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Event Source Token to validate.  Used with [Alexa Skills][1].
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Function<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}Name of the Lambda function whose resource policy you are updating
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Principal<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The principal who is getting this permission.
e.g. `s3.amazonaws.com`, an AWS account ID, or any valid AWS service principal
such as `events.amazonaws.com` or `sns.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Qualifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Query parameter to specify function version or alias name.
The permission will then apply to the specific qualified ARN.
e.g. `arn:aws:lambda:aws-region:acct-id:function:function-name:2`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}This parameter is used for S3 and SES. The AWS account ID (without a hyphen) of the source owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}When granting Amazon S3 or CloudWatch Events permission to
invoke your function, you should specify this field with the Amazon Resource Name (ARN)
for the S3 Bucket or CloudWatch Events Rule as its value.  This ensures that only events
generated from the specified bucket or rule can invoke the function.
API Gateway ARNs have a unique structure described
[here](http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-control-access-using-iam-policies-to-invoke-api.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Statement<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A unique statement identifier. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Statement<wbr>Id<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A statement identifier prefix. This provider will generate a unique suffix. Conflicts with `statement_id`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">action<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Lambda action you want to allow in this statement. (e.g. `lambda:InvokeFunction`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">event<wbr>Source<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Event Source Token to validate.  Used with [Alexa Skills][1].
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">function<span class="property-indicator"></span>
        <span class="property-type">string | Function</span>
    </dt>
    <dd>{{% md %}}Name of the Lambda function whose resource policy you are updating
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">principal<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The principal who is getting this permission.
e.g. `s3.amazonaws.com`, an AWS account ID, or any valid AWS service principal
such as `events.amazonaws.com` or `sns.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Query parameter to specify function version or alias name.
The permission will then apply to the specific qualified ARN.
e.g. `arn:aws:lambda:aws-region:acct-id:function:function-name:2`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}This parameter is used for S3 and SES. The AWS account ID (without a hyphen) of the source owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When granting Amazon S3 or CloudWatch Events permission to
invoke your function, you should specify this field with the Amazon Resource Name (ARN)
for the S3 Bucket or CloudWatch Events Rule as its value.  This ensures that only events
generated from the specified bucket or rule can invoke the function.
API Gateway ARNs have a unique structure described
[here](http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-control-access-using-iam-policies-to-invoke-api.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">statement<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique statement identifier. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">statement<wbr>Id<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A statement identifier prefix. This provider will generate a unique suffix. Conflicts with `statement_id`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS Lambda action you want to allow in this statement. (e.g. `lambda:InvokeFunction`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">event_<wbr>source_<wbr>token<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Event Source Token to validate.  Used with [Alexa Skills][1].
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">function<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Name of the Lambda function whose resource policy you are updating
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">principal<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The principal who is getting this permission.
e.g. `s3.amazonaws.com`, an AWS account ID, or any valid AWS service principal
such as `events.amazonaws.com` or `sns.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">qualifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Query parameter to specify function version or alias name.
The permission will then apply to the specific qualified ARN.
e.g. `arn:aws:lambda:aws-region:acct-id:function:function-name:2`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>account<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}This parameter is used for S3 and SES. The AWS account ID (without a hyphen) of the source owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When granting Amazon S3 or CloudWatch Events permission to
invoke your function, you should specify this field with the Amazon Resource Name (ARN)
for the S3 Bucket or CloudWatch Events Rule as its value.  This ensures that only events
generated from the specified bucket or rule can invoke the function.
API Gateway ARNs have a unique structure described
[here](http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-control-access-using-iam-policies-to-invoke-api.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">statement_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique statement identifier. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">statement_<wbr>id_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A statement identifier prefix. This provider will generate a unique suffix. Conflicts with `statement_id`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







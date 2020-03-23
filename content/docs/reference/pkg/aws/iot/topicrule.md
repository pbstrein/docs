
---
title: "TopicRule"
block_external_search_index: true
---

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const mytopic = new aws.sns.Topic("mytopic", {});
const role = new aws.iam.Role("role", {
    assumeRolePolicy: `{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "iot.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
`,
});
const rule = new aws.iot.TopicRule("rule", {
    description: "Example rule",
    enabled: true,
    sns: {
        messageFormat: "RAW",
        roleArn: role.arn,
        targetArn: mytopic.arn,
    },
    sql: "SELECT * FROM 'topic/test'",
    sqlVersion: "2015-10-08",
});
const iamPolicyForLambda = new aws.iam.RolePolicy("iam_policy_for_lambda", {
    policy: pulumi.interpolate`{
  "Version": "2012-10-17",
  "Statement": [
    {
        "Effect": "Allow",
        "Action": [
            "sns:Publish"
        ],
        "Resource": "${mytopic.arn}"
    }
  ]
}
`,
    role: role.id,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/iot_topic_rule.html.markdown.



## Create a TopicRule Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/iot/#TopicRule">TopicRule</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/iot/#TopicRuleArgs">TopicRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">TopicRule</span><span class="p">(resource_name, opts=None, </span>cloudwatch_alarm=None<span class="p">, </span>cloudwatch_metric=None<span class="p">, </span>description=None<span class="p">, </span>dynamodb=None<span class="p">, </span>elasticsearch=None<span class="p">, </span>enabled=None<span class="p">, </span>firehose=None<span class="p">, </span>kinesis=None<span class="p">, </span>lambda_=None<span class="p">, </span>name=None<span class="p">, </span>republish=None<span class="p">, </span>s3=None<span class="p">, </span>sns=None<span class="p">, </span>sql=None<span class="p">, </span>sql_version=None<span class="p">, </span>sqs=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewTopicRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleArgs">TopicRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRule">TopicRule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRule.html">TopicRule</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleArgs.html">TopicRuleArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Cloudwatch<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchalarm">Topic<wbr>Rule<wbr>Cloudwatch<wbr>Alarm<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloudwatch<wbr>Metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchmetric">Topic<wbr>Rule<wbr>Cloudwatch<wbr>Metric<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dynamodb<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruledynamodb">Topic<wbr>Rule<wbr>Dynamodb<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elasticsearch<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruleelasticsearch">Topic<wbr>Rule<wbr>Elasticsearch<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the rule is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulefirehose">Topic<wbr>Rule<wbr>Firehose<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulekinesis">Topic<wbr>Rule<wbr>Kinesis<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulelambda">Topic<wbr>Rule<wbr>Lambda<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Republish<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulerepublish">Topic<wbr>Rule<wbr>Republish<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrules3">Topic<wbr>Rule<wbr>S3Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesns">Topic<wbr>Rule<wbr>Sns<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sql<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The SQL statement used to query the topic. For more information, see AWS IoT SQL Reference (http://docs.aws.amazon.com/iot/latest/developerguide/iot-rules.html#aws-iot-sql-reference) in the AWS IoT Developer Guide.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sql<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the SQL rules engine to use when evaluating the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesqs">Topic<wbr>Rule<wbr>Sqs<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cloudwatch<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchalarm">*Topic<wbr>Rule<wbr>Cloudwatch<wbr>Alarm</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloudwatch<wbr>Metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchmetric">*Topic<wbr>Rule<wbr>Cloudwatch<wbr>Metric</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dynamodb<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruledynamodb">*Topic<wbr>Rule<wbr>Dynamodb</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elasticsearch<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruleelasticsearch">*Topic<wbr>Rule<wbr>Elasticsearch</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the rule is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulefirehose">*Topic<wbr>Rule<wbr>Firehose</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulekinesis">*Topic<wbr>Rule<wbr>Kinesis</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulelambda">*Topic<wbr>Rule<wbr>Lambda</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Republish<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulerepublish">*Topic<wbr>Rule<wbr>Republish</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrules3">*Topic<wbr>Rule<wbr>S3</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesns">*Topic<wbr>Rule<wbr>Sns</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sql<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The SQL statement used to query the topic. For more information, see AWS IoT SQL Reference (http://docs.aws.amazon.com/iot/latest/developerguide/iot-rules.html#aws-iot-sql-reference) in the AWS IoT Developer Guide.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sql<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the SQL rules engine to use when evaluating the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesqs">*Topic<wbr>Rule<wbr>Sqs</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cloudwatch<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchalarm">Topic<wbr>Rule<wbr>Cloudwatch<wbr>Alarm?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloudwatch<wbr>Metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchmetric">Topic<wbr>Rule<wbr>Cloudwatch<wbr>Metric?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dynamodb<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruledynamodb">Topic<wbr>Rule<wbr>Dynamodb?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elasticsearch<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruleelasticsearch">Topic<wbr>Rule<wbr>Elasticsearch?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Specifies whether the rule is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulefirehose">Topic<wbr>Rule<wbr>Firehose?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulekinesis">Topic<wbr>Rule<wbr>Kinesis?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulelambda">Topic<wbr>Rule<wbr>Lambda?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">republish<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulerepublish">Topic<wbr>Rule<wbr>Republish?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrules3">Topic<wbr>Rule<wbr>S3?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesns">Topic<wbr>Rule<wbr>Sns?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sql<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The SQL statement used to query the topic. For more information, see AWS IoT SQL Reference (http://docs.aws.amazon.com/iot/latest/developerguide/iot-rules.html#aws-iot-sql-reference) in the AWS IoT Developer Guide.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sql<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the SQL rules engine to use when evaluating the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesqs">Topic<wbr>Rule<wbr>Sqs?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cloudwatch_<wbr>alarm<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchalarm">Dict[Topic<wbr>Rule<wbr>Cloudwatch<wbr>Alarm]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloudwatch_<wbr>metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchmetric">Dict[Topic<wbr>Rule<wbr>Cloudwatch<wbr>Metric]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dynamodb<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruledynamodb">Dict[Topic<wbr>Rule<wbr>Dynamodb]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elasticsearch<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruleelasticsearch">Dict[Topic<wbr>Rule<wbr>Elasticsearch]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the rule is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulefirehose">Dict[Topic<wbr>Rule<wbr>Firehose]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulekinesis">Dict[Topic<wbr>Rule<wbr>Kinesis]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulelambda">Dict[Topic<wbr>Rule<wbr>Lambda]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">republish<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulerepublish">Dict[Topic<wbr>Rule<wbr>Republish]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrules3">Dict[Topic<wbr>Rule<wbr>S3]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesns">Dict[Topic<wbr>Rule<wbr>Sns]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sql<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The SQL statement used to query the topic. For more information, see AWS IoT SQL Reference (http://docs.aws.amazon.com/iot/latest/developerguide/iot-rules.html#aws-iot-sql-reference) in the AWS IoT Developer Guide.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sql_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of the SQL rules engine to use when evaluating the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesqs">Dict[Topic<wbr>Rule<wbr>Sqs]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## TopicRule Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the topic rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cloudwatch<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchalarm">Topic<wbr>Rule<wbr>Cloudwatch<wbr>Alarm?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Cloudwatch<wbr>Metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchmetric">Topic<wbr>Rule<wbr>Cloudwatch<wbr>Metric?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dynamodb<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruledynamodb">Topic<wbr>Rule<wbr>Dynamodb?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Elasticsearch<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruleelasticsearch">Topic<wbr>Rule<wbr>Elasticsearch?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the rule is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulefirehose">Topic<wbr>Rule<wbr>Firehose?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Kinesis<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulekinesis">Topic<wbr>Rule<wbr>Kinesis?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulelambda">Topic<wbr>Rule<wbr>Lambda?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Republish<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulerepublish">Topic<wbr>Rule<wbr>Republish?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">S3<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrules3">Topic<wbr>Rule<wbr>S3?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Sns<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesns">Topic<wbr>Rule<wbr>Sns?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Sql<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The SQL statement used to query the topic. For more information, see AWS IoT SQL Reference (http://docs.aws.amazon.com/iot/latest/developerguide/iot-rules.html#aws-iot-sql-reference) in the AWS IoT Developer Guide.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sql<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the SQL rules engine to use when evaluating the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sqs<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesqs">Topic<wbr>Rule<wbr>Sqs?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the topic rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cloudwatch<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchalarm">*Topic<wbr>Rule<wbr>Cloudwatch<wbr>Alarm</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Cloudwatch<wbr>Metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchmetric">*Topic<wbr>Rule<wbr>Cloudwatch<wbr>Metric</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dynamodb<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruledynamodb">*Topic<wbr>Rule<wbr>Dynamodb</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Elasticsearch<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruleelasticsearch">*Topic<wbr>Rule<wbr>Elasticsearch</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the rule is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulefirehose">*Topic<wbr>Rule<wbr>Firehose</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Kinesis<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulekinesis">*Topic<wbr>Rule<wbr>Kinesis</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulelambda">*Topic<wbr>Rule<wbr>Lambda</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Republish<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulerepublish">*Topic<wbr>Rule<wbr>Republish</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">S3<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrules3">*Topic<wbr>Rule<wbr>S3</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Sns<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesns">*Topic<wbr>Rule<wbr>Sns</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Sql<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The SQL statement used to query the topic. For more information, see AWS IoT SQL Reference (http://docs.aws.amazon.com/iot/latest/developerguide/iot-rules.html#aws-iot-sql-reference) in the AWS IoT Developer Guide.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sql<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the SQL rules engine to use when evaluating the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sqs<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesqs">*Topic<wbr>Rule<wbr>Sqs</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the topic rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">cloudwatch<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchalarm">Topic<wbr>Rule<wbr>Cloudwatch<wbr>Alarm?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">cloudwatch<wbr>Metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchmetric">Topic<wbr>Rule<wbr>Cloudwatch<wbr>Metric?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dynamodb<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruledynamodb">Topic<wbr>Rule<wbr>Dynamodb?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">elasticsearch<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruleelasticsearch">Topic<wbr>Rule<wbr>Elasticsearch?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Specifies whether the rule is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulefirehose">Topic<wbr>Rule<wbr>Firehose?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">kinesis<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulekinesis">Topic<wbr>Rule<wbr>Kinesis?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulelambda">Topic<wbr>Rule<wbr>Lambda?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">republish<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulerepublish">Topic<wbr>Rule<wbr>Republish?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">s3<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrules3">Topic<wbr>Rule<wbr>S3?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">sns<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesns">Topic<wbr>Rule<wbr>Sns?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">sql<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The SQL statement used to query the topic. For more information, see AWS IoT SQL Reference (http://docs.aws.amazon.com/iot/latest/developerguide/iot-rules.html#aws-iot-sql-reference) in the AWS IoT Developer Guide.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sql<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the SQL rules engine to use when evaluating the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sqs<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesqs">Topic<wbr>Rule<wbr>Sqs?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the topic rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">cloudwatch_<wbr>alarm<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchalarm">Dict[Topic<wbr>Rule<wbr>Cloudwatch<wbr>Alarm]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">cloudwatch_<wbr>metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchmetric">Dict[Topic<wbr>Rule<wbr>Cloudwatch<wbr>Metric]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dynamodb<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruledynamodb">Dict[Topic<wbr>Rule<wbr>Dynamodb]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">elasticsearch<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruleelasticsearch">Dict[Topic<wbr>Rule<wbr>Elasticsearch]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the rule is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulefirehose">Dict[Topic<wbr>Rule<wbr>Firehose]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">kinesis<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulekinesis">Dict[Topic<wbr>Rule<wbr>Kinesis]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda_<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulelambda">Dict[Topic<wbr>Rule<wbr>Lambda]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">republish<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulerepublish">Dict[Topic<wbr>Rule<wbr>Republish]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">s3<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrules3">Dict[Topic<wbr>Rule<wbr>S3]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">sns<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesns">Dict[Topic<wbr>Rule<wbr>Sns]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">sql<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The SQL statement used to query the topic. For more information, see AWS IoT SQL Reference (http://docs.aws.amazon.com/iot/latest/developerguide/iot-rules.html#aws-iot-sql-reference) in the AWS IoT Developer Guide.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sql_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of the SQL rules engine to use when evaluating the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sqs<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesqs">Dict[Topic<wbr>Rule<wbr>Sqs]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing TopicRule Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/iot/#TopicRuleState">TopicRuleState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/iot/#TopicRule">TopicRule</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>cloudwatch_alarm=None<span class="p">, </span>cloudwatch_metric=None<span class="p">, </span>description=None<span class="p">, </span>dynamodb=None<span class="p">, </span>elasticsearch=None<span class="p">, </span>enabled=None<span class="p">, </span>firehose=None<span class="p">, </span>kinesis=None<span class="p">, </span>lambda_=None<span class="p">, </span>name=None<span class="p">, </span>republish=None<span class="p">, </span>s3=None<span class="p">, </span>sns=None<span class="p">, </span>sql=None<span class="p">, </span>sql_version=None<span class="p">, </span>sqs=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetTopicRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleState">TopicRuleState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRule">TopicRule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRule.html">TopicRule</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleState.html">TopicRuleState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing TopicRule resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The ARN of the topic rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloudwatch<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchalarm">Topic<wbr>Rule<wbr>Cloudwatch<wbr>Alarm<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloudwatch<wbr>Metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchmetric">Topic<wbr>Rule<wbr>Cloudwatch<wbr>Metric<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dynamodb<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruledynamodb">Topic<wbr>Rule<wbr>Dynamodb<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elasticsearch<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruleelasticsearch">Topic<wbr>Rule<wbr>Elasticsearch<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the rule is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulefirehose">Topic<wbr>Rule<wbr>Firehose<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulekinesis">Topic<wbr>Rule<wbr>Kinesis<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulelambda">Topic<wbr>Rule<wbr>Lambda<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Republish<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulerepublish">Topic<wbr>Rule<wbr>Republish<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrules3">Topic<wbr>Rule<wbr>S3Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesns">Topic<wbr>Rule<wbr>Sns<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sql<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The SQL statement used to query the topic. For more information, see AWS IoT SQL Reference (http://docs.aws.amazon.com/iot/latest/developerguide/iot-rules.html#aws-iot-sql-reference) in the AWS IoT Developer Guide.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sql<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the SQL rules engine to use when evaluating the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesqs">Topic<wbr>Rule<wbr>Sqs<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the topic rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloudwatch<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchalarm">*Topic<wbr>Rule<wbr>Cloudwatch<wbr>Alarm</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloudwatch<wbr>Metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchmetric">*Topic<wbr>Rule<wbr>Cloudwatch<wbr>Metric</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dynamodb<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruledynamodb">*Topic<wbr>Rule<wbr>Dynamodb</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elasticsearch<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruleelasticsearch">*Topic<wbr>Rule<wbr>Elasticsearch</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the rule is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulefirehose">*Topic<wbr>Rule<wbr>Firehose</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulekinesis">*Topic<wbr>Rule<wbr>Kinesis</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulelambda">*Topic<wbr>Rule<wbr>Lambda</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Republish<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulerepublish">*Topic<wbr>Rule<wbr>Republish</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrules3">*Topic<wbr>Rule<wbr>S3</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesns">*Topic<wbr>Rule<wbr>Sns</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sql<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The SQL statement used to query the topic. For more information, see AWS IoT SQL Reference (http://docs.aws.amazon.com/iot/latest/developerguide/iot-rules.html#aws-iot-sql-reference) in the AWS IoT Developer Guide.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sql<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version of the SQL rules engine to use when evaluating the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesqs">*Topic<wbr>Rule<wbr>Sqs</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the topic rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloudwatch<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchalarm">Topic<wbr>Rule<wbr>Cloudwatch<wbr>Alarm?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloudwatch<wbr>Metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchmetric">Topic<wbr>Rule<wbr>Cloudwatch<wbr>Metric?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dynamodb<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruledynamodb">Topic<wbr>Rule<wbr>Dynamodb?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elasticsearch<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruleelasticsearch">Topic<wbr>Rule<wbr>Elasticsearch?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the rule is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulefirehose">Topic<wbr>Rule<wbr>Firehose?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulekinesis">Topic<wbr>Rule<wbr>Kinesis?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulelambda">Topic<wbr>Rule<wbr>Lambda?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">republish<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulerepublish">Topic<wbr>Rule<wbr>Republish?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrules3">Topic<wbr>Rule<wbr>S3?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesns">Topic<wbr>Rule<wbr>Sns?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sql<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The SQL statement used to query the topic. For more information, see AWS IoT SQL Reference (http://docs.aws.amazon.com/iot/latest/developerguide/iot-rules.html#aws-iot-sql-reference) in the AWS IoT Developer Guide.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sql<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the SQL rules engine to use when evaluating the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesqs">Topic<wbr>Rule<wbr>Sqs?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the topic rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloudwatch_<wbr>alarm<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchalarm">Dict[Topic<wbr>Rule<wbr>Cloudwatch<wbr>Alarm]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloudwatch_<wbr>metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulecloudwatchmetric">Dict[Topic<wbr>Rule<wbr>Cloudwatch<wbr>Metric]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dynamodb<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruledynamodb">Dict[Topic<wbr>Rule<wbr>Dynamodb]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elasticsearch<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicruleelasticsearch">Dict[Topic<wbr>Rule<wbr>Elasticsearch]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the rule is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">firehose<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulefirehose">Dict[Topic<wbr>Rule<wbr>Firehose]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulekinesis">Dict[Topic<wbr>Rule<wbr>Kinesis]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulelambda">Dict[Topic<wbr>Rule<wbr>Lambda]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">republish<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulerepublish">Dict[Topic<wbr>Rule<wbr>Republish]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrules3">Dict[Topic<wbr>Rule<wbr>S3]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesns">Dict[Topic<wbr>Rule<wbr>Sns]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sql<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The SQL statement used to query the topic. For more information, see AWS IoT SQL Reference (http://docs.aws.amazon.com/iot/latest/developerguide/iot-rules.html#aws-iot-sql-reference) in the AWS IoT Developer Guide.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sql_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of the SQL rules engine to use when evaluating the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs<span class="property-indicator"></span>
        <span class="property-type"><a href="#topicrulesqs">Dict[Topic<wbr>Rule<wbr>Sqs]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### TopicRuleCloudwatchAlarm
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TopicRuleCloudwatchAlarm">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TopicRuleCloudwatchAlarm">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleCloudwatchAlarmArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleCloudwatchAlarmOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleCloudwatchAlarmArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleCloudwatchAlarm.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Alarm<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudWatch alarm name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">State<wbr>Reason<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The reason for the alarm change.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">State<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of the alarm state. Acceptable values are: OK, ALARM, INSUFFICIENT_DATA.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Alarm<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudWatch alarm name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">State<wbr>Reason<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The reason for the alarm change.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">State<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of the alarm state. Acceptable values are: OK, ALARM, INSUFFICIENT_DATA.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">alarm<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudWatch alarm name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">state<wbr>Reason<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The reason for the alarm change.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">state<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of the alarm state. Acceptable values are: OK, ALARM, INSUFFICIENT_DATA.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">alarm<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CloudWatch alarm name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">state<wbr>Reason<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The reason for the alarm change.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">state<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The value of the alarm state. Acceptable values are: OK, ALARM, INSUFFICIENT_DATA.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TopicRuleCloudwatchMetric
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TopicRuleCloudwatchMetric">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TopicRuleCloudwatchMetric">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleCloudwatchMetricArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleCloudwatchMetricOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleCloudwatchMetricArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleCloudwatchMetric.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudWatch metric name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Metric<wbr>Namespace<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudWatch metric namespace name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An optional Unix timestamp (http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/cloudwatch_concepts.html#about_timestamp).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Metric<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The metric unit (supported units can be found here: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/cloudwatch_concepts.html#Unit)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Metric<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudWatch metric value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudWatch metric name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Metric<wbr>Namespace<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudWatch metric namespace name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An optional Unix timestamp (http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/cloudwatch_concepts.html#about_timestamp).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Metric<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The metric unit (supported units can be found here: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/cloudwatch_concepts.html#Unit)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Metric<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudWatch metric value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudWatch metric name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">metric<wbr>Namespace<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudWatch metric namespace name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An optional Unix timestamp (http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/cloudwatch_concepts.html#about_timestamp).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">metric<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The metric unit (supported units can be found here: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/cloudwatch_concepts.html#Unit)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">metric<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudWatch metric value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">metric_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CloudWatch metric name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">metric<wbr>Namespace<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CloudWatch metric namespace name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric<wbr>Timestamp<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An optional Unix timestamp (http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/cloudwatch_concepts.html#about_timestamp).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">metric<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The metric unit (supported units can be found here: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/cloudwatch_concepts.html#Unit)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">metric<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CloudWatch metric value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TopicRuleDynamodb
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TopicRuleDynamodb">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TopicRuleDynamodb">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleDynamodbArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleDynamodbOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleDynamodbArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleDynamodb.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Hash<wbr>Key<wbr>Field<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The hash key name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hash<wbr>Key<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The hash key type. Valid values are &#34;STRING&#34; or &#34;NUMBER&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Hash<wbr>Key<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The hash key value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Payload<wbr>Field<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The action payload.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Range<wbr>Key<wbr>Field<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The range key name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Range<wbr>Key<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The range key type. Valid values are &#34;STRING&#34; or &#34;NUMBER&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Range<wbr>Key<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The range key value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Table<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the DynamoDB table.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Hash<wbr>Key<wbr>Field<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The hash key name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hash<wbr>Key<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The hash key type. Valid values are &#34;STRING&#34; or &#34;NUMBER&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Hash<wbr>Key<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The hash key value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Payload<wbr>Field<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The action payload.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Range<wbr>Key<wbr>Field<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The range key name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Range<wbr>Key<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The range key type. Valid values are &#34;STRING&#34; or &#34;NUMBER&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Range<wbr>Key<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The range key value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Table<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the DynamoDB table.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">hash<wbr>Key<wbr>Field<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The hash key name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hash<wbr>Key<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The hash key type. Valid values are &#34;STRING&#34; or &#34;NUMBER&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">hash<wbr>Key<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The hash key value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">payload<wbr>Field<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The action payload.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">range<wbr>Key<wbr>Field<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The range key name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">range<wbr>Key<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The range key type. Valid values are &#34;STRING&#34; or &#34;NUMBER&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">range<wbr>Key<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The range key value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">table<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the DynamoDB table.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">hash<wbr>Key<wbr>Field<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The hash key name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hash<wbr>Key<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The hash key type. Valid values are &#34;STRING&#34; or &#34;NUMBER&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">hash<wbr>Key<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The hash key value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">payload<wbr>Field<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The action payload.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">range<wbr>Key<wbr>Field<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The range key name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">range<wbr>Key<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The range key type. Valid values are &#34;STRING&#34; or &#34;NUMBER&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">range<wbr>Key<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The range key value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">table_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the DynamoDB table.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TopicRuleElasticsearch
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TopicRuleElasticsearch">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TopicRuleElasticsearch">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleElasticsearchArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleElasticsearchOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleElasticsearchArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleElasticsearch.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The endpoint of your Elasticsearch domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique identifier for the document you are storing.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Index<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Elasticsearch index where you want to store your data.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of document you are storing.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The endpoint of your Elasticsearch domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique identifier for the document you are storing.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Index<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Elasticsearch index where you want to store your data.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of document you are storing.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The endpoint of your Elasticsearch domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique identifier for the document you are storing.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">index<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Elasticsearch index where you want to store your data.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of document you are storing.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The endpoint of your Elasticsearch domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The unique identifier for the document you are storing.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">index<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Elasticsearch index where you want to store your data.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of document you are storing.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TopicRuleFirehose
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TopicRuleFirehose">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TopicRuleFirehose">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleFirehoseArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleFirehoseOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleFirehoseArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleFirehose.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Delivery<wbr>Stream<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The delivery stream name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Separator<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A character separator that is used to separate records written to the Firehose stream. Valid values are: &#39;\n&#39; (newline), &#39;\t&#39; (tab), &#39;\r\n&#39; (Windows newline), &#39;,&#39; (comma).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Delivery<wbr>Stream<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The delivery stream name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Separator<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A character separator that is used to separate records written to the Firehose stream. Valid values are: &#39;\n&#39; (newline), &#39;\t&#39; (tab), &#39;\r\n&#39; (Windows newline), &#39;,&#39; (comma).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">delivery<wbr>Stream<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The delivery stream name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">separator<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A character separator that is used to separate records written to the Firehose stream. Valid values are: &#39;\n&#39; (newline), &#39;\t&#39; (tab), &#39;\r\n&#39; (Windows newline), &#39;,&#39; (comma).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">delivery<wbr>Stream<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The delivery stream name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">separator<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A character separator that is used to separate records written to the Firehose stream. Valid values are: &#39;\n&#39; (newline), &#39;\t&#39; (tab), &#39;\r\n&#39; (Windows newline), &#39;,&#39; (comma).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TopicRuleKinesis
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TopicRuleKinesis">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TopicRuleKinesis">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleKinesisArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleKinesisOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleKinesisArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleKinesis.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Partition<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The partition key.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stream<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon Kinesis stream.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Partition<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The partition key.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stream<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon Kinesis stream.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">partition<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The partition key.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stream<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon Kinesis stream.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">partition<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The partition key.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stream<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon Kinesis stream.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TopicRuleLambda
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TopicRuleLambda">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TopicRuleLambda">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleLambdaArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleLambdaOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleLambdaArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleLambda.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Function<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Function<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">function<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">function_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TopicRuleRepublish
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TopicRuleRepublish">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TopicRuleRepublish">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleRepublishArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleRepublishOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleRepublishArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleRepublish.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Topic<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the MQTT topic the message should be republished to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Topic<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the MQTT topic the message should be republished to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">topic<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the MQTT topic the message should be republished to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">topic<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the MQTT topic the message should be republished to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TopicRuleS3
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TopicRuleS3">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TopicRuleS3">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleS3Args">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleS3Output">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleS3Args.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleS3.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The object key.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The object key.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The object key.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The object key.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TopicRuleSns
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TopicRuleSns">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TopicRuleSns">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleSnsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleSnsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleSnsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleSns.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Message<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The message format of the message to publish. Accepted values are &#34;JSON&#34; and &#34;RAW&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Message<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The message format of the message to publish. Accepted values are &#34;JSON&#34; and &#34;RAW&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">message<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The message format of the message to publish. Accepted values are &#34;JSON&#34; and &#34;RAW&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">message<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The message format of the message to publish. Accepted values are &#34;JSON&#34; and &#34;RAW&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TopicRuleSqs
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TopicRuleSqs">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TopicRuleSqs">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleSqsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iot?tab=doc#TopicRuleSqsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleSqsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iot.TopicRuleSqs.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Queue<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URL of the Amazon SQS queue.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Use<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether to use Base64 encoding.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Queue<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URL of the Amazon SQS queue.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Use<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether to use Base64 encoding.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">queue<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URL of the Amazon SQS queue.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">use<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Specifies whether to use Base64 encoding.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">queue_<wbr>url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The URL of the Amazon SQS queue.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that grants access.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">use<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether to use Base64 encoding.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








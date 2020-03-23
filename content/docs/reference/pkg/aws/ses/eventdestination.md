
---
title: "EventDestination"
block_external_search_index: true
---

Provides an SES event destination

## Example Usage

### CloudWatch Destination

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const cloudwatch = new aws.ses.EventDestination("cloudwatch", {
    cloudwatchDestinations: [{
        defaultValue: "default",
        dimensionName: "dimension",
        valueSource: "emailHeader",
    }],
    configurationSetName: aws_ses_configuration_set_example.name,
    enabled: true,
    matchingTypes: [
        "bounce",
        "send",
    ],
});
```

### Kinesis Destination

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const kinesis = new aws.ses.EventDestination("kinesis", {
    configurationSetName: aws_ses_configuration_set_example.name,
    enabled: true,
    kinesisDestination: {
        roleArn: aws_iam_role_example.arn,
        streamArn: aws_kinesis_firehose_delivery_stream_example.arn,
    },
    matchingTypes: [
        "bounce",
        "send",
    ],
});
```

### SNS Destination

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const sns = new aws.ses.EventDestination("sns", {
    configurationSetName: aws_ses_configuration_set_example.name,
    enabled: true,
    matchingTypes: [
        "bounce",
        "send",
    ],
    snsDestination: {
        topicArn: aws_sns_topic_example.arn,
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/ses_event_destination.markdown.



## Create a EventDestination Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ses/#EventDestination">EventDestination</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ses/#EventDestinationArgs">EventDestinationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">EventDestination</span><span class="p">(resource_name, opts=None, </span>cloudwatch_destinations=None<span class="p">, </span>configuration_set_name=None<span class="p">, </span>enabled=None<span class="p">, </span>kinesis_destination=None<span class="p">, </span>matching_types=None<span class="p">, </span>name=None<span class="p">, </span>sns_destination=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewEventDestination<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#EventDestinationArgs">EventDestinationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#EventDestination">EventDestination</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.EventDestination.html">EventDestination</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.EventDestinationArgs.html">EventDestinationArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Cloudwatch<wbr>Destinations<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationcloudwatchdestination">List&lt;Event<wbr>Destination<wbr>Cloudwatch<wbr>Destination<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}CloudWatch destination for the events
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Configuration<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the configuration set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the event destination will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationkinesisdestination">Event<wbr>Destination<wbr>Kinesis<wbr>Destination<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Send the events to a kinesis firehose destination
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Matching<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of matching types. May be any of `&#34;send&#34;`, `&#34;reject&#34;`, `&#34;bounce&#34;`, `&#34;complaint&#34;`, `&#34;delivery&#34;`, `&#34;open&#34;`, `&#34;click&#34;`, or `&#34;renderingFailure&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the event destination
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationsnsdestination">Event<wbr>Destination<wbr>Sns<wbr>Destination<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Send the events to an SNS Topic destination
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cloudwatch<wbr>Destinations<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationcloudwatchdestination">[]Event<wbr>Destination<wbr>Cloudwatch<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}CloudWatch destination for the events
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Configuration<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the configuration set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the event destination will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationkinesisdestination">*Event<wbr>Destination<wbr>Kinesis<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}Send the events to a kinesis firehose destination
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Matching<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of matching types. May be any of `&#34;send&#34;`, `&#34;reject&#34;`, `&#34;bounce&#34;`, `&#34;complaint&#34;`, `&#34;delivery&#34;`, `&#34;open&#34;`, `&#34;click&#34;`, or `&#34;renderingFailure&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the event destination
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationsnsdestination">*Event<wbr>Destination<wbr>Sns<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}Send the events to an SNS Topic destination
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cloudwatch<wbr>Destinations<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationcloudwatchdestination">Event<wbr>Destination<wbr>Cloudwatch<wbr>Destination[]?</a></span>
    </dt>
    <dd>{{% md %}}CloudWatch destination for the events
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">configuration<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the configuration set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the event destination will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationkinesisdestination">Event<wbr>Destination<wbr>Kinesis<wbr>Destination?</a></span>
    </dt>
    <dd>{{% md %}}Send the events to a kinesis firehose destination
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">matching<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of matching types. May be any of `&#34;send&#34;`, `&#34;reject&#34;`, `&#34;bounce&#34;`, `&#34;complaint&#34;`, `&#34;delivery&#34;`, `&#34;open&#34;`, `&#34;click&#34;`, or `&#34;renderingFailure&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the event destination
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationsnsdestination">Event<wbr>Destination<wbr>Sns<wbr>Destination?</a></span>
    </dt>
    <dd>{{% md %}}Send the events to an SNS Topic destination
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cloudwatch_<wbr>destinations<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationcloudwatchdestination">List[Event<wbr>Destination<wbr>Cloudwatch<wbr>Destination]</a></span>
    </dt>
    <dd>{{% md %}}CloudWatch destination for the events
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">configuration_<wbr>set_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the configuration set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the event destination will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis_<wbr>destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationkinesisdestination">Dict[Event<wbr>Destination<wbr>Kinesis<wbr>Destination]</a></span>
    </dt>
    <dd>{{% md %}}Send the events to a kinesis firehose destination
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">matching_<wbr>types<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of matching types. May be any of `&#34;send&#34;`, `&#34;reject&#34;`, `&#34;bounce&#34;`, `&#34;complaint&#34;`, `&#34;delivery&#34;`, `&#34;open&#34;`, `&#34;click&#34;`, or `&#34;renderingFailure&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the event destination
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns_<wbr>destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationsnsdestination">Dict[Event<wbr>Destination<wbr>Sns<wbr>Destination]</a></span>
    </dt>
    <dd>{{% md %}}Send the events to an SNS Topic destination
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## EventDestination Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Cloudwatch<wbr>Destinations<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationcloudwatchdestination">List&lt;Event<wbr>Destination<wbr>Cloudwatch<wbr>Destination&gt;?</a></span>
    </dt>
    <dd>{{% md %}}CloudWatch destination for the events
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the configuration set
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the event destination will be enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kinesis<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationkinesisdestination">Event<wbr>Destination<wbr>Kinesis<wbr>Destination?</a></span>
    </dt>
    <dd>{{% md %}}Send the events to a kinesis firehose destination
{{% /md %}}</dd>

    <dt class="property-"
            title="">Matching<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of matching types. May be any of `&#34;send&#34;`, `&#34;reject&#34;`, `&#34;bounce&#34;`, `&#34;complaint&#34;`, `&#34;delivery&#34;`, `&#34;open&#34;`, `&#34;click&#34;`, or `&#34;renderingFailure&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the event destination
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sns<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationsnsdestination">Event<wbr>Destination<wbr>Sns<wbr>Destination?</a></span>
    </dt>
    <dd>{{% md %}}Send the events to an SNS Topic destination
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Cloudwatch<wbr>Destinations<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationcloudwatchdestination">[]Event<wbr>Destination<wbr>Cloudwatch<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}CloudWatch destination for the events
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the configuration set
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the event destination will be enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kinesis<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationkinesisdestination">*Event<wbr>Destination<wbr>Kinesis<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}Send the events to a kinesis firehose destination
{{% /md %}}</dd>

    <dt class="property-"
            title="">Matching<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of matching types. May be any of `&#34;send&#34;`, `&#34;reject&#34;`, `&#34;bounce&#34;`, `&#34;complaint&#34;`, `&#34;delivery&#34;`, `&#34;open&#34;`, `&#34;click&#34;`, or `&#34;renderingFailure&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the event destination
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sns<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationsnsdestination">*Event<wbr>Destination<wbr>Sns<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}Send the events to an SNS Topic destination
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">cloudwatch<wbr>Destinations<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationcloudwatchdestination">Event<wbr>Destination<wbr>Cloudwatch<wbr>Destination[]?</a></span>
    </dt>
    <dd>{{% md %}}CloudWatch destination for the events
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the configuration set
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the event destination will be enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">kinesis<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationkinesisdestination">Event<wbr>Destination<wbr>Kinesis<wbr>Destination?</a></span>
    </dt>
    <dd>{{% md %}}Send the events to a kinesis firehose destination
{{% /md %}}</dd>

    <dt class="property-"
            title="">matching<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of matching types. May be any of `&#34;send&#34;`, `&#34;reject&#34;`, `&#34;bounce&#34;`, `&#34;complaint&#34;`, `&#34;delivery&#34;`, `&#34;open&#34;`, `&#34;click&#34;`, or `&#34;renderingFailure&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the event destination
{{% /md %}}</dd>

    <dt class="property-"
            title="">sns<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationsnsdestination">Event<wbr>Destination<wbr>Sns<wbr>Destination?</a></span>
    </dt>
    <dd>{{% md %}}Send the events to an SNS Topic destination
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">cloudwatch_<wbr>destinations<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationcloudwatchdestination">List[Event<wbr>Destination<wbr>Cloudwatch<wbr>Destination]</a></span>
    </dt>
    <dd>{{% md %}}CloudWatch destination for the events
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration_<wbr>set_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the configuration set
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the event destination will be enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">kinesis_<wbr>destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationkinesisdestination">Dict[Event<wbr>Destination<wbr>Kinesis<wbr>Destination]</a></span>
    </dt>
    <dd>{{% md %}}Send the events to a kinesis firehose destination
{{% /md %}}</dd>

    <dt class="property-"
            title="">matching_<wbr>types<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of matching types. May be any of `&#34;send&#34;`, `&#34;reject&#34;`, `&#34;bounce&#34;`, `&#34;complaint&#34;`, `&#34;delivery&#34;`, `&#34;open&#34;`, `&#34;click&#34;`, or `&#34;renderingFailure&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the event destination
{{% /md %}}</dd>

    <dt class="property-"
            title="">sns_<wbr>destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationsnsdestination">Dict[Event<wbr>Destination<wbr>Sns<wbr>Destination]</a></span>
    </dt>
    <dd>{{% md %}}Send the events to an SNS Topic destination
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing EventDestination Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ses/#EventDestinationState">EventDestinationState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ses/#EventDestination">EventDestination</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>cloudwatch_destinations=None<span class="p">, </span>configuration_set_name=None<span class="p">, </span>enabled=None<span class="p">, </span>kinesis_destination=None<span class="p">, </span>matching_types=None<span class="p">, </span>name=None<span class="p">, </span>sns_destination=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetEventDestination<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#EventDestinationState">EventDestinationState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#EventDestination">EventDestination</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.EventDestination.html">EventDestination</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.EventDestinationState.html">EventDestinationState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing EventDestination resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Cloudwatch<wbr>Destinations<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationcloudwatchdestination">List&lt;Event<wbr>Destination<wbr>Cloudwatch<wbr>Destination<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}CloudWatch destination for the events
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the configuration set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the event destination will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationkinesisdestination">Event<wbr>Destination<wbr>Kinesis<wbr>Destination<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Send the events to a kinesis firehose destination
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Matching<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of matching types. May be any of `&#34;send&#34;`, `&#34;reject&#34;`, `&#34;bounce&#34;`, `&#34;complaint&#34;`, `&#34;delivery&#34;`, `&#34;open&#34;`, `&#34;click&#34;`, or `&#34;renderingFailure&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the event destination
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationsnsdestination">Event<wbr>Destination<wbr>Sns<wbr>Destination<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Send the events to an SNS Topic destination
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cloudwatch<wbr>Destinations<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationcloudwatchdestination">[]Event<wbr>Destination<wbr>Cloudwatch<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}CloudWatch destination for the events
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the configuration set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the event destination will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kinesis<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationkinesisdestination">*Event<wbr>Destination<wbr>Kinesis<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}Send the events to a kinesis firehose destination
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Matching<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of matching types. May be any of `&#34;send&#34;`, `&#34;reject&#34;`, `&#34;bounce&#34;`, `&#34;complaint&#34;`, `&#34;delivery&#34;`, `&#34;open&#34;`, `&#34;click&#34;`, or `&#34;renderingFailure&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the event destination
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationsnsdestination">*Event<wbr>Destination<wbr>Sns<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}Send the events to an SNS Topic destination
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cloudwatch<wbr>Destinations<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationcloudwatchdestination">Event<wbr>Destination<wbr>Cloudwatch<wbr>Destination[]?</a></span>
    </dt>
    <dd>{{% md %}}CloudWatch destination for the events
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the configuration set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the event destination will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationkinesisdestination">Event<wbr>Destination<wbr>Kinesis<wbr>Destination?</a></span>
    </dt>
    <dd>{{% md %}}Send the events to a kinesis firehose destination
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">matching<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of matching types. May be any of `&#34;send&#34;`, `&#34;reject&#34;`, `&#34;bounce&#34;`, `&#34;complaint&#34;`, `&#34;delivery&#34;`, `&#34;open&#34;`, `&#34;click&#34;`, or `&#34;renderingFailure&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the event destination
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationsnsdestination">Event<wbr>Destination<wbr>Sns<wbr>Destination?</a></span>
    </dt>
    <dd>{{% md %}}Send the events to an SNS Topic destination
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cloudwatch_<wbr>destinations<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationcloudwatchdestination">List[Event<wbr>Destination<wbr>Cloudwatch<wbr>Destination]</a></span>
    </dt>
    <dd>{{% md %}}CloudWatch destination for the events
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration_<wbr>set_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the configuration set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the event destination will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kinesis_<wbr>destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationkinesisdestination">Dict[Event<wbr>Destination<wbr>Kinesis<wbr>Destination]</a></span>
    </dt>
    <dd>{{% md %}}Send the events to a kinesis firehose destination
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">matching_<wbr>types<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of matching types. May be any of `&#34;send&#34;`, `&#34;reject&#34;`, `&#34;bounce&#34;`, `&#34;complaint&#34;`, `&#34;delivery&#34;`, `&#34;open&#34;`, `&#34;click&#34;`, or `&#34;renderingFailure&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the event destination
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns_<wbr>destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#eventdestinationsnsdestination">Dict[Event<wbr>Destination<wbr>Sns<wbr>Destination]</a></span>
    </dt>
    <dd>{{% md %}}Send the events to an SNS Topic destination
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### EventDestinationCloudwatchDestination
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#EventDestinationCloudwatchDestination">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#EventDestinationCloudwatchDestination">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#EventDestinationCloudwatchDestinationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#EventDestinationCloudwatchDestinationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.EventDestinationCloudwatchDestinationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.EventDestinationCloudwatchDestination.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Default<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The default value for the event
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Dimension<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name for the dimension
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The source for the value. It can be either `&#34;messageTag&#34;` or `&#34;emailHeader&#34;`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Default<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The default value for the event
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Dimension<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name for the dimension
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The source for the value. It can be either `&#34;messageTag&#34;` or `&#34;emailHeader&#34;`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">default<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The default value for the event
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">dimension<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name for the dimension
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The source for the value. It can be either `&#34;messageTag&#34;` or `&#34;emailHeader&#34;`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">default_<wbr>value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The default value for the event
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">dimension<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name for the dimension
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The source for the value. It can be either `&#34;messageTag&#34;` or `&#34;emailHeader&#34;`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### EventDestinationKinesisDestination
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#EventDestinationKinesisDestination">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#EventDestinationKinesisDestination">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#EventDestinationKinesisDestinationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#EventDestinationKinesisDestinationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.EventDestinationKinesisDestinationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.EventDestinationKinesisDestination.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the role that has permissions to access the Kinesis Stream
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Stream
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the role that has permissions to access the Kinesis Stream
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Stream
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the role that has permissions to access the Kinesis Stream
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Stream
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the role that has permissions to access the Kinesis Stream
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stream_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Kinesis Stream
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### EventDestinationSnsDestination
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#EventDestinationSnsDestination">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#EventDestinationSnsDestination">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#EventDestinationSnsDestinationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#EventDestinationSnsDestinationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.EventDestinationSnsDestinationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.EventDestinationSnsDestination.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








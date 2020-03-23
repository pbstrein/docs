
---
title: "Environment"
block_external_search_index: true
---

Provides an Elastic Beanstalk Environment Resource. Elastic Beanstalk allows
you to deploy and manage applications in the AWS cloud without worrying about
the infrastructure that runs those applications.

Environments are often things such as `development`, `integration`, or
`production`.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const tftest = new aws.elasticbeanstalk.Application("tftest", {
    description: "tf-test-desc",
});
const tfenvtest = new aws.elasticbeanstalk.Environment("tfenvtest", {
    application: tftest.name,
    solutionStackName: "64bit Amazon Linux 2015.03 v2.0.3 running Go 1.4",
});
```

## Option Settings

Some options can be stack-specific, check [AWS Docs](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/command-options-general.html)
for supported options and examples.

The `setting` and `all_settings` mappings support the following format:

* `namespace` - unique namespace identifying the option's associated AWS resource
* `name` - name of the configuration option
* `value` - value for the configuration option
* `resource` - (Optional) resource name for [scheduled action](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/command-options-general.html#command-options-general-autoscalingscheduledaction)

### Example With Options

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const tftest = new aws.elasticbeanstalk.Application("tftest", {
    description: "tf-test-desc",
});
const tfenvtest = new aws.elasticbeanstalk.Environment("tfenvtest", {
    application: tftest.name,
    settings: [
        {
            name: "VPCId",
            namespace: "aws:ec2:vpc",
            value: "vpc-xxxxxxxx",
        },
        {
            name: "Subnets",
            namespace: "aws:ec2:vpc",
            value: "subnet-xxxxxxxx",
        },
    ],
    solutionStackName: "64bit Amazon Linux 2015.03 v2.0.3 running Go 1.4",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/elastic_beanstalk_environment.html.markdown.



## Create a Environment Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticbeanstalk/#Environment">Environment</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticbeanstalk/#EnvironmentArgs">EnvironmentArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Environment</span><span class="p">(resource_name, opts=None, </span>application=None<span class="p">, </span>cname_prefix=None<span class="p">, </span>description=None<span class="p">, </span>name=None<span class="p">, </span>platform_arn=None<span class="p">, </span>poll_interval=None<span class="p">, </span>settings=None<span class="p">, </span>solution_stack_name=None<span class="p">, </span>tags=None<span class="p">, </span>template_name=None<span class="p">, </span>tier=None<span class="p">, </span>version=None<span class="p">, </span>wait_for_ready_timeout=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewEnvironment<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticbeanstalk?tab=doc#EnvironmentArgs">EnvironmentArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticbeanstalk?tab=doc#Environment">Environment</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticbeanstalk.Environment.html">Environment</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticbeanstalk.EnvironmentArgs.html">EnvironmentArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Application<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the application that contains the version
to be deployed
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cname<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Prefix to use for the fully qualified DNS name of
the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Short description of the Environment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Platform<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [ARN][2] of the Elastic Beanstalk [Platform][3]
to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Poll<wbr>Interval<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time between polling the AWS API to
check if changes have been applied. Use this to adjust the rate of API calls
for any `create` or `update` action. Minimum `10s`, maximum `180s`. Omit this to
use the default behavior, which is an exponential backoff
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentsetting">List&lt;Environment<wbr>Setting<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Option settings to configure the new Environment. These
override specific values that are set as defaults. The format is detailed
below in Option Settings
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Solution<wbr>Stack<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A solution stack to base your environment
off of. Example stacks can be found in the [Amazon API documentation][1]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A set of tags to apply to the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Template<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Configuration
template to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Elastic Beanstalk Environment tier. Valid values are `Worker`
or `WebServer`. If tier is left blank `WebServer` will be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Application Version
to use in deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Ready<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum
[duration](https://golang.org/pkg/time/#ParseDuration) that this provider should
wait for an Elastic Beanstalk Environment to be in a ready state before timing
out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Application<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}Name of the application that contains the version
to be deployed
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cname<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Prefix to use for the fully qualified DNS name of
the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Short description of the Environment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Platform<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The [ARN][2] of the Elastic Beanstalk [Platform][3]
to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Poll<wbr>Interval<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The time between polling the AWS API to
check if changes have been applied. Use this to adjust the rate of API calls
for any `create` or `update` action. Minimum `10s`, maximum `180s`. Omit this to
use the default behavior, which is an exponential backoff
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentsetting">[]Environment<wbr>Setting</a></span>
    </dt>
    <dd>{{% md %}}Option settings to configure the new Environment. These
override specific values that are set as defaults. The format is detailed
below in Option Settings
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Solution<wbr>Stack<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A solution stack to base your environment
off of. Example stacks can be found in the [Amazon API documentation][1]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A set of tags to apply to the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Template<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Configuration
template to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Elastic Beanstalk Environment tier. Valid values are `Worker`
or `WebServer`. If tier is left blank `WebServer` will be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Application Version
to use in deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Ready<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum
[duration](https://golang.org/pkg/time/#ParseDuration) that this provider should
wait for an Elastic Beanstalk Environment to be in a ready state before timing
out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">application<span class="property-indicator"></span>
        <span class="property-type">string | Application</span>
    </dt>
    <dd>{{% md %}}Name of the application that contains the version
to be deployed
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cname<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Prefix to use for the fully qualified DNS name of
the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Short description of the Environment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">platform<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [ARN][2] of the Elastic Beanstalk [Platform][3]
to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">poll<wbr>Interval<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time between polling the AWS API to
check if changes have been applied. Use this to adjust the rate of API calls
for any `create` or `update` action. Minimum `10s`, maximum `180s`. Omit this to
use the default behavior, which is an exponential backoff
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentsetting">Environment<wbr>Setting[]?</a></span>
    </dt>
    <dd>{{% md %}}Option settings to configure the new Environment. These
override specific values that are set as defaults. The format is detailed
below in Option Settings
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">solution<wbr>Stack<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A solution stack to base your environment
off of. Example stacks can be found in the [Amazon API documentation][1]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A set of tags to apply to the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">template<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Configuration
template to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Elastic Beanstalk Environment tier. Valid values are `Worker`
or `WebServer`. If tier is left blank `WebServer` will be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">ApplicationVersion?</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Application Version
to use in deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait<wbr>For<wbr>Ready<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum
[duration](https://golang.org/pkg/time/#ParseDuration) that this provider should
wait for an Elastic Beanstalk Environment to be in a ready state before timing
out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">application<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Name of the application that contains the version
to be deployed
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cname_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Prefix to use for the fully qualified DNS name of
the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Short description of the Environment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">platform_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [ARN][2] of the Elastic Beanstalk [Platform][3]
to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">poll_<wbr>interval<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time between polling the AWS API to
check if changes have been applied. Use this to adjust the rate of API calls
for any `create` or `update` action. Minimum `10s`, maximum `180s`. Omit this to
use the default behavior, which is an exponential backoff
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentsetting">List[Environment<wbr>Setting]</a></span>
    </dt>
    <dd>{{% md %}}Option settings to configure the new Environment. These
override specific values that are set as defaults. The format is detailed
below in Option Settings
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">solution_<wbr>stack_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A solution stack to base your environment
off of. Example stacks can be found in the [Amazon API documentation][1]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A set of tags to apply to the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">template_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Configuration
template to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Elastic Beanstalk Environment tier. Valid values are `Worker`
or `WebServer`. If tier is left blank `WebServer` will be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Application Version
to use in deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait_<wbr>for_<wbr>ready_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum
[duration](https://golang.org/pkg/time/#ParseDuration) that this provider should
wait for an Elastic Beanstalk Environment to be in a ready state before timing
out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Environment Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">All<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentallsetting">List&lt;Environment<wbr>All<wbr>Setting&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of all option settings configured in this Environment. These
are a combination of default settings and their overrides from `setting` in
the configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Application<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the application that contains the version
to be deployed
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The autoscaling groups used by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Fully qualified DNS name for this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cname<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Prefix to use for the fully qualified DNS name of
the Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Short description of the Environment
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URL to the Load Balancer for this Environment
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instances<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Instances used by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Launch<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Launch configurations in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Elastic load balancers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-"
            title="">Platform<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [ARN][2] of the Elastic Beanstalk [Platform][3]
to use in deployment
{{% /md %}}</dd>

    <dt class="property-"
            title="">Poll<wbr>Interval<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time between polling the AWS API to
check if changes have been applied. Use this to adjust the rate of API calls
for any `create` or `update` action. Minimum `10s`, maximum `180s`. Omit this to
use the default behavior, which is an exponential backoff
{{% /md %}}</dd>

    <dt class="property-"
            title="">Queues<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}SQS queues in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentsetting">List&lt;Environment<wbr>Setting&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Option settings to configure the new Environment. These
override specific values that are set as defaults. The format is detailed
below in Option Settings
{{% /md %}}</dd>

    <dt class="property-"
            title="">Solution<wbr>Stack<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A solution stack to base your environment
off of. Example stacks can be found in the [Amazon API documentation][1]
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A set of tags to apply to the Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Template<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Configuration
template to use in deployment
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Elastic Beanstalk Environment tier. Valid values are `Worker`
or `WebServer`. If tier is left blank `WebServer` will be used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Triggers<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Autoscaling triggers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Application Version
to use in deployment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Wait<wbr>For<wbr>Ready<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum
[duration](https://golang.org/pkg/time/#ParseDuration) that this provider should
wait for an Elastic Beanstalk Environment to be in a ready state before timing
out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">All<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentallsetting">[]Environment<wbr>All<wbr>Setting</a></span>
    </dt>
    <dd>{{% md %}}List of all option settings configured in this Environment. These
are a combination of default settings and their overrides from `setting` in
the configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Application<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the application that contains the version
to be deployed
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The autoscaling groups used by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Fully qualified DNS name for this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cname<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Prefix to use for the fully qualified DNS name of
the Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Short description of the Environment
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URL to the Load Balancer for this Environment
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instances<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Instances used by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Launch<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Launch configurations in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Elastic load balancers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-"
            title="">Platform<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [ARN][2] of the Elastic Beanstalk [Platform][3]
to use in deployment
{{% /md %}}</dd>

    <dt class="property-"
            title="">Poll<wbr>Interval<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The time between polling the AWS API to
check if changes have been applied. Use this to adjust the rate of API calls
for any `create` or `update` action. Minimum `10s`, maximum `180s`. Omit this to
use the default behavior, which is an exponential backoff
{{% /md %}}</dd>

    <dt class="property-"
            title="">Queues<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}SQS queues in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentsetting">[]Environment<wbr>Setting</a></span>
    </dt>
    <dd>{{% md %}}Option settings to configure the new Environment. These
override specific values that are set as defaults. The format is detailed
below in Option Settings
{{% /md %}}</dd>

    <dt class="property-"
            title="">Solution<wbr>Stack<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A solution stack to base your environment
off of. Example stacks can be found in the [Amazon API documentation][1]
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A set of tags to apply to the Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Template<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Configuration
template to use in deployment
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Elastic Beanstalk Environment tier. Valid values are `Worker`
or `WebServer`. If tier is left blank `WebServer` will be used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Triggers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Autoscaling triggers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Application Version
to use in deployment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Wait<wbr>For<wbr>Ready<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum
[duration](https://golang.org/pkg/time/#ParseDuration) that this provider should
wait for an Elastic Beanstalk Environment to be in a ready state before timing
out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">all<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentallsetting">Environment<wbr>All<wbr>Setting[]</a></span>
    </dt>
    <dd>{{% md %}}List of all option settings configured in this Environment. These
are a combination of default settings and their overrides from `setting` in
the configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">application<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the application that contains the version
to be deployed
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The autoscaling groups used by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Fully qualified DNS name for this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cname<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Prefix to use for the fully qualified DNS name of
the Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Short description of the Environment
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URL to the Load Balancer for this Environment
{{% /md %}}</dd>

    <dt class="property-"
            title="">instances<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Instances used by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">launch<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Launch configurations in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Elastic load balancers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-"
            title="">platform<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [ARN][2] of the Elastic Beanstalk [Platform][3]
to use in deployment
{{% /md %}}</dd>

    <dt class="property-"
            title="">poll<wbr>Interval<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time between polling the AWS API to
check if changes have been applied. Use this to adjust the rate of API calls
for any `create` or `update` action. Minimum `10s`, maximum `180s`. Omit this to
use the default behavior, which is an exponential backoff
{{% /md %}}</dd>

    <dt class="property-"
            title="">queues<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}SQS queues in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentsetting">Environment<wbr>Setting[]?</a></span>
    </dt>
    <dd>{{% md %}}Option settings to configure the new Environment. These
override specific values that are set as defaults. The format is detailed
below in Option Settings
{{% /md %}}</dd>

    <dt class="property-"
            title="">solution<wbr>Stack<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A solution stack to base your environment
off of. Example stacks can be found in the [Amazon API documentation][1]
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A set of tags to apply to the Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">template<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Configuration
template to use in deployment
{{% /md %}}</dd>

    <dt class="property-"
            title="">tier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Elastic Beanstalk Environment tier. Valid values are `Worker`
or `WebServer`. If tier is left blank `WebServer` will be used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">triggers<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Autoscaling triggers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">ApplicationVersion</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Application Version
to use in deployment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">wait<wbr>For<wbr>Ready<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum
[duration](https://golang.org/pkg/time/#ParseDuration) that this provider should
wait for an Elastic Beanstalk Environment to be in a ready state before timing
out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">all_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentallsetting">List[Environment<wbr>All<wbr>Setting]</a></span>
    </dt>
    <dd>{{% md %}}List of all option settings configured in this Environment. These
are a combination of default settings and their overrides from `setting` in
the configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">application<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the application that contains the version
to be deployed
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">autoscaling_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The autoscaling groups used by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cname<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Fully qualified DNS name for this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cname_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Prefix to use for the fully qualified DNS name of
the Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Short description of the Environment
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint_<wbr>url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The URL to the Load Balancer for this Environment
{{% /md %}}</dd>

    <dt class="property-"
            title="">instances<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Instances used by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">launch_<wbr>configurations<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Launch configurations in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">load_<wbr>balancers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Elastic load balancers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-"
            title="">platform_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [ARN][2] of the Elastic Beanstalk [Platform][3]
to use in deployment
{{% /md %}}</dd>

    <dt class="property-"
            title="">poll_<wbr>interval<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time between polling the AWS API to
check if changes have been applied. Use this to adjust the rate of API calls
for any `create` or `update` action. Minimum `10s`, maximum `180s`. Omit this to
use the default behavior, which is an exponential backoff
{{% /md %}}</dd>

    <dt class="property-"
            title="">queues<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}SQS queues in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentsetting">List[Environment<wbr>Setting]</a></span>
    </dt>
    <dd>{{% md %}}Option settings to configure the new Environment. These
override specific values that are set as defaults. The format is detailed
below in Option Settings
{{% /md %}}</dd>

    <dt class="property-"
            title="">solution_<wbr>stack_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A solution stack to base your environment
off of. Example stacks can be found in the [Amazon API documentation][1]
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A set of tags to apply to the Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">template_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Configuration
template to use in deployment
{{% /md %}}</dd>

    <dt class="property-"
            title="">tier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Elastic Beanstalk Environment tier. Valid values are `Worker`
or `WebServer`. If tier is left blank `WebServer` will be used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">triggers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Autoscaling triggers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Application Version
to use in deployment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">wait_<wbr>for_<wbr>ready_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum
[duration](https://golang.org/pkg/time/#ParseDuration) that this provider should
wait for an Elastic Beanstalk Environment to be in a ready state before timing
out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Environment Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticbeanstalk/#EnvironmentState">EnvironmentState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticbeanstalk/#Environment">Environment</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>all_settings=None<span class="p">, </span>application=None<span class="p">, </span>arn=None<span class="p">, </span>autoscaling_groups=None<span class="p">, </span>cname=None<span class="p">, </span>cname_prefix=None<span class="p">, </span>description=None<span class="p">, </span>endpoint_url=None<span class="p">, </span>instances=None<span class="p">, </span>launch_configurations=None<span class="p">, </span>load_balancers=None<span class="p">, </span>name=None<span class="p">, </span>platform_arn=None<span class="p">, </span>poll_interval=None<span class="p">, </span>queues=None<span class="p">, </span>settings=None<span class="p">, </span>solution_stack_name=None<span class="p">, </span>tags=None<span class="p">, </span>template_name=None<span class="p">, </span>tier=None<span class="p">, </span>triggers=None<span class="p">, </span>version=None<span class="p">, </span>wait_for_ready_timeout=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetEnvironment<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticbeanstalk?tab=doc#EnvironmentState">EnvironmentState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticbeanstalk?tab=doc#Environment">Environment</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticbeanstalk.Environment.html">Environment</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticbeanstalk.EnvironmentState.html">EnvironmentState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Environment resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">All<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentallsetting">List&lt;Environment<wbr>All<wbr>Setting<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List of all option settings configured in this Environment. These
are a combination of default settings and their overrides from `setting` in
the configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Application<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the application that contains the version
to be deployed
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The autoscaling groups used by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cname<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Fully qualified DNS name for this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cname<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Prefix to use for the fully qualified DNS name of
the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Short description of the Environment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The URL to the Load Balancer for this Environment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instances<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Instances used by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Launch configurations in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Elastic load balancers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Platform<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [ARN][2] of the Elastic Beanstalk [Platform][3]
to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Poll<wbr>Interval<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time between polling the AWS API to
check if changes have been applied. Use this to adjust the rate of API calls
for any `create` or `update` action. Minimum `10s`, maximum `180s`. Omit this to
use the default behavior, which is an exponential backoff
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Queues<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}SQS queues in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentsetting">List&lt;Environment<wbr>Setting<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Option settings to configure the new Environment. These
override specific values that are set as defaults. The format is detailed
below in Option Settings
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Solution<wbr>Stack<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A solution stack to base your environment
off of. Example stacks can be found in the [Amazon API documentation][1]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A set of tags to apply to the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Template<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Configuration
template to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Elastic Beanstalk Environment tier. Valid values are `Worker`
or `WebServer`. If tier is left blank `WebServer` will be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Triggers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Autoscaling triggers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Application Version
to use in deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Ready<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum
[duration](https://golang.org/pkg/time/#ParseDuration) that this provider should
wait for an Elastic Beanstalk Environment to be in a ready state before timing
out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">All<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentallsetting">[]Environment<wbr>All<wbr>Setting</a></span>
    </dt>
    <dd>{{% md %}}List of all option settings configured in this Environment. These
are a combination of default settings and their overrides from `setting` in
the configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Application<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}Name of the application that contains the version
to be deployed
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The autoscaling groups used by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cname<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Fully qualified DNS name for this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cname<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Prefix to use for the fully qualified DNS name of
the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Short description of the Environment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The URL to the Load Balancer for this Environment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instances<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Instances used by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Launch configurations in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Elastic load balancers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Platform<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The [ARN][2] of the Elastic Beanstalk [Platform][3]
to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Poll<wbr>Interval<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The time between polling the AWS API to
check if changes have been applied. Use this to adjust the rate of API calls
for any `create` or `update` action. Minimum `10s`, maximum `180s`. Omit this to
use the default behavior, which is an exponential backoff
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Queues<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}SQS queues in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentsetting">[]Environment<wbr>Setting</a></span>
    </dt>
    <dd>{{% md %}}Option settings to configure the new Environment. These
override specific values that are set as defaults. The format is detailed
below in Option Settings
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Solution<wbr>Stack<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A solution stack to base your environment
off of. Example stacks can be found in the [Amazon API documentation][1]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A set of tags to apply to the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Template<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Configuration
template to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Elastic Beanstalk Environment tier. Valid values are `Worker`
or `WebServer`. If tier is left blank `WebServer` will be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Triggers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Autoscaling triggers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Application Version
to use in deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Ready<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum
[duration](https://golang.org/pkg/time/#ParseDuration) that this provider should
wait for an Elastic Beanstalk Environment to be in a ready state before timing
out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">all<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentallsetting">Environment<wbr>All<wbr>Setting[]?</a></span>
    </dt>
    <dd>{{% md %}}List of all option settings configured in this Environment. These
are a combination of default settings and their overrides from `setting` in
the configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">application<span class="property-indicator"></span>
        <span class="property-type">string | Application</span>
    </dt>
    <dd>{{% md %}}Name of the application that contains the version
to be deployed
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The autoscaling groups used by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cname<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Fully qualified DNS name for this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cname<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Prefix to use for the fully qualified DNS name of
the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Short description of the Environment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The URL to the Load Balancer for this Environment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instances<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Instances used by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Launch configurations in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Elastic load balancers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">platform<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [ARN][2] of the Elastic Beanstalk [Platform][3]
to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">poll<wbr>Interval<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time between polling the AWS API to
check if changes have been applied. Use this to adjust the rate of API calls
for any `create` or `update` action. Minimum `10s`, maximum `180s`. Omit this to
use the default behavior, which is an exponential backoff
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">queues<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}SQS queues in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentsetting">Environment<wbr>Setting[]?</a></span>
    </dt>
    <dd>{{% md %}}Option settings to configure the new Environment. These
override specific values that are set as defaults. The format is detailed
below in Option Settings
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">solution<wbr>Stack<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A solution stack to base your environment
off of. Example stacks can be found in the [Amazon API documentation][1]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A set of tags to apply to the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">template<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Configuration
template to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Elastic Beanstalk Environment tier. Valid values are `Worker`
or `WebServer`. If tier is left blank `WebServer` will be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">triggers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Autoscaling triggers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">ApplicationVersion?</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Application Version
to use in deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait<wbr>For<wbr>Ready<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum
[duration](https://golang.org/pkg/time/#ParseDuration) that this provider should
wait for an Elastic Beanstalk Environment to be in a ready state before timing
out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">all_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentallsetting">List[Environment<wbr>All<wbr>Setting]</a></span>
    </dt>
    <dd>{{% md %}}List of all option settings configured in this Environment. These
are a combination of default settings and their overrides from `setting` in
the configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">application<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Name of the application that contains the version
to be deployed
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">autoscaling_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The autoscaling groups used by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cname<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Fully qualified DNS name for this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cname_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Prefix to use for the fully qualified DNS name of
the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Short description of the Environment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint_<wbr>url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The URL to the Load Balancer for this Environment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instances<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Instances used by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch_<wbr>configurations<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Launch configurations in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load_<wbr>balancers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Elastic load balancers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">platform_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [ARN][2] of the Elastic Beanstalk [Platform][3]
to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">poll_<wbr>interval<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time between polling the AWS API to
check if changes have been applied. Use this to adjust the rate of API calls
for any `create` or `update` action. Minimum `10s`, maximum `180s`. Omit this to
use the default behavior, which is an exponential backoff
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">queues<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}SQS queues in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#environmentsetting">List[Environment<wbr>Setting]</a></span>
    </dt>
    <dd>{{% md %}}Option settings to configure the new Environment. These
override specific values that are set as defaults. The format is detailed
below in Option Settings
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">solution_<wbr>stack_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A solution stack to base your environment
off of. Example stacks can be found in the [Amazon API documentation][1]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A set of tags to apply to the Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">template_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Configuration
template to use in deployment
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Elastic Beanstalk Environment tier. Valid values are `Worker`
or `WebServer`. If tier is left blank `WebServer` will be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">triggers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Autoscaling triggers in use by this Environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Elastic Beanstalk Application Version
to use in deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait_<wbr>for_<wbr>ready_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum
[duration](https://golang.org/pkg/time/#ParseDuration) that this provider should
wait for an Elastic Beanstalk Environment to be in a ready state before timing
out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### EnvironmentAllSetting
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#EnvironmentAllSetting">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticbeanstalk?tab=doc#EnvironmentAllSettingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticbeanstalk.EnvironmentAllSetting.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Namespace<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Namespace<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">namespace<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">namespace<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### EnvironmentSetting
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#EnvironmentSetting">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#EnvironmentSetting">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticbeanstalk?tab=doc#EnvironmentSettingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticbeanstalk?tab=doc#EnvironmentSettingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticbeanstalk.EnvironmentSettingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticbeanstalk.EnvironmentSetting.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Namespace<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Namespace<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">namespace<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name for this Environment. This name is used
in the application URL
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">namespace<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








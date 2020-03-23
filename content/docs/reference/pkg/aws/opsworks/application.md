
---
title: "Application"
block_external_search_index: true
---

Provides an OpsWorks application resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";
import * as fs from "fs";

const foo_app = new aws.opsworks.Application("foo-app", {
    appSources: [{
        revision: "master",
        type: "git",
        url: "https://github.com/example.git",
    }],
    autoBundleOnDeploy: "true",
    description: "This is a Rails application",
    documentRoot: "public",
    domains: [
        "example.com",
        "sub.example.com",
    ],
    enableSsl: true,
    environments: [{
        key: "key",
        secure: false,
        value: "value",
    }],
    railsEnv: "staging",
    shortName: "foobar",
    sslConfigurations: [{
        certificate: fs.readFileSync("./foobar.crt", "utf-8"),
        privateKey: fs.readFileSync("./foobar.key", "utf-8"),
    }],
    stackId: aws_opsworks_stack_main.id,
    type: "rails",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/opsworks_application.html.markdown.



## Create a Application Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#Application">Application</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#ApplicationArgs">ApplicationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Application</span><span class="p">(resource_name, opts=None, </span>app_sources=None<span class="p">, </span>auto_bundle_on_deploy=None<span class="p">, </span>aws_flow_ruby_settings=None<span class="p">, </span>data_source_arn=None<span class="p">, </span>data_source_database_name=None<span class="p">, </span>data_source_type=None<span class="p">, </span>description=None<span class="p">, </span>document_root=None<span class="p">, </span>domains=None<span class="p">, </span>enable_ssl=None<span class="p">, </span>environments=None<span class="p">, </span>name=None<span class="p">, </span>rails_env=None<span class="p">, </span>short_name=None<span class="p">, </span>ssl_configurations=None<span class="p">, </span>stack_id=None<span class="p">, </span>type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewApplication<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#ApplicationArgs">ApplicationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#Application">Application</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.Application.html">Application</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.ApplicationArgs.html">ApplicationArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">App<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationappsource">List&lt;Application<wbr>App<wbr>Source<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}SCM configuration of the app as described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Bundle<wbr>On<wbr>Deploy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Run bundle install when deploying for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Flow<wbr>Ruby<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify activity and workflow workers for your app using the aws-flow gem.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s ARN.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<wbr>Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The database name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s type one of `AutoSelectOpsworksMysqlInstance`, `OpsworksMysqlInstance`, or `RdsDbInstance`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Root<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subfolder for the document root for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domains<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of virtual host alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable SSL for the app. This must be set in order to let `ssl_configuration.private_key`, `ssl_configuration.certificate` and `ssl_configuration.chain` take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Environments<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationenvironment">List&lt;Application<wbr>Environment<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Object to define environment variables.  Object is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rails<wbr>Env<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Rails environment for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A short, machine-readable name for the application. This can only be defined on resource creation and ignored on resource update.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssl<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationsslconfiguration">List&lt;Application<wbr>Ssl<wbr>Configuration<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The SSL configuration of the app. Object is described below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the application will belong to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">App<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationappsource">[]Application<wbr>App<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}SCM configuration of the app as described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Bundle<wbr>On<wbr>Deploy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Run bundle install when deploying for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Flow<wbr>Ruby<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify activity and workflow workers for your app using the aws-flow gem.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s ARN.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<wbr>Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The database name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s type one of `AutoSelectOpsworksMysqlInstance`, `OpsworksMysqlInstance`, or `RdsDbInstance`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A description of the app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Root<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Subfolder for the document root for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domains<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of virtual host alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable SSL for the app. This must be set in order to let `ssl_configuration.private_key`, `ssl_configuration.certificate` and `ssl_configuration.chain` take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Environments<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationenvironment">[]Application<wbr>Environment</a></span>
    </dt>
    <dd>{{% md %}}Object to define environment variables.  Object is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rails<wbr>Env<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Rails environment for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A short, machine-readable name for the application. This can only be defined on resource creation and ignored on resource update.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssl<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationsslconfiguration">[]Application<wbr>Ssl<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The SSL configuration of the app. Object is described below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the application will belong to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">app<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationappsource">Application<wbr>App<wbr>Source[]?</a></span>
    </dt>
    <dd>{{% md %}}SCM configuration of the app as described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Bundle<wbr>On<wbr>Deploy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Run bundle install when deploying for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws<wbr>Flow<wbr>Ruby<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify activity and workflow workers for your app using the aws-flow gem.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data<wbr>Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s ARN.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data<wbr>Source<wbr>Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The database name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data<wbr>Source<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s type one of `AutoSelectOpsworksMysqlInstance`, `OpsworksMysqlInstance`, or `RdsDbInstance`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document<wbr>Root<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subfolder for the document root for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domains<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of virtual host alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable SSL for the app. This must be set in order to let `ssl_configuration.private_key`, `ssl_configuration.certificate` and `ssl_configuration.chain` take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">environments<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationenvironment">Application<wbr>Environment[]?</a></span>
    </dt>
    <dd>{{% md %}}Object to define environment variables.  Object is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rails<wbr>Env<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Rails environment for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A short, machine-readable name for the application. This can only be defined on resource creation and ignored on resource update.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssl<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationsslconfiguration">Application<wbr>Ssl<wbr>Configuration[]?</a></span>
    </dt>
    <dd>{{% md %}}The SSL configuration of the app. Object is described below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the application will belong to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">app_<wbr>sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationappsource">List[Application<wbr>App<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}SCM configuration of the app as described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>bundle_<wbr>on_<wbr>deploy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Run bundle install when deploying for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws_<wbr>flow_<wbr>ruby_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify activity and workflow workers for your app using the aws-flow gem.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data_<wbr>source_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s ARN.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data_<wbr>source_<wbr>database_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The database name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data_<wbr>source_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s type one of `AutoSelectOpsworksMysqlInstance`, `OpsworksMysqlInstance`, or `RdsDbInstance`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A description of the app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document_<wbr>root<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Subfolder for the document root for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domains<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of virtual host alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>ssl<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable SSL for the app. This must be set in order to let `ssl_configuration.private_key`, `ssl_configuration.certificate` and `ssl_configuration.chain` take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">environments<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationenvironment">List[Application<wbr>Environment]</a></span>
    </dt>
    <dd>{{% md %}}Object to define environment variables.  Object is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rails_<wbr>env<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Rails environment for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">short_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A short, machine-readable name for the application. This can only be defined on resource creation and ignored on resource update.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssl_<wbr>configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationsslconfiguration">List[Application<wbr>Ssl<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The SSL configuration of the app. Object is described below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stack_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the stack the application will belong to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Application Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">App<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationappsource">List&lt;Application<wbr>App<wbr>Source&gt;</a></span>
    </dt>
    <dd>{{% md %}}SCM configuration of the app as described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Bundle<wbr>On<wbr>Deploy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Run bundle install when deploying for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Aws<wbr>Flow<wbr>Ruby<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify activity and workflow workers for your app using the aws-flow gem.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Data<wbr>Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s ARN.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Data<wbr>Source<wbr>Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The database name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Data<wbr>Source<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s type one of `AutoSelectOpsworksMysqlInstance`, `OpsworksMysqlInstance`, or `RdsDbInstance`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the app.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Document<wbr>Root<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subfolder for the document root for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Domains<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of virtual host alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable SSL for the app. This must be set in order to let `ssl_configuration.private_key`, `ssl_configuration.certificate` and `ssl_configuration.chain` take effect.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Environments<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationenvironment">List&lt;Application<wbr>Environment&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Object to define environment variables.  Object is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rails<wbr>Env<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Rails environment for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A short, machine-readable name for the application. This can only be defined on resource creation and ignored on resource update.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ssl<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationsslconfiguration">List&lt;Application<wbr>Ssl<wbr>Configuration&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The SSL configuration of the app. Object is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the application will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">App<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationappsource">[]Application<wbr>App<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}SCM configuration of the app as described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Bundle<wbr>On<wbr>Deploy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Run bundle install when deploying for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Aws<wbr>Flow<wbr>Ruby<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify activity and workflow workers for your app using the aws-flow gem.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Data<wbr>Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s ARN.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Data<wbr>Source<wbr>Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The database name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Data<wbr>Source<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s type one of `AutoSelectOpsworksMysqlInstance`, `OpsworksMysqlInstance`, or `RdsDbInstance`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A description of the app.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Document<wbr>Root<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Subfolder for the document root for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Domains<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of virtual host alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable SSL for the app. This must be set in order to let `ssl_configuration.private_key`, `ssl_configuration.certificate` and `ssl_configuration.chain` take effect.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Environments<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationenvironment">[]Application<wbr>Environment</a></span>
    </dt>
    <dd>{{% md %}}Object to define environment variables.  Object is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rails<wbr>Env<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Rails environment for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A short, machine-readable name for the application. This can only be defined on resource creation and ignored on resource update.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ssl<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationsslconfiguration">[]Application<wbr>Ssl<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The SSL configuration of the app. Object is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the application will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">app<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationappsource">Application<wbr>App<wbr>Source[]</a></span>
    </dt>
    <dd>{{% md %}}SCM configuration of the app as described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto<wbr>Bundle<wbr>On<wbr>Deploy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Run bundle install when deploying for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">aws<wbr>Flow<wbr>Ruby<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify activity and workflow workers for your app using the aws-flow gem.
{{% /md %}}</dd>

    <dt class="property-"
            title="">data<wbr>Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s ARN.
{{% /md %}}</dd>

    <dt class="property-"
            title="">data<wbr>Source<wbr>Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The database name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">data<wbr>Source<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s type one of `AutoSelectOpsworksMysqlInstance`, `OpsworksMysqlInstance`, or `RdsDbInstance`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the app.
{{% /md %}}</dd>

    <dt class="property-"
            title="">document<wbr>Root<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subfolder for the document root for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">domains<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of virtual host alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable SSL for the app. This must be set in order to let `ssl_configuration.private_key`, `ssl_configuration.certificate` and `ssl_configuration.chain` take effect.
{{% /md %}}</dd>

    <dt class="property-"
            title="">environments<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationenvironment">Application<wbr>Environment[]?</a></span>
    </dt>
    <dd>{{% md %}}Object to define environment variables.  Object is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rails<wbr>Env<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Rails environment for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A short, machine-readable name for the application. This can only be defined on resource creation and ignored on resource update.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ssl<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationsslconfiguration">Application<wbr>Ssl<wbr>Configuration[]?</a></span>
    </dt>
    <dd>{{% md %}}The SSL configuration of the app. Object is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the application will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">app_<wbr>sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationappsource">List[Application<wbr>App<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}SCM configuration of the app as described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto_<wbr>bundle_<wbr>on_<wbr>deploy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Run bundle install when deploying for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">aws_<wbr>flow_<wbr>ruby_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify activity and workflow workers for your app using the aws-flow gem.
{{% /md %}}</dd>

    <dt class="property-"
            title="">data_<wbr>source_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s ARN.
{{% /md %}}</dd>

    <dt class="property-"
            title="">data_<wbr>source_<wbr>database_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The database name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">data_<wbr>source_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s type one of `AutoSelectOpsworksMysqlInstance`, `OpsworksMysqlInstance`, or `RdsDbInstance`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A description of the app.
{{% /md %}}</dd>

    <dt class="property-"
            title="">document_<wbr>root<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Subfolder for the document root for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">domains<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of virtual host alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable_<wbr>ssl<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable SSL for the app. This must be set in order to let `ssl_configuration.private_key`, `ssl_configuration.certificate` and `ssl_configuration.chain` take effect.
{{% /md %}}</dd>

    <dt class="property-"
            title="">environments<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationenvironment">List[Application<wbr>Environment]</a></span>
    </dt>
    <dd>{{% md %}}Object to define environment variables.  Object is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rails_<wbr>env<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Rails environment for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">short_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A short, machine-readable name for the application. This can only be defined on resource creation and ignored on resource update.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ssl_<wbr>configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationsslconfiguration">List[Application<wbr>Ssl<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The SSL configuration of the app. Object is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">stack_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the stack the application will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Application Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#ApplicationState">ApplicationState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#Application">Application</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>app_sources=None<span class="p">, </span>auto_bundle_on_deploy=None<span class="p">, </span>aws_flow_ruby_settings=None<span class="p">, </span>data_source_arn=None<span class="p">, </span>data_source_database_name=None<span class="p">, </span>data_source_type=None<span class="p">, </span>description=None<span class="p">, </span>document_root=None<span class="p">, </span>domains=None<span class="p">, </span>enable_ssl=None<span class="p">, </span>environments=None<span class="p">, </span>name=None<span class="p">, </span>rails_env=None<span class="p">, </span>short_name=None<span class="p">, </span>ssl_configurations=None<span class="p">, </span>stack_id=None<span class="p">, </span>type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetApplication<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#ApplicationState">ApplicationState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#Application">Application</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.Application.html">Application</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.ApplicationState.html">ApplicationState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Application resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">App<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationappsource">List&lt;Application<wbr>App<wbr>Source<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}SCM configuration of the app as described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Bundle<wbr>On<wbr>Deploy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Run bundle install when deploying for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Flow<wbr>Ruby<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify activity and workflow workers for your app using the aws-flow gem.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s ARN.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<wbr>Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The database name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s type one of `AutoSelectOpsworksMysqlInstance`, `OpsworksMysqlInstance`, or `RdsDbInstance`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Root<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subfolder for the document root for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domains<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of virtual host alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable SSL for the app. This must be set in order to let `ssl_configuration.private_key`, `ssl_configuration.certificate` and `ssl_configuration.chain` take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Environments<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationenvironment">List&lt;Application<wbr>Environment<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Object to define environment variables.  Object is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rails<wbr>Env<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Rails environment for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A short, machine-readable name for the application. This can only be defined on resource creation and ignored on resource update.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssl<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationsslconfiguration">List&lt;Application<wbr>Ssl<wbr>Configuration<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The SSL configuration of the app. Object is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the stack the application will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">App<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationappsource">[]Application<wbr>App<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}SCM configuration of the app as described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Bundle<wbr>On<wbr>Deploy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Run bundle install when deploying for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Flow<wbr>Ruby<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify activity and workflow workers for your app using the aws-flow gem.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s ARN.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<wbr>Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The database name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Data<wbr>Source<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s type one of `AutoSelectOpsworksMysqlInstance`, `OpsworksMysqlInstance`, or `RdsDbInstance`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A description of the app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Root<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Subfolder for the document root for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domains<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of virtual host alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable SSL for the app. This must be set in order to let `ssl_configuration.private_key`, `ssl_configuration.certificate` and `ssl_configuration.chain` take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Environments<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationenvironment">[]Application<wbr>Environment</a></span>
    </dt>
    <dd>{{% md %}}Object to define environment variables.  Object is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rails<wbr>Env<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Rails environment for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A short, machine-readable name for the application. This can only be defined on resource creation and ignored on resource update.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssl<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationsslconfiguration">[]Application<wbr>Ssl<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The SSL configuration of the app. Object is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the application will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">app<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationappsource">Application<wbr>App<wbr>Source[]?</a></span>
    </dt>
    <dd>{{% md %}}SCM configuration of the app as described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Bundle<wbr>On<wbr>Deploy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Run bundle install when deploying for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws<wbr>Flow<wbr>Ruby<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify activity and workflow workers for your app using the aws-flow gem.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data<wbr>Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s ARN.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data<wbr>Source<wbr>Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The database name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data<wbr>Source<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s type one of `AutoSelectOpsworksMysqlInstance`, `OpsworksMysqlInstance`, or `RdsDbInstance`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document<wbr>Root<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subfolder for the document root for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domains<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of virtual host alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable SSL for the app. This must be set in order to let `ssl_configuration.private_key`, `ssl_configuration.certificate` and `ssl_configuration.chain` take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">environments<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationenvironment">Application<wbr>Environment[]?</a></span>
    </dt>
    <dd>{{% md %}}Object to define environment variables.  Object is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rails<wbr>Env<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Rails environment for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A short, machine-readable name for the application. This can only be defined on resource creation and ignored on resource update.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssl<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationsslconfiguration">Application<wbr>Ssl<wbr>Configuration[]?</a></span>
    </dt>
    <dd>{{% md %}}The SSL configuration of the app. Object is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the stack the application will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">app_<wbr>sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationappsource">List[Application<wbr>App<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}SCM configuration of the app as described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>bundle_<wbr>on_<wbr>deploy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Run bundle install when deploying for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws_<wbr>flow_<wbr>ruby_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify activity and workflow workers for your app using the aws-flow gem.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data_<wbr>source_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s ARN.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data_<wbr>source_<wbr>database_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The database name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">data_<wbr>source_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The data source&#39;s type one of `AutoSelectOpsworksMysqlInstance`, `OpsworksMysqlInstance`, or `RdsDbInstance`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A description of the app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document_<wbr>root<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Subfolder for the document root for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domains<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of virtual host alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>ssl<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable SSL for the app. This must be set in order to let `ssl_configuration.private_key`, `ssl_configuration.certificate` and `ssl_configuration.chain` take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">environments<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationenvironment">List[Application<wbr>Environment]</a></span>
    </dt>
    <dd>{{% md %}}Object to define environment variables.  Object is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rails_<wbr>env<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Rails environment for application of type `rails`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">short_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A short, machine-readable name for the application. This can only be defined on resource creation and ignored on resource update.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssl_<wbr>configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#applicationsslconfiguration">List[Application<wbr>Ssl<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The SSL configuration of the app. Object is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stack_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the stack the application will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### ApplicationAppSource
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ApplicationAppSource">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ApplicationAppSource">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#ApplicationAppSourceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#ApplicationAppSourceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.ApplicationAppSourceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.ApplicationAppSource.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Revision<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}For sources that are version-aware, the revision to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The URL where the app resource can be found.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Username<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Username to use when authenticating to the source.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Password<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Revision<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}For sources that are version-aware, the revision to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Url<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The URL where the app resource can be found.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Username<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Username to use when authenticating to the source.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">revision<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}For sources that are version-aware, the revision to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The URL where the app resource can be found.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">username<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Username to use when authenticating to the source.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">password<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">revision<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}For sources that are version-aware, the revision to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of source to use. For example, &#34;archive&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The URL where the app resource can be found.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">username<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Username to use when authenticating to the source.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ApplicationEnvironment
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ApplicationEnvironment">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ApplicationEnvironment">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#ApplicationEnvironmentArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#ApplicationEnvironmentOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.ApplicationEnvironmentArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.ApplicationEnvironment.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secure<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
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
            title="Required">Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secure<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
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
            title="Required">key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secure<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
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
            title="Required">key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secure<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ApplicationSslConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ApplicationSslConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ApplicationSslConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#ApplicationSslConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#ApplicationSslConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.ApplicationSslConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.ApplicationSslConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Certificate<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Chain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Private<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Certificate<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Chain<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Private<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">certificate<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">chain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">private<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">certificate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">chain<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">private_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








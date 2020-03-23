
---
title: "JavaAppLayer"
block_external_search_index: true
---

Provides an OpsWorks Java application layer resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const app = new aws.opsworks.JavaAppLayer("app", {
    stackId: aws_opsworks_stack_main.id,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/opsworks_java_app_layer.html.markdown.



## Create a JavaAppLayer Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#JavaAppLayer">JavaAppLayer</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#JavaAppLayerArgs">JavaAppLayerArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">JavaAppLayer</span><span class="p">(resource_name, opts=None, </span>app_server=None<span class="p">, </span>app_server_version=None<span class="p">, </span>auto_assign_elastic_ips=None<span class="p">, </span>auto_assign_public_ips=None<span class="p">, </span>auto_healing=None<span class="p">, </span>custom_configure_recipes=None<span class="p">, </span>custom_deploy_recipes=None<span class="p">, </span>custom_instance_profile_arn=None<span class="p">, </span>custom_json=None<span class="p">, </span>custom_security_group_ids=None<span class="p">, </span>custom_setup_recipes=None<span class="p">, </span>custom_shutdown_recipes=None<span class="p">, </span>custom_undeploy_recipes=None<span class="p">, </span>drain_elb_on_shutdown=None<span class="p">, </span>ebs_volumes=None<span class="p">, </span>elastic_load_balancer=None<span class="p">, </span>install_updates_on_boot=None<span class="p">, </span>instance_shutdown_timeout=None<span class="p">, </span>jvm_options=None<span class="p">, </span>jvm_type=None<span class="p">, </span>jvm_version=None<span class="p">, </span>name=None<span class="p">, </span>stack_id=None<span class="p">, </span>system_packages=None<span class="p">, </span>use_ebs_optimized_instances=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewJavaAppLayer<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#JavaAppLayerArgs">JavaAppLayerArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#JavaAppLayer">JavaAppLayer</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.JavaAppLayer.html">JavaAppLayer</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.JavaAppLayerArgs.html">JavaAppLayerArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">App<wbr>Server<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword for the application container to use. Defaults to &#34;tomcat&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">App<wbr>Server<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of the selected application container to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Assign<wbr>Elastic<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to automatically assign an elastic IP address to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Assign<wbr>Public<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}For stacks belonging to a VPC, whether to automatically assign a public IP address to each of the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Healing<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable auto-healing for the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Configure<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Deploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM profile that will be used for the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Ids for a set of security groups to apply to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Setup<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Shutdown<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Undeploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Drain<wbr>Elb<wbr>On<wbr>Shutdown<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable Elastic Load Balancing connection draining.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#javaapplayerebsvolume">List&lt;Java<wbr>App<wbr>Layer<wbr>Ebs<wbr>Volume<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}`ebs_volume` blocks, as described below, will each create an EBS volume and connect it to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of an Elastic Load Balancer to attach to this layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to install OS and package updates on each instance when it boots.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Shutdown<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time, in seconds, that OpsWorks will wait for Chef to complete after triggering the Shutdown event.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jvm<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Options to set for the JVM.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jvm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword for the type of JVM to use. Defaults to `openjdk`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jvm<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of JVM to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the layer.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the layer will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">System<wbr>Packages<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Names of a set of system packages to install on the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Ebs<wbr>Optimized<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to use EBS-optimized instances.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">App<wbr>Server<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Keyword for the application container to use. Defaults to &#34;tomcat&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">App<wbr>Server<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Version of the selected application container to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Assign<wbr>Elastic<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to automatically assign an elastic IP address to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Assign<wbr>Public<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}For stacks belonging to a VPC, whether to automatically assign a public IP address to each of the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Healing<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable auto-healing for the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Configure<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Deploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM profile that will be used for the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Ids for a set of security groups to apply to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Setup<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Shutdown<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Undeploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Drain<wbr>Elb<wbr>On<wbr>Shutdown<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable Elastic Load Balancing connection draining.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#javaapplayerebsvolume">[]Java<wbr>App<wbr>Layer<wbr>Ebs<wbr>Volume</a></span>
    </dt>
    <dd>{{% md %}}`ebs_volume` blocks, as described below, will each create an EBS volume and connect it to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of an Elastic Load Balancer to attach to this layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to install OS and package updates on each instance when it boots.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Shutdown<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time, in seconds, that OpsWorks will wait for Chef to complete after triggering the Shutdown event.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jvm<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Options to set for the JVM.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jvm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Keyword for the type of JVM to use. Defaults to `openjdk`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jvm<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Version of JVM to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the layer.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the layer will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">System<wbr>Packages<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Names of a set of system packages to install on the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Ebs<wbr>Optimized<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to use EBS-optimized instances.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">app<wbr>Server<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword for the application container to use. Defaults to &#34;tomcat&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">app<wbr>Server<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of the selected application container to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Assign<wbr>Elastic<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to automatically assign an elastic IP address to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Assign<wbr>Public<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}For stacks belonging to a VPC, whether to automatically assign a public IP address to each of the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Healing<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable auto-healing for the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Configure<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Deploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM profile that will be used for the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Ids for a set of security groups to apply to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Setup<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Shutdown<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Undeploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">drain<wbr>Elb<wbr>On<wbr>Shutdown<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable Elastic Load Balancing connection draining.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#javaapplayerebsvolume">Java<wbr>App<wbr>Layer<wbr>Ebs<wbr>Volume[]?</a></span>
    </dt>
    <dd>{{% md %}}`ebs_volume` blocks, as described below, will each create an EBS volume and connect it to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic<wbr>Load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of an Elastic Load Balancer to attach to this layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to install OS and package updates on each instance when it boots.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Shutdown<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time, in seconds, that OpsWorks will wait for Chef to complete after triggering the Shutdown event.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jvm<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Options to set for the JVM.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jvm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword for the type of JVM to use. Defaults to `openjdk`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jvm<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of JVM to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the layer.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the layer will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">system<wbr>Packages<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Names of a set of system packages to install on the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use<wbr>Ebs<wbr>Optimized<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to use EBS-optimized instances.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">app_<wbr>server<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Keyword for the application container to use. Defaults to &#34;tomcat&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">app_<wbr>server_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Version of the selected application container to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>assign_<wbr>elastic_<wbr>ips<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to automatically assign an elastic IP address to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>assign_<wbr>public_<wbr>ips<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}For stacks belonging to a VPC, whether to automatically assign a public IP address to each of the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>healing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable auto-healing for the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>configure_<wbr>recipes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>deploy_<wbr>recipes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>instance_<wbr>profile_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM profile that will be used for the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>json<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Ids for a set of security groups to apply to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>setup_<wbr>recipes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>shutdown_<wbr>recipes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>undeploy_<wbr>recipes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">drain_<wbr>elb_<wbr>on_<wbr>shutdown<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable Elastic Load Balancing connection draining.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#javaapplayerebsvolume">List[Java<wbr>App<wbr>Layer<wbr>Ebs<wbr>Volume]</a></span>
    </dt>
    <dd>{{% md %}}`ebs_volume` blocks, as described below, will each create an EBS volume and connect it to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic_<wbr>load_<wbr>balancer<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of an Elastic Load Balancer to attach to this layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">install_<wbr>updates_<wbr>on_<wbr>boot<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to install OS and package updates on each instance when it boots.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>shutdown_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time, in seconds, that OpsWorks will wait for Chef to complete after triggering the Shutdown event.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jvm_<wbr>options<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Options to set for the JVM.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jvm_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Keyword for the type of JVM to use. Defaults to `openjdk`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jvm_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Version of JVM to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the layer.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stack_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the stack the layer will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">system_<wbr>packages<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Names of a set of system packages to install on the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use_<wbr>ebs_<wbr>optimized_<wbr>instances<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to use EBS-optimized instances.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## JavaAppLayer Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">App<wbr>Server<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword for the application container to use. Defaults to &#34;tomcat&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">App<wbr>Server<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of the selected application container to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Assign<wbr>Elastic<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to automatically assign an elastic IP address to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Assign<wbr>Public<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}For stacks belonging to a VPC, whether to automatically assign a public IP address to each of the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Healing<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable auto-healing for the layer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Configure<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Deploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM profile that will be used for the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the layer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Ids for a set of security groups to apply to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Setup<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Shutdown<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Undeploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Drain<wbr>Elb<wbr>On<wbr>Shutdown<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable Elastic Load Balancing connection draining.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#javaapplayerebsvolume">List&lt;Java<wbr>App<wbr>Layer<wbr>Ebs<wbr>Volume&gt;?</a></span>
    </dt>
    <dd>{{% md %}}`ebs_volume` blocks, as described below, will each create an EBS volume and connect it to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elastic<wbr>Load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of an Elastic Load Balancer to attach to this layer
{{% /md %}}</dd>

    <dt class="property-"
            title="">Install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to install OS and package updates on each instance when it boots.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Shutdown<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time, in seconds, that OpsWorks will wait for Chef to complete after triggering the Shutdown event.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Jvm<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Options to set for the JVM.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Jvm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword for the type of JVM to use. Defaults to `openjdk`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Jvm<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of JVM to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the layer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the layer will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">System<wbr>Packages<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Names of a set of system packages to install on the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Use<wbr>Ebs<wbr>Optimized<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to use EBS-optimized instances.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">App<wbr>Server<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Keyword for the application container to use. Defaults to &#34;tomcat&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">App<wbr>Server<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Version of the selected application container to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Assign<wbr>Elastic<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to automatically assign an elastic IP address to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Assign<wbr>Public<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}For stacks belonging to a VPC, whether to automatically assign a public IP address to each of the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Healing<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable auto-healing for the layer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Configure<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Deploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM profile that will be used for the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the layer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Ids for a set of security groups to apply to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Setup<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Shutdown<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Undeploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Drain<wbr>Elb<wbr>On<wbr>Shutdown<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable Elastic Load Balancing connection draining.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#javaapplayerebsvolume">[]Java<wbr>App<wbr>Layer<wbr>Ebs<wbr>Volume</a></span>
    </dt>
    <dd>{{% md %}}`ebs_volume` blocks, as described below, will each create an EBS volume and connect it to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elastic<wbr>Load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of an Elastic Load Balancer to attach to this layer
{{% /md %}}</dd>

    <dt class="property-"
            title="">Install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to install OS and package updates on each instance when it boots.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Shutdown<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time, in seconds, that OpsWorks will wait for Chef to complete after triggering the Shutdown event.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Jvm<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Options to set for the JVM.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Jvm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Keyword for the type of JVM to use. Defaults to `openjdk`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Jvm<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Version of JVM to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the layer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the layer will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">System<wbr>Packages<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Names of a set of system packages to install on the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Use<wbr>Ebs<wbr>Optimized<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to use EBS-optimized instances.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">app<wbr>Server<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword for the application container to use. Defaults to &#34;tomcat&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">app<wbr>Server<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of the selected application container to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto<wbr>Assign<wbr>Elastic<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to automatically assign an elastic IP address to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto<wbr>Assign<wbr>Public<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}For stacks belonging to a VPC, whether to automatically assign a public IP address to each of the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto<wbr>Healing<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable auto-healing for the layer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">custom<wbr>Configure<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">custom<wbr>Deploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">custom<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM profile that will be used for the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the layer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">custom<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Ids for a set of security groups to apply to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">custom<wbr>Setup<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">custom<wbr>Shutdown<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">custom<wbr>Undeploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">drain<wbr>Elb<wbr>On<wbr>Shutdown<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable Elastic Load Balancing connection draining.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs<wbr>Volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#javaapplayerebsvolume">Java<wbr>App<wbr>Layer<wbr>Ebs<wbr>Volume[]?</a></span>
    </dt>
    <dd>{{% md %}}`ebs_volume` blocks, as described below, will each create an EBS volume and connect it to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">elastic<wbr>Load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of an Elastic Load Balancer to attach to this layer
{{% /md %}}</dd>

    <dt class="property-"
            title="">install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to install OS and package updates on each instance when it boots.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Shutdown<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time, in seconds, that OpsWorks will wait for Chef to complete after triggering the Shutdown event.
{{% /md %}}</dd>

    <dt class="property-"
            title="">jvm<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Options to set for the JVM.
{{% /md %}}</dd>

    <dt class="property-"
            title="">jvm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword for the type of JVM to use. Defaults to `openjdk`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">jvm<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of JVM to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the layer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the layer will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">system<wbr>Packages<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Names of a set of system packages to install on the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">use<wbr>Ebs<wbr>Optimized<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to use EBS-optimized instances.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">app_<wbr>server<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Keyword for the application container to use. Defaults to &#34;tomcat&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">app_<wbr>server_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Version of the selected application container to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto_<wbr>assign_<wbr>elastic_<wbr>ips<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to automatically assign an elastic IP address to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto_<wbr>assign_<wbr>public_<wbr>ips<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}For stacks belonging to a VPC, whether to automatically assign a public IP address to each of the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto_<wbr>healing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable auto-healing for the layer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">custom_<wbr>configure_<wbr>recipes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">custom_<wbr>deploy_<wbr>recipes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">custom_<wbr>instance_<wbr>profile_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM profile that will be used for the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">custom_<wbr>json<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the layer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">custom_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Ids for a set of security groups to apply to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">custom_<wbr>setup_<wbr>recipes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">custom_<wbr>shutdown_<wbr>recipes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">custom_<wbr>undeploy_<wbr>recipes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">drain_<wbr>elb_<wbr>on_<wbr>shutdown<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable Elastic Load Balancing connection draining.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs_<wbr>volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#javaapplayerebsvolume">List[Java<wbr>App<wbr>Layer<wbr>Ebs<wbr>Volume]</a></span>
    </dt>
    <dd>{{% md %}}`ebs_volume` blocks, as described below, will each create an EBS volume and connect it to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">elastic_<wbr>load_<wbr>balancer<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of an Elastic Load Balancer to attach to this layer
{{% /md %}}</dd>

    <dt class="property-"
            title="">install_<wbr>updates_<wbr>on_<wbr>boot<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to install OS and package updates on each instance when it boots.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>shutdown_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time, in seconds, that OpsWorks will wait for Chef to complete after triggering the Shutdown event.
{{% /md %}}</dd>

    <dt class="property-"
            title="">jvm_<wbr>options<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Options to set for the JVM.
{{% /md %}}</dd>

    <dt class="property-"
            title="">jvm_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Keyword for the type of JVM to use. Defaults to `openjdk`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">jvm_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Version of JVM to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the layer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">stack_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the stack the layer will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">system_<wbr>packages<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Names of a set of system packages to install on the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">use_<wbr>ebs_<wbr>optimized_<wbr>instances<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to use EBS-optimized instances.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing JavaAppLayer Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#JavaAppLayerState">JavaAppLayerState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#JavaAppLayer">JavaAppLayer</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>app_server=None<span class="p">, </span>app_server_version=None<span class="p">, </span>auto_assign_elastic_ips=None<span class="p">, </span>auto_assign_public_ips=None<span class="p">, </span>auto_healing=None<span class="p">, </span>custom_configure_recipes=None<span class="p">, </span>custom_deploy_recipes=None<span class="p">, </span>custom_instance_profile_arn=None<span class="p">, </span>custom_json=None<span class="p">, </span>custom_security_group_ids=None<span class="p">, </span>custom_setup_recipes=None<span class="p">, </span>custom_shutdown_recipes=None<span class="p">, </span>custom_undeploy_recipes=None<span class="p">, </span>drain_elb_on_shutdown=None<span class="p">, </span>ebs_volumes=None<span class="p">, </span>elastic_load_balancer=None<span class="p">, </span>install_updates_on_boot=None<span class="p">, </span>instance_shutdown_timeout=None<span class="p">, </span>jvm_options=None<span class="p">, </span>jvm_type=None<span class="p">, </span>jvm_version=None<span class="p">, </span>name=None<span class="p">, </span>stack_id=None<span class="p">, </span>system_packages=None<span class="p">, </span>use_ebs_optimized_instances=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetJavaAppLayer<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#JavaAppLayerState">JavaAppLayerState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#JavaAppLayer">JavaAppLayer</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.JavaAppLayer.html">JavaAppLayer</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.JavaAppLayerState.html">JavaAppLayerState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing JavaAppLayer resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">App<wbr>Server<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword for the application container to use. Defaults to &#34;tomcat&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">App<wbr>Server<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of the selected application container to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Assign<wbr>Elastic<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to automatically assign an elastic IP address to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Assign<wbr>Public<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}For stacks belonging to a VPC, whether to automatically assign a public IP address to each of the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Healing<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable auto-healing for the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Configure<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Deploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM profile that will be used for the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Ids for a set of security groups to apply to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Setup<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Shutdown<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Undeploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Drain<wbr>Elb<wbr>On<wbr>Shutdown<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable Elastic Load Balancing connection draining.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#javaapplayerebsvolume">List&lt;Java<wbr>App<wbr>Layer<wbr>Ebs<wbr>Volume<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}`ebs_volume` blocks, as described below, will each create an EBS volume and connect it to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of an Elastic Load Balancer to attach to this layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to install OS and package updates on each instance when it boots.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Shutdown<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time, in seconds, that OpsWorks will wait for Chef to complete after triggering the Shutdown event.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jvm<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Options to set for the JVM.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jvm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword for the type of JVM to use. Defaults to `openjdk`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jvm<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of JVM to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the stack the layer will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">System<wbr>Packages<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Names of a set of system packages to install on the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Ebs<wbr>Optimized<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to use EBS-optimized instances.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">App<wbr>Server<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Keyword for the application container to use. Defaults to &#34;tomcat&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">App<wbr>Server<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Version of the selected application container to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Assign<wbr>Elastic<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to automatically assign an elastic IP address to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Assign<wbr>Public<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}For stacks belonging to a VPC, whether to automatically assign a public IP address to each of the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Healing<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable auto-healing for the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Configure<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Deploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM profile that will be used for the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Ids for a set of security groups to apply to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Setup<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Shutdown<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Undeploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Drain<wbr>Elb<wbr>On<wbr>Shutdown<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable Elastic Load Balancing connection draining.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#javaapplayerebsvolume">[]Java<wbr>App<wbr>Layer<wbr>Ebs<wbr>Volume</a></span>
    </dt>
    <dd>{{% md %}}`ebs_volume` blocks, as described below, will each create an EBS volume and connect it to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of an Elastic Load Balancer to attach to this layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to install OS and package updates on each instance when it boots.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Shutdown<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time, in seconds, that OpsWorks will wait for Chef to complete after triggering the Shutdown event.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jvm<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Options to set for the JVM.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jvm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Keyword for the type of JVM to use. Defaults to `openjdk`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Jvm<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Version of JVM to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the layer will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">System<wbr>Packages<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Names of a set of system packages to install on the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Ebs<wbr>Optimized<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to use EBS-optimized instances.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">app<wbr>Server<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword for the application container to use. Defaults to &#34;tomcat&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">app<wbr>Server<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of the selected application container to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Assign<wbr>Elastic<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to automatically assign an elastic IP address to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Assign<wbr>Public<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}For stacks belonging to a VPC, whether to automatically assign a public IP address to each of the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Healing<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable auto-healing for the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Configure<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Deploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM profile that will be used for the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Ids for a set of security groups to apply to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Setup<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Shutdown<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Undeploy<wbr>Recipes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">drain<wbr>Elb<wbr>On<wbr>Shutdown<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable Elastic Load Balancing connection draining.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#javaapplayerebsvolume">Java<wbr>App<wbr>Layer<wbr>Ebs<wbr>Volume[]?</a></span>
    </dt>
    <dd>{{% md %}}`ebs_volume` blocks, as described below, will each create an EBS volume and connect it to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic<wbr>Load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of an Elastic Load Balancer to attach to this layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to install OS and package updates on each instance when it boots.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Shutdown<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time, in seconds, that OpsWorks will wait for Chef to complete after triggering the Shutdown event.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jvm<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Options to set for the JVM.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jvm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword for the type of JVM to use. Defaults to `openjdk`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jvm<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of JVM to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the stack the layer will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">system<wbr>Packages<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Names of a set of system packages to install on the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use<wbr>Ebs<wbr>Optimized<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to use EBS-optimized instances.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">app_<wbr>server<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Keyword for the application container to use. Defaults to &#34;tomcat&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">app_<wbr>server_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Version of the selected application container to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>assign_<wbr>elastic_<wbr>ips<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to automatically assign an elastic IP address to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>assign_<wbr>public_<wbr>ips<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}For stacks belonging to a VPC, whether to automatically assign a public IP address to each of the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>healing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable auto-healing for the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>configure_<wbr>recipes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>deploy_<wbr>recipes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>instance_<wbr>profile_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM profile that will be used for the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>json<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Ids for a set of security groups to apply to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>setup_<wbr>recipes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>shutdown_<wbr>recipes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>undeploy_<wbr>recipes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">drain_<wbr>elb_<wbr>on_<wbr>shutdown<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable Elastic Load Balancing connection draining.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#javaapplayerebsvolume">List[Java<wbr>App<wbr>Layer<wbr>Ebs<wbr>Volume]</a></span>
    </dt>
    <dd>{{% md %}}`ebs_volume` blocks, as described below, will each create an EBS volume and connect it to the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic_<wbr>load_<wbr>balancer<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of an Elastic Load Balancer to attach to this layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">install_<wbr>updates_<wbr>on_<wbr>boot<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to install OS and package updates on each instance when it boots.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>shutdown_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time, in seconds, that OpsWorks will wait for Chef to complete after triggering the Shutdown event.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jvm_<wbr>options<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Options to set for the JVM.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jvm_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Keyword for the type of JVM to use. Defaults to `openjdk`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">jvm_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Version of JVM to use. Defaults to &#34;7&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A human-readable name for the layer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stack_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the stack the layer will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">system_<wbr>packages<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Names of a set of system packages to install on the layer&#39;s instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use_<wbr>ebs_<wbr>optimized_<wbr>instances<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to use EBS-optimized instances.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### JavaAppLayerEbsVolume
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#JavaAppLayerEbsVolume">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#JavaAppLayerEbsVolume">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#JavaAppLayerEbsVolumeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#JavaAppLayerEbsVolumeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.JavaAppLayerEbsVolumeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.JavaAppLayerEbsVolume.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Mount<wbr>Point<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Number<wbr>Of<wbr>Disks<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Raid<wbr>Level<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Mount<wbr>Point<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Number<wbr>Of<wbr>Disks<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Raid<wbr>Level<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">mount<wbr>Point<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">number<wbr>Of<wbr>Disks<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">raid<wbr>Level<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">mount<wbr>Point<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">number<wbr>Of<wbr>Disks<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">raid<wbr>Level<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








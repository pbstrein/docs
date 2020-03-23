
---
title: "Stack"
block_external_search_index: true
---

Provides an OpsWorks stack resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const main = new aws.opsworks.Stack("main", {
    customJson: `{
 "foobar": {
    "version": "1.0.0"
  }
}
`,
    defaultInstanceProfileArn: aws_iam_instance_profile_opsworks.arn,
    region: "us-west-1",
    serviceRoleArn: aws_iam_role_opsworks.arn,
    tags: {
        Name: "foobar-stack",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/opsworks_stack.html.markdown.



## Create a Stack Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#Stack">Stack</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#StackArgs">StackArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Stack</span><span class="p">(resource_name, opts=None, </span>agent_version=None<span class="p">, </span>berkshelf_version=None<span class="p">, </span>color=None<span class="p">, </span>configuration_manager_name=None<span class="p">, </span>configuration_manager_version=None<span class="p">, </span>custom_cookbooks_sources=None<span class="p">, </span>custom_json=None<span class="p">, </span>default_availability_zone=None<span class="p">, </span>default_instance_profile_arn=None<span class="p">, </span>default_os=None<span class="p">, </span>default_root_device_type=None<span class="p">, </span>default_ssh_key_name=None<span class="p">, </span>default_subnet_id=None<span class="p">, </span>hostname_theme=None<span class="p">, </span>manage_berkshelf=None<span class="p">, </span>name=None<span class="p">, </span>region=None<span class="p">, </span>service_role_arn=None<span class="p">, </span>tags=None<span class="p">, </span>use_custom_cookbooks=None<span class="p">, </span>use_opsworks_security_groups=None<span class="p">, </span>vpc_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewStack<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#StackArgs">StackArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#Stack">Stack</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.Stack.html">Stack</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.StackArgs.html">StackArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If set to `&#34;LATEST&#34;`, OpsWorks will automatically install the latest version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Berkshelf<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `manage_berkshelf` is enabled, the version of Berkshelf to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Color<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Color to paint next to the stack&#39;s resources in the OpsWorks console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Manager<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the configuration manager to use. Defaults to &#34;Chef&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Manager<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of the configuration manager to use. Defaults to &#34;11.4&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Cookbooks<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#stackcustomcookbookssource">List&lt;Stack<wbr>Custom<wbr>Cookbooks<wbr>Source<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}When `use_custom_cookbooks` is set, provide this sub-object as
described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the entire stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default. This is required unless you set `vpc_id`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Default<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM Instance Profile that created instances
will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Os<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of OS that will be installed on instances by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Id of the subnet in which instances will be created by default. Mandatory
if `vpc_id` is set, and forbidden if it isn&#39;t.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hostname<wbr>Theme<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword representing the naming scheme that will be used for instance hostnames
within this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Manage<wbr>Berkshelf<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether Opsworks will run Berkshelf for this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the stack.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the region where the stack will exist.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that the OpsWorks service will act as.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Custom<wbr>Cookbooks<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the custom cookbook settings are
enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Opsworks<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the standard OpsWorks
security groups apply to created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the VPC that this stack belongs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If set to `&#34;LATEST&#34;`, OpsWorks will automatically install the latest version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Berkshelf<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If `manage_berkshelf` is enabled, the version of Berkshelf to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Color<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Color to paint next to the stack&#39;s resources in the OpsWorks console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Manager<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the configuration manager to use. Defaults to &#34;Chef&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Manager<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Version of the configuration manager to use. Defaults to &#34;11.4&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Cookbooks<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#stackcustomcookbookssource">[]Stack<wbr>Custom<wbr>Cookbooks<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}When `use_custom_cookbooks` is set, provide this sub-object as
described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the entire stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default. This is required unless you set `vpc_id`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Default<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM Instance Profile that created instances
will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Os<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of OS that will be installed on instances by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Id of the subnet in which instances will be created by default. Mandatory
if `vpc_id` is set, and forbidden if it isn&#39;t.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hostname<wbr>Theme<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Keyword representing the naming scheme that will be used for instance hostnames
within this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Manage<wbr>Berkshelf<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether Opsworks will run Berkshelf for this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the stack.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the region where the stack will exist.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that the OpsWorks service will act as.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Custom<wbr>Cookbooks<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the custom cookbook settings are
enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Opsworks<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the standard OpsWorks
security groups apply to created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The id of the VPC that this stack belongs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If set to `&#34;LATEST&#34;`, OpsWorks will automatically install the latest version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">berkshelf<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `manage_berkshelf` is enabled, the version of Berkshelf to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">color<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Color to paint next to the stack&#39;s resources in the OpsWorks console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<wbr>Manager<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the configuration manager to use. Defaults to &#34;Chef&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<wbr>Manager<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of the configuration manager to use. Defaults to &#34;11.4&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Cookbooks<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#stackcustomcookbookssource">Stack<wbr>Custom<wbr>Cookbooks<wbr>Source[]?</a></span>
    </dt>
    <dd>{{% md %}}When `use_custom_cookbooks` is set, provide this sub-object as
described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the entire stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default. This is required unless you set `vpc_id`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">default<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM Instance Profile that created instances
will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Os<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of OS that will be installed on instances by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Id of the subnet in which instances will be created by default. Mandatory
if `vpc_id` is set, and forbidden if it isn&#39;t.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hostname<wbr>Theme<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword representing the naming scheme that will be used for instance hostnames
within this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">manage<wbr>Berkshelf<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether Opsworks will run Berkshelf for this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the stack.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the region where the stack will exist.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that the OpsWorks service will act as.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use<wbr>Custom<wbr>Cookbooks<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the custom cookbook settings are
enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use<wbr>Opsworks<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the standard OpsWorks
security groups apply to created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the VPC that this stack belongs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">agent_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If set to `&#34;LATEST&#34;`, OpsWorks will automatically install the latest version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">berkshelf_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If `manage_berkshelf` is enabled, the version of Berkshelf to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">color<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Color to paint next to the stack&#39;s resources in the OpsWorks console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration_<wbr>manager_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the configuration manager to use. Defaults to &#34;Chef&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration_<wbr>manager_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Version of the configuration manager to use. Defaults to &#34;11.4&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>cookbooks_<wbr>sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#stackcustomcookbookssource">List[Stack<wbr>Custom<wbr>Cookbooks<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}When `use_custom_cookbooks` is set, provide this sub-object as
described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>json<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the entire stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default. This is required unless you set `vpc_id`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">default_<wbr>instance_<wbr>profile_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM Instance Profile that created instances
will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>os<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of OS that will be installed on instances by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>root_<wbr>device_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>ssh_<wbr>key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Id of the subnet in which instances will be created by default. Mandatory
if `vpc_id` is set, and forbidden if it isn&#39;t.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hostname_<wbr>theme<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Keyword representing the naming scheme that will be used for instance hostnames
within this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">manage_<wbr>berkshelf<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether Opsworks will run Berkshelf for this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the stack.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the region where the stack will exist.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that the OpsWorks service will act as.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use_<wbr>custom_<wbr>cookbooks<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the custom cookbook settings are
enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use_<wbr>opsworks_<wbr>security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the standard OpsWorks
security groups apply to created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the VPC that this stack belongs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Stack Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}If set to `&#34;LATEST&#34;`, OpsWorks will automatically install the latest version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Berkshelf<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `manage_berkshelf` is enabled, the version of Berkshelf to use.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Color<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Color to paint next to the stack&#39;s resources in the OpsWorks console.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<wbr>Manager<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the configuration manager to use. Defaults to &#34;Chef&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<wbr>Manager<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of the configuration manager to use. Defaults to &#34;11.4&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Cookbooks<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#stackcustomcookbookssource">List&lt;Stack<wbr>Custom<wbr>Cookbooks<wbr>Source&gt;</a></span>
    </dt>
    <dd>{{% md %}}When `use_custom_cookbooks` is set, provide this sub-object as
described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the entire stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default. This is required unless you set `vpc_id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM Instance Profile that created instances
will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Os<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of OS that will be installed on instances by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Id of the subnet in which instances will be created by default. Mandatory
if `vpc_id` is set, and forbidden if it isn&#39;t.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hostname<wbr>Theme<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword representing the naming scheme that will be used for instance hostnames
within this stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Manage<wbr>Berkshelf<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether Opsworks will run Berkshelf for this stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the region where the stack will exist.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that the OpsWorks service will act as.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stack<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Use<wbr>Custom<wbr>Cookbooks<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the custom cookbook settings are
enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Use<wbr>Opsworks<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the standard OpsWorks
security groups apply to created instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the VPC that this stack belongs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}If set to `&#34;LATEST&#34;`, OpsWorks will automatically install the latest version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Berkshelf<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If `manage_berkshelf` is enabled, the version of Berkshelf to use.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Color<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Color to paint next to the stack&#39;s resources in the OpsWorks console.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<wbr>Manager<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the configuration manager to use. Defaults to &#34;Chef&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<wbr>Manager<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Version of the configuration manager to use. Defaults to &#34;11.4&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Cookbooks<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#stackcustomcookbookssource">[]Stack<wbr>Custom<wbr>Cookbooks<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}When `use_custom_cookbooks` is set, provide this sub-object as
described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the entire stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default. This is required unless you set `vpc_id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM Instance Profile that created instances
will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Os<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of OS that will be installed on instances by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Id of the subnet in which instances will be created by default. Mandatory
if `vpc_id` is set, and forbidden if it isn&#39;t.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hostname<wbr>Theme<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Keyword representing the naming scheme that will be used for instance hostnames
within this stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Manage<wbr>Berkshelf<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether Opsworks will run Berkshelf for this stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the region where the stack will exist.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that the OpsWorks service will act as.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stack<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Use<wbr>Custom<wbr>Cookbooks<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the custom cookbook settings are
enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Use<wbr>Opsworks<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the standard OpsWorks
security groups apply to created instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the VPC that this stack belongs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}If set to `&#34;LATEST&#34;`, OpsWorks will automatically install the latest version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">berkshelf<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `manage_berkshelf` is enabled, the version of Berkshelf to use.
{{% /md %}}</dd>

    <dt class="property-"
            title="">color<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Color to paint next to the stack&#39;s resources in the OpsWorks console.
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration<wbr>Manager<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the configuration manager to use. Defaults to &#34;Chef&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration<wbr>Manager<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of the configuration manager to use. Defaults to &#34;11.4&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">custom<wbr>Cookbooks<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#stackcustomcookbookssource">Stack<wbr>Custom<wbr>Cookbooks<wbr>Source[]</a></span>
    </dt>
    <dd>{{% md %}}When `use_custom_cookbooks` is set, provide this sub-object as
described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the entire stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default. This is required unless you set `vpc_id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM Instance Profile that created instances
will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Os<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of OS that will be installed on instances by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Id of the subnet in which instances will be created by default. Mandatory
if `vpc_id` is set, and forbidden if it isn&#39;t.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hostname<wbr>Theme<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword representing the naming scheme that will be used for instance hostnames
within this stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">manage<wbr>Berkshelf<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether Opsworks will run Berkshelf for this stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the region where the stack will exist.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that the OpsWorks service will act as.
{{% /md %}}</dd>

    <dt class="property-"
            title="">stack<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">use<wbr>Custom<wbr>Cookbooks<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the custom cookbook settings are
enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">use<wbr>Opsworks<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the standard OpsWorks
security groups apply to created instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the VPC that this stack belongs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">agent_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If set to `&#34;LATEST&#34;`, OpsWorks will automatically install the latest version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">berkshelf_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If `manage_berkshelf` is enabled, the version of Berkshelf to use.
{{% /md %}}</dd>

    <dt class="property-"
            title="">color<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Color to paint next to the stack&#39;s resources in the OpsWorks console.
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration_<wbr>manager_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the configuration manager to use. Defaults to &#34;Chef&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration_<wbr>manager_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Version of the configuration manager to use. Defaults to &#34;11.4&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">custom_<wbr>cookbooks_<wbr>sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#stackcustomcookbookssource">List[Stack<wbr>Custom<wbr>Cookbooks<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}When `use_custom_cookbooks` is set, provide this sub-object as
described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">custom_<wbr>json<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the entire stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default. This is required unless you set `vpc_id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>instance_<wbr>profile_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM Instance Profile that created instances
will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>os<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of OS that will be installed on instances by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>root_<wbr>device_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>ssh_<wbr>key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Id of the subnet in which instances will be created by default. Mandatory
if `vpc_id` is set, and forbidden if it isn&#39;t.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hostname_<wbr>theme<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Keyword representing the naming scheme that will be used for instance hostnames
within this stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">manage_<wbr>berkshelf<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether Opsworks will run Berkshelf for this stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the stack.
{{% /md %}}</dd>

    <dt class="property-"
            title="">region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the region where the stack will exist.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that the OpsWorks service will act as.
{{% /md %}}</dd>

    <dt class="property-"
            title="">stack_<wbr>endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">use_<wbr>custom_<wbr>cookbooks<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the custom cookbook settings are
enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">use_<wbr>opsworks_<wbr>security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the standard OpsWorks
security groups apply to created instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the VPC that this stack belongs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Stack Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#StackState">StackState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#Stack">Stack</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>agent_version=None<span class="p">, </span>arn=None<span class="p">, </span>berkshelf_version=None<span class="p">, </span>color=None<span class="p">, </span>configuration_manager_name=None<span class="p">, </span>configuration_manager_version=None<span class="p">, </span>custom_cookbooks_sources=None<span class="p">, </span>custom_json=None<span class="p">, </span>default_availability_zone=None<span class="p">, </span>default_instance_profile_arn=None<span class="p">, </span>default_os=None<span class="p">, </span>default_root_device_type=None<span class="p">, </span>default_ssh_key_name=None<span class="p">, </span>default_subnet_id=None<span class="p">, </span>hostname_theme=None<span class="p">, </span>manage_berkshelf=None<span class="p">, </span>name=None<span class="p">, </span>region=None<span class="p">, </span>service_role_arn=None<span class="p">, </span>stack_endpoint=None<span class="p">, </span>tags=None<span class="p">, </span>use_custom_cookbooks=None<span class="p">, </span>use_opsworks_security_groups=None<span class="p">, </span>vpc_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetStack<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#StackState">StackState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#Stack">Stack</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.Stack.html">Stack</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.StackState.html">StackState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Stack resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If set to `&#34;LATEST&#34;`, OpsWorks will automatically install the latest version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Berkshelf<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `manage_berkshelf` is enabled, the version of Berkshelf to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Color<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Color to paint next to the stack&#39;s resources in the OpsWorks console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Manager<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the configuration manager to use. Defaults to &#34;Chef&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Manager<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of the configuration manager to use. Defaults to &#34;11.4&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Cookbooks<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#stackcustomcookbookssource">List&lt;Stack<wbr>Custom<wbr>Cookbooks<wbr>Source<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}When `use_custom_cookbooks` is set, provide this sub-object as
described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the entire stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default. This is required unless you set `vpc_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM Instance Profile that created instances
will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Os<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of OS that will be installed on instances by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Id of the subnet in which instances will be created by default. Mandatory
if `vpc_id` is set, and forbidden if it isn&#39;t.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hostname<wbr>Theme<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword representing the naming scheme that will be used for instance hostnames
within this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Manage<wbr>Berkshelf<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether Opsworks will run Berkshelf for this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the region where the stack will exist.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that the OpsWorks service will act as.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stack<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Custom<wbr>Cookbooks<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the custom cookbook settings are
enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Opsworks<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the standard OpsWorks
security groups apply to created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the VPC that this stack belongs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If set to `&#34;LATEST&#34;`, OpsWorks will automatically install the latest version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Berkshelf<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If `manage_berkshelf` is enabled, the version of Berkshelf to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Color<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Color to paint next to the stack&#39;s resources in the OpsWorks console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Manager<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the configuration manager to use. Defaults to &#34;Chef&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Manager<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Version of the configuration manager to use. Defaults to &#34;11.4&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Cookbooks<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#stackcustomcookbookssource">[]Stack<wbr>Custom<wbr>Cookbooks<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}When `use_custom_cookbooks` is set, provide this sub-object as
described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the entire stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default. This is required unless you set `vpc_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM Instance Profile that created instances
will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Os<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of OS that will be installed on instances by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Id of the subnet in which instances will be created by default. Mandatory
if `vpc_id` is set, and forbidden if it isn&#39;t.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hostname<wbr>Theme<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Keyword representing the naming scheme that will be used for instance hostnames
within this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Manage<wbr>Berkshelf<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether Opsworks will run Berkshelf for this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Region<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the region where the stack will exist.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that the OpsWorks service will act as.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stack<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Custom<wbr>Cookbooks<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the custom cookbook settings are
enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Opsworks<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the standard OpsWorks
security groups apply to created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The id of the VPC that this stack belongs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If set to `&#34;LATEST&#34;`, OpsWorks will automatically install the latest version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">berkshelf<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `manage_berkshelf` is enabled, the version of Berkshelf to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">color<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Color to paint next to the stack&#39;s resources in the OpsWorks console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<wbr>Manager<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the configuration manager to use. Defaults to &#34;Chef&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<wbr>Manager<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Version of the configuration manager to use. Defaults to &#34;11.4&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Cookbooks<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#stackcustomcookbookssource">Stack<wbr>Custom<wbr>Cookbooks<wbr>Source[]?</a></span>
    </dt>
    <dd>{{% md %}}When `use_custom_cookbooks` is set, provide this sub-object as
described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the entire stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default. This is required unless you set `vpc_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM Instance Profile that created instances
will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Os<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of OS that will be installed on instances by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Id of the subnet in which instances will be created by default. Mandatory
if `vpc_id` is set, and forbidden if it isn&#39;t.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hostname<wbr>Theme<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword representing the naming scheme that will be used for instance hostnames
within this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">manage<wbr>Berkshelf<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether Opsworks will run Berkshelf for this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the region where the stack will exist.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that the OpsWorks service will act as.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stack<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use<wbr>Custom<wbr>Cookbooks<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the custom cookbook settings are
enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use<wbr>Opsworks<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the standard OpsWorks
security groups apply to created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the VPC that this stack belongs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">agent_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If set to `&#34;LATEST&#34;`, OpsWorks will automatically install the latest version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">berkshelf_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If `manage_berkshelf` is enabled, the version of Berkshelf to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">color<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Color to paint next to the stack&#39;s resources in the OpsWorks console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration_<wbr>manager_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the configuration manager to use. Defaults to &#34;Chef&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration_<wbr>manager_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Version of the configuration manager to use. Defaults to &#34;11.4&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>cookbooks_<wbr>sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#stackcustomcookbookssource">List[Stack<wbr>Custom<wbr>Cookbooks<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}When `use_custom_cookbooks` is set, provide this sub-object as
described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>json<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Custom JSON attributes to apply to the entire stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default. This is required unless you set `vpc_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>instance_<wbr>profile_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM Instance Profile that created instances
will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>os<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of OS that will be installed on instances by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>root_<wbr>device_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>ssh_<wbr>key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Id of the subnet in which instances will be created by default. Mandatory
if `vpc_id` is set, and forbidden if it isn&#39;t.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hostname_<wbr>theme<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Keyword representing the naming scheme that will be used for instance hostnames
within this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">manage_<wbr>berkshelf<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether Opsworks will run Berkshelf for this stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the stack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the region where the stack will exist.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that the OpsWorks service will act as.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stack_<wbr>endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use_<wbr>custom_<wbr>cookbooks<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the custom cookbook settings are
enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use_<wbr>opsworks_<wbr>security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value controlling whether the standard OpsWorks
security groups apply to created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the VPC that this stack belongs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### StackCustomCookbooksSource
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#StackCustomCookbooksSource">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#StackCustomCookbooksSource">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#StackCustomCookbooksSourceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#StackCustomCookbooksSourceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.StackCustomCookbooksSourceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.StackCustomCookbooksSource.html">output</a> API doc for this type.
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
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Username<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

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
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Username<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

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
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">username<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

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
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">username<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








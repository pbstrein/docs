
---
title: "Connection"
block_external_search_index: true
---

Provides a Glue Connection resource.

## Example Usage

### Non-VPC Connection

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.glue.Connection("example", {
    connectionProperties: {
        JDBC_CONNECTION_URL: "jdbc:mysql://example.com/exampledatabase",
        PASSWORD: "examplepassword",
        USERNAME: "exampleusername",
    },
});
```

### VPC Connection

For more information, see the [AWS Documentation](https://docs.aws.amazon.com/glue/latest/dg/populate-add-connection.html#connection-JDBC-VPC).

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.glue.Connection("example", {
    connectionProperties: {
        JDBC_CONNECTION_URL: pulumi.interpolate`jdbc:mysql://${aws_rds_cluster_example.endpoint}/exampledatabase`,
        PASSWORD: "examplepassword",
        USERNAME: "exampleusername",
    },
    physicalConnectionRequirements: {
        availabilityZone: aws_subnet_example.availabilityZone,
        securityGroupIdLists: [aws_security_group_example.id],
        subnetId: aws_subnet_example.id,
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/glue_connection.html.markdown.



## Create a Connection Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#Connection">Connection</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#ConnectionArgs">ConnectionArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Connection</span><span class="p">(resource_name, opts=None, </span>catalog_id=None<span class="p">, </span>connection_properties=None<span class="p">, </span>connection_type=None<span class="p">, </span>description=None<span class="p">, </span>match_criterias=None<span class="p">, </span>name=None<span class="p">, </span>physical_connection_requirements=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewConnection<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#ConnectionArgs">ConnectionArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#Connection">Connection</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.Connection.html">Connection</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.ConnectionArgs.html">ConnectionArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Data Catalog in which to create the connection. If none is supplied, the AWS account ID is used by default.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Connection<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}A map of key-value pairs used as parameters for this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the connection. Defaults to `JBDC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Match<wbr>Criterias<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of criteria that can be used in selecting this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Physical<wbr>Connection<wbr>Requirements<span class="property-indicator"></span>
        <span class="property-type"><a href="#connectionphysicalconnectionrequirements">Connection<wbr>Physical<wbr>Connection<wbr>Requirements<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A map of physical connection requirements, such as VPC and SecurityGroup. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the Data Catalog in which to create the connection. If none is supplied, the AWS account ID is used by default.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Connection<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A map of key-value pairs used as parameters for this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the connection. Defaults to `JBDC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Match<wbr>Criterias<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of criteria that can be used in selecting this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Physical<wbr>Connection<wbr>Requirements<span class="property-indicator"></span>
        <span class="property-type"><a href="#connectionphysicalconnectionrequirements">*Connection<wbr>Physical<wbr>Connection<wbr>Requirements</a></span>
    </dt>
    <dd>{{% md %}}A map of physical connection requirements, such as VPC and SecurityGroup. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Data Catalog in which to create the connection. If none is supplied, the AWS account ID is used by default.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">connection<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}A map of key-value pairs used as parameters for this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the connection. Defaults to `JBDC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">match<wbr>Criterias<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of criteria that can be used in selecting this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">physical<wbr>Connection<wbr>Requirements<span class="property-indicator"></span>
        <span class="property-type"><a href="#connectionphysicalconnectionrequirements">Connection<wbr>Physical<wbr>Connection<wbr>Requirements?</a></span>
    </dt>
    <dd>{{% md %}}A map of physical connection requirements, such as VPC and SecurityGroup. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">catalog_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Data Catalog in which to create the connection. If none is supplied, the AWS account ID is used by default.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">connection_<wbr>properties<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A map of key-value pairs used as parameters for this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the connection. Defaults to `JBDC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">match_<wbr>criterias<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of criteria that can be used in selecting this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">physical_<wbr>connection_<wbr>requirements<span class="property-indicator"></span>
        <span class="property-type"><a href="#connectionphysicalconnectionrequirements">Dict[Connection<wbr>Physical<wbr>Connection<wbr>Requirements]</a></span>
    </dt>
    <dd>{{% md %}}A map of physical connection requirements, such as VPC and SecurityGroup. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Connection Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Data Catalog in which to create the connection. If none is supplied, the AWS account ID is used by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connection<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}A map of key-value pairs used as parameters for this connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the connection. Defaults to `JBDC`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Match<wbr>Criterias<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of criteria that can be used in selecting this connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Physical<wbr>Connection<wbr>Requirements<span class="property-indicator"></span>
        <span class="property-type"><a href="#connectionphysicalconnectionrequirements">Connection<wbr>Physical<wbr>Connection<wbr>Requirements?</a></span>
    </dt>
    <dd>{{% md %}}A map of physical connection requirements, such as VPC and SecurityGroup. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Data Catalog in which to create the connection. If none is supplied, the AWS account ID is used by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connection<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A map of key-value pairs used as parameters for this connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the connection. Defaults to `JBDC`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Match<wbr>Criterias<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of criteria that can be used in selecting this connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Physical<wbr>Connection<wbr>Requirements<span class="property-indicator"></span>
        <span class="property-type"><a href="#connectionphysicalconnectionrequirements">*Connection<wbr>Physical<wbr>Connection<wbr>Requirements</a></span>
    </dt>
    <dd>{{% md %}}A map of physical connection requirements, such as VPC and SecurityGroup. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Data Catalog in which to create the connection. If none is supplied, the AWS account ID is used by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">connection<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}A map of key-value pairs used as parameters for this connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the connection. Defaults to `JBDC`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">match<wbr>Criterias<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of criteria that can be used in selecting this connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">physical<wbr>Connection<wbr>Requirements<span class="property-indicator"></span>
        <span class="property-type"><a href="#connectionphysicalconnectionrequirements">Connection<wbr>Physical<wbr>Connection<wbr>Requirements?</a></span>
    </dt>
    <dd>{{% md %}}A map of physical connection requirements, such as VPC and SecurityGroup. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">catalog_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Data Catalog in which to create the connection. If none is supplied, the AWS account ID is used by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">connection_<wbr>properties<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A map of key-value pairs used as parameters for this connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">connection_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the connection. Defaults to `JBDC`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">match_<wbr>criterias<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of criteria that can be used in selecting this connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">physical_<wbr>connection_<wbr>requirements<span class="property-indicator"></span>
        <span class="property-type"><a href="#connectionphysicalconnectionrequirements">Dict[Connection<wbr>Physical<wbr>Connection<wbr>Requirements]</a></span>
    </dt>
    <dd>{{% md %}}A map of physical connection requirements, such as VPC and SecurityGroup. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Connection Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#ConnectionState">ConnectionState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#Connection">Connection</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>catalog_id=None<span class="p">, </span>connection_properties=None<span class="p">, </span>connection_type=None<span class="p">, </span>description=None<span class="p">, </span>match_criterias=None<span class="p">, </span>name=None<span class="p">, </span>physical_connection_requirements=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetConnection<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#ConnectionState">ConnectionState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#Connection">Connection</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.Connection.html">Connection</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.ConnectionState.html">ConnectionState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Connection resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Data Catalog in which to create the connection. If none is supplied, the AWS account ID is used by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A map of key-value pairs used as parameters for this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the connection. Defaults to `JBDC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Match<wbr>Criterias<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of criteria that can be used in selecting this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Physical<wbr>Connection<wbr>Requirements<span class="property-indicator"></span>
        <span class="property-type"><a href="#connectionphysicalconnectionrequirements">Connection<wbr>Physical<wbr>Connection<wbr>Requirements<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A map of physical connection requirements, such as VPC and SecurityGroup. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the Data Catalog in which to create the connection. If none is supplied, the AWS account ID is used by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A map of key-value pairs used as parameters for this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the connection. Defaults to `JBDC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Match<wbr>Criterias<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of criteria that can be used in selecting this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Physical<wbr>Connection<wbr>Requirements<span class="property-indicator"></span>
        <span class="property-type"><a href="#connectionphysicalconnectionrequirements">*Connection<wbr>Physical<wbr>Connection<wbr>Requirements</a></span>
    </dt>
    <dd>{{% md %}}A map of physical connection requirements, such as VPC and SecurityGroup. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Data Catalog in which to create the connection. If none is supplied, the AWS account ID is used by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A map of key-value pairs used as parameters for this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the connection. Defaults to `JBDC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">match<wbr>Criterias<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of criteria that can be used in selecting this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">physical<wbr>Connection<wbr>Requirements<span class="property-indicator"></span>
        <span class="property-type"><a href="#connectionphysicalconnectionrequirements">Connection<wbr>Physical<wbr>Connection<wbr>Requirements?</a></span>
    </dt>
    <dd>{{% md %}}A map of physical connection requirements, such as VPC and SecurityGroup. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">catalog_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Data Catalog in which to create the connection. If none is supplied, the AWS account ID is used by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection_<wbr>properties<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A map of key-value pairs used as parameters for this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the connection. Defaults to `JBDC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">match_<wbr>criterias<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of criteria that can be used in selecting this connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">physical_<wbr>connection_<wbr>requirements<span class="property-indicator"></span>
        <span class="property-type"><a href="#connectionphysicalconnectionrequirements">Dict[Connection<wbr>Physical<wbr>Connection<wbr>Requirements]</a></span>
    </dt>
    <dd>{{% md %}}A map of physical connection requirements, such as VPC and SecurityGroup. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### ConnectionPhysicalConnectionRequirements
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ConnectionPhysicalConnectionRequirements">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ConnectionPhysicalConnectionRequirements">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#ConnectionPhysicalConnectionRequirementsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#ConnectionPhysicalConnectionRequirementsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.ConnectionPhysicalConnectionRequirementsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.ConnectionPhysicalConnectionRequirements.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The availability zone of the connection. This field is redundant and implied by `subnet_id`, but is currently an api requirement.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Id<wbr>Lists<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The security group ID list used by the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The subnet ID used by the connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The availability zone of the connection. This field is redundant and implied by `subnet_id`, but is currently an api requirement.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Id<wbr>Lists<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The security group ID list used by the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The subnet ID used by the connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The availability zone of the connection. This field is redundant and implied by `subnet_id`, but is currently an api requirement.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Id<wbr>Lists<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The security group ID list used by the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The subnet ID used by the connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The availability zone of the connection. This field is redundant and implied by `subnet_id`, but is currently an api requirement.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Id<wbr>Lists<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The security group ID list used by the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The subnet ID used by the connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








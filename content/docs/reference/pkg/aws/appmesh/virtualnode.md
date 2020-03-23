
---
title: "VirtualNode"
block_external_search_index: true
---

Provides an AWS App Mesh virtual node resource.

## Breaking Changes

Because of backward incompatible API changes (read [here](https://github.com/awslabs/aws-app-mesh-examples/issues/92)), `aws.appmesh.VirtualNode` resource definitions created with provider versions earlier than v2.3.0 will need to be modified:

* Rename the `service_name` attribute of the `dns` object to `hostname`.

* Replace the `backends` attribute of the `spec` object with one or more `backend` configuration blocks,
setting `virtual_service_name` to the name of the service.

The state associated with existing resources will automatically be migrated.

## Example Usage

### Basic

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const serviceb1 = new aws.appmesh.VirtualNode("serviceb1", {
    meshName: aws_appmesh_mesh_simple.id,
    spec: {
        backends: [{
            virtualService: {
                virtualServiceName: "servicea.simpleapp.local",
            },
        }],
        listener: {
            portMapping: {
                port: 8080,
                protocol: "http",
            },
        },
        serviceDiscovery: {
            dns: {
                hostname: "serviceb.simpleapp.local",
            },
        },
    },
});
```

### AWS Cloud Map Service Discovery

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.servicediscovery.HttpNamespace("example", {});
const serviceb1 = new aws.appmesh.VirtualNode("serviceb1", {
    meshName: aws_appmesh_mesh_simple.id,
    spec: {
        backends: [{
            virtualService: {
                virtualServiceName: "servicea.simpleapp.local",
            },
        }],
        listener: {
            portMapping: {
                port: 8080,
                protocol: "http",
            },
        },
        serviceDiscovery: {
            awsCloudMap: {
                attributes: {
                    stack: "blue",
                },
                namespaceName: example.name,
                serviceName: "serviceb1",
            },
        },
    },
});
```

### Listener Health Check

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const serviceb1 = new aws.appmesh.VirtualNode("serviceb1", {
    meshName: aws_appmesh_mesh_simple.id,
    spec: {
        backends: [{
            virtualService: {
                virtualServiceName: "servicea.simpleapp.local",
            },
        }],
        listener: {
            healthCheck: {
                healthyThreshold: 2,
                intervalMillis: 5000,
                path: "/ping",
                protocol: "http",
                timeoutMillis: 2000,
                unhealthyThreshold: 2,
            },
            portMapping: {
                port: 8080,
                protocol: "http",
            },
        },
        serviceDiscovery: {
            dns: {
                hostname: "serviceb.simpleapp.local",
            },
        },
    },
});
```

### Logging

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const serviceb1 = new aws.appmesh.VirtualNode("serviceb1", {
    meshName: aws_appmesh_mesh_simple.id,
    spec: {
        backends: [{
            virtualService: {
                virtualServiceName: "servicea.simpleapp.local",
            },
        }],
        listener: {
            portMapping: {
                port: 8080,
                protocol: "http",
            },
        },
        logging: {
            accessLog: {
                file: {
                    path: "/dev/stdout",
                },
            },
        },
        serviceDiscovery: {
            dns: {
                hostname: "serviceb.simpleapp.local",
            },
        },
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/appmesh_virtual_node.html.markdown.



## Create a VirtualNode Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appmesh/#VirtualNode">VirtualNode</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appmesh/#VirtualNodeArgs">VirtualNodeArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">VirtualNode</span><span class="p">(resource_name, opts=None, </span>mesh_name=None<span class="p">, </span>name=None<span class="p">, </span>spec=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewVirtualNode<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeArgs">VirtualNodeArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNode">VirtualNode</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNode.html">VirtualNode</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeArgs.html">VirtualNodeArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual node.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespec">Virtual<wbr>Node<wbr>Spec<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The virtual node specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual node.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespec">Virtual<wbr>Node<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The virtual node specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual node.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespec">Virtual<wbr>Node<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The virtual node specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">mesh_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual node.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespec">Dict[Virtual<wbr>Node<wbr>Spec]</a></span>
    </dt>
    <dd>{{% md %}}The virtual node specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## VirtualNode Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespec">Virtual<wbr>Node<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The virtual node specification to apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespec">Virtual<wbr>Node<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The virtual node specification to apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespec">Virtual<wbr>Node<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The virtual node specification to apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last_<wbr>updated_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">mesh_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual node.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespec">Dict[Virtual<wbr>Node<wbr>Spec]</a></span>
    </dt>
    <dd>{{% md %}}The virtual node specification to apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing VirtualNode Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appmesh/#VirtualNodeState">VirtualNodeState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appmesh/#VirtualNode">VirtualNode</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>created_date=None<span class="p">, </span>last_updated_date=None<span class="p">, </span>mesh_name=None<span class="p">, </span>name=None<span class="p">, </span>spec=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetVirtualNode<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeState">VirtualNodeState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNode">VirtualNode</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNode.html">VirtualNode</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeState.html">VirtualNodeState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing VirtualNode resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The ARN of the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespec">Virtual<wbr>Node<wbr>Spec<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The virtual node specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespec">*Virtual<wbr>Node<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The virtual node specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespec">Virtual<wbr>Node<wbr>Spec?</a></span>
    </dt>
    <dd>{{% md %}}The virtual node specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last_<wbr>updated_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mesh_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespec">Dict[Virtual<wbr>Node<wbr>Spec]</a></span>
    </dt>
    <dd>{{% md %}}The virtual node specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### VirtualNodeSpec
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VirtualNodeSpec">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VirtualNodeSpec">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpec.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Backends<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecbackend">List&lt;Virtual<wbr>Node<wbr>Spec<wbr>Backend<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The backends to which the virtual node is expected to send outbound traffic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Listener<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclistener">Virtual<wbr>Node<wbr>Spec<wbr>Listener<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The listeners from which the virtual node is expected to receive inbound traffic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclogging">Virtual<wbr>Node<wbr>Spec<wbr>Logging<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The inbound and outbound access logging information for the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Discovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecservicediscovery">Virtual<wbr>Node<wbr>Spec<wbr>Service<wbr>Discovery<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The service discovery information for the virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Backends<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecbackend">[]Virtual<wbr>Node<wbr>Spec<wbr>Backend</a></span>
    </dt>
    <dd>{{% md %}}The backends to which the virtual node is expected to send outbound traffic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Listener<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclistener">*Virtual<wbr>Node<wbr>Spec<wbr>Listener</a></span>
    </dt>
    <dd>{{% md %}}The listeners from which the virtual node is expected to receive inbound traffic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclogging">*Virtual<wbr>Node<wbr>Spec<wbr>Logging</a></span>
    </dt>
    <dd>{{% md %}}The inbound and outbound access logging information for the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Discovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecservicediscovery">*Virtual<wbr>Node<wbr>Spec<wbr>Service<wbr>Discovery</a></span>
    </dt>
    <dd>{{% md %}}The service discovery information for the virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">backends<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecbackend">Virtual<wbr>Node<wbr>Spec<wbr>Backend[]?</a></span>
    </dt>
    <dd>{{% md %}}The backends to which the virtual node is expected to send outbound traffic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">listener<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclistener">Virtual<wbr>Node<wbr>Spec<wbr>Listener?</a></span>
    </dt>
    <dd>{{% md %}}The listeners from which the virtual node is expected to receive inbound traffic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclogging">Virtual<wbr>Node<wbr>Spec<wbr>Logging?</a></span>
    </dt>
    <dd>{{% md %}}The inbound and outbound access logging information for the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service<wbr>Discovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecservicediscovery">Virtual<wbr>Node<wbr>Spec<wbr>Service<wbr>Discovery?</a></span>
    </dt>
    <dd>{{% md %}}The service discovery information for the virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">backends<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecbackend">List[Virtual<wbr>Node<wbr>Spec<wbr>Backend]</a></span>
    </dt>
    <dd>{{% md %}}The backends to which the virtual node is expected to send outbound traffic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">listener<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclistener">Dict[Virtual<wbr>Node<wbr>Spec<wbr>Listener]</a></span>
    </dt>
    <dd>{{% md %}}The listeners from which the virtual node is expected to receive inbound traffic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclogging">Dict[Virtual<wbr>Node<wbr>Spec<wbr>Logging]</a></span>
    </dt>
    <dd>{{% md %}}The inbound and outbound access logging information for the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service<wbr>Discovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecservicediscovery">Dict[Virtual<wbr>Node<wbr>Spec<wbr>Service<wbr>Discovery]</a></span>
    </dt>
    <dd>{{% md %}}The service discovery information for the virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### VirtualNodeSpecBackend
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VirtualNodeSpecBackend">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VirtualNodeSpecBackend">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecBackendArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecBackendOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecBackendArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecBackend.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Virtual<wbr>Service<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecbackendvirtualservice">Virtual<wbr>Node<wbr>Spec<wbr>Backend<wbr>Virtual<wbr>Service<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Specifies a virtual service to use as a backend for a virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Virtual<wbr>Service<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecbackendvirtualservice">*Virtual<wbr>Node<wbr>Spec<wbr>Backend<wbr>Virtual<wbr>Service</a></span>
    </dt>
    <dd>{{% md %}}Specifies a virtual service to use as a backend for a virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">virtual<wbr>Service<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecbackendvirtualservice">Virtual<wbr>Node<wbr>Spec<wbr>Backend<wbr>Virtual<wbr>Service?</a></span>
    </dt>
    <dd>{{% md %}}Specifies a virtual service to use as a backend for a virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">virtual<wbr>Service<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecbackendvirtualservice">Dict[Virtual<wbr>Node<wbr>Spec<wbr>Backend<wbr>Virtual<wbr>Service]</a></span>
    </dt>
    <dd>{{% md %}}Specifies a virtual service to use as a backend for a virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### VirtualNodeSpecBackendVirtualService
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VirtualNodeSpecBackendVirtualService">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VirtualNodeSpecBackendVirtualService">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecBackendVirtualServiceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecBackendVirtualServiceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecBackendVirtualServiceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecBackendVirtualService.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Virtual<wbr>Service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the virtual service that is acting as a virtual node backend.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Virtual<wbr>Service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the virtual service that is acting as a virtual node backend.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">virtual<wbr>Service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the virtual service that is acting as a virtual node backend.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">virtual<wbr>Service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the virtual service that is acting as a virtual node backend.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### VirtualNodeSpecListener
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VirtualNodeSpecListener">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VirtualNodeSpecListener">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecListenerArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecListenerOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecListenerArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecListener.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclistenerhealthcheck">Virtual<wbr>Node<wbr>Spec<wbr>Listener<wbr>Health<wbr>Check<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The health check information for the listener.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Port<wbr>Mapping<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclistenerportmapping">Virtual<wbr>Node<wbr>Spec<wbr>Listener<wbr>Port<wbr>Mapping<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The port mapping information for the listener.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclistenerhealthcheck">*Virtual<wbr>Node<wbr>Spec<wbr>Listener<wbr>Health<wbr>Check</a></span>
    </dt>
    <dd>{{% md %}}The health check information for the listener.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Port<wbr>Mapping<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclistenerportmapping">Virtual<wbr>Node<wbr>Spec<wbr>Listener<wbr>Port<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}The port mapping information for the listener.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclistenerhealthcheck">Virtual<wbr>Node<wbr>Spec<wbr>Listener<wbr>Health<wbr>Check?</a></span>
    </dt>
    <dd>{{% md %}}The health check information for the listener.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">port<wbr>Mapping<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclistenerportmapping">Virtual<wbr>Node<wbr>Spec<wbr>Listener<wbr>Port<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}The port mapping information for the listener.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">health_<wbr>check<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclistenerhealthcheck">Dict[Virtual<wbr>Node<wbr>Spec<wbr>Listener<wbr>Health<wbr>Check]</a></span>
    </dt>
    <dd>{{% md %}}The health check information for the listener.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">port<wbr>Mapping<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespeclistenerportmapping">Dict[Virtual<wbr>Node<wbr>Spec<wbr>Listener<wbr>Port<wbr>Mapping]</a></span>
    </dt>
    <dd>{{% md %}}The port mapping information for the listener.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### VirtualNodeSpecListenerHealthCheck
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VirtualNodeSpecListenerHealthCheck">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VirtualNodeSpecListenerHealthCheck">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecListenerHealthCheckArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecListenerHealthCheckOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecListenerHealthCheckArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecListenerHealthCheck.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Healthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of consecutive successful health checks that must occur before declaring listener healthy.
* `interval_millis`- (Required) The time period in milliseconds between each health check execution.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Interval<wbr>Millis<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination path for the health check request. This is only required if the specified protocol is `http`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The destination port for the health check request. This port must match the port defined in the `port_mapping` for the listener.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol for the health check request. Valid values are `http` and `tcp`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Timeout<wbr>Millis<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The amount of time to wait when receiving a response from the health check, in milliseconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Unhealthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of consecutive failed health checks that must occur before declaring a virtual node unhealthy.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Healthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of consecutive successful health checks that must occur before declaring listener healthy.
* `interval_millis`- (Required) The time period in milliseconds between each health check execution.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Interval<wbr>Millis<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Path<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The destination path for the health check request. This is only required if the specified protocol is `http`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The destination port for the health check request. This port must match the port defined in the `port_mapping` for the listener.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol for the health check request. Valid values are `http` and `tcp`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Timeout<wbr>Millis<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The amount of time to wait when receiving a response from the health check, in milliseconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Unhealthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of consecutive failed health checks that must occur before declaring a virtual node unhealthy.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">healthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of consecutive successful health checks that must occur before declaring listener healthy.
* `interval_millis`- (Required) The time period in milliseconds between each health check execution.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">interval<wbr>Millis<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination path for the health check request. This is only required if the specified protocol is `http`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The destination port for the health check request. This port must match the port defined in the `port_mapping` for the listener.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol for the health check request. Valid values are `http` and `tcp`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">timeout<wbr>Millis<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The amount of time to wait when receiving a response from the health check, in milliseconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">unhealthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of consecutive failed health checks that must occur before declaring a virtual node unhealthy.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">healthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of consecutive successful health checks that must occur before declaring listener healthy.
* `interval_millis`- (Required) The time period in milliseconds between each health check execution.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">interval<wbr>Millis<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The destination path for the health check request. This is only required if the specified protocol is `http`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The destination port for the health check request. This port must match the port defined in the `port_mapping` for the listener.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol for the health check request. Valid values are `http` and `tcp`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">timeout<wbr>Millis<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of time to wait when receiving a response from the health check, in milliseconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">unhealthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of consecutive failed health checks that must occur before declaring a virtual node unhealthy.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### VirtualNodeSpecListenerPortMapping
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VirtualNodeSpecListenerPortMapping">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VirtualNodeSpecListenerPortMapping">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecListenerPortMappingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecListenerPortMappingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecListenerPortMappingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecListenerPortMapping.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The destination port for the health check request. This port must match the port defined in the `port_mapping` for the listener.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol for the health check request. Valid values are `http` and `tcp`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The destination port for the health check request. This port must match the port defined in the `port_mapping` for the listener.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol for the health check request. Valid values are `http` and `tcp`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The destination port for the health check request. This port must match the port defined in the `port_mapping` for the listener.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol for the health check request. Valid values are `http` and `tcp`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The destination port for the health check request. This port must match the port defined in the `port_mapping` for the listener.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol for the health check request. Valid values are `http` and `tcp`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### VirtualNodeSpecLogging
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VirtualNodeSpecLogging">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VirtualNodeSpecLogging">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecLoggingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecLoggingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecLoggingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecLogging.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Access<wbr>Log<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecloggingaccesslog">Virtual<wbr>Node<wbr>Spec<wbr>Logging<wbr>Access<wbr>Log<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The access log configuration for a virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Access<wbr>Log<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecloggingaccesslog">*Virtual<wbr>Node<wbr>Spec<wbr>Logging<wbr>Access<wbr>Log</a></span>
    </dt>
    <dd>{{% md %}}The access log configuration for a virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access<wbr>Log<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecloggingaccesslog">Virtual<wbr>Node<wbr>Spec<wbr>Logging<wbr>Access<wbr>Log?</a></span>
    </dt>
    <dd>{{% md %}}The access log configuration for a virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access<wbr>Log<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecloggingaccesslog">Dict[Virtual<wbr>Node<wbr>Spec<wbr>Logging<wbr>Access<wbr>Log]</a></span>
    </dt>
    <dd>{{% md %}}The access log configuration for a virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### VirtualNodeSpecLoggingAccessLog
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VirtualNodeSpecLoggingAccessLog">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VirtualNodeSpecLoggingAccessLog">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecLoggingAccessLogArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecLoggingAccessLogOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecLoggingAccessLogArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecLoggingAccessLog.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">File<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecloggingaccesslogfile">Virtual<wbr>Node<wbr>Spec<wbr>Logging<wbr>Access<wbr>Log<wbr>File<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The file object to send virtual node access logs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">File<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecloggingaccesslogfile">*Virtual<wbr>Node<wbr>Spec<wbr>Logging<wbr>Access<wbr>Log<wbr>File</a></span>
    </dt>
    <dd>{{% md %}}The file object to send virtual node access logs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">file<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecloggingaccesslogfile">Virtual<wbr>Node<wbr>Spec<wbr>Logging<wbr>Access<wbr>Log<wbr>File?</a></span>
    </dt>
    <dd>{{% md %}}The file object to send virtual node access logs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">file<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecloggingaccesslogfile">Dict[Virtual<wbr>Node<wbr>Spec<wbr>Logging<wbr>Access<wbr>Log<wbr>File]</a></span>
    </dt>
    <dd>{{% md %}}The file object to send virtual node access logs to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### VirtualNodeSpecLoggingAccessLogFile
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VirtualNodeSpecLoggingAccessLogFile">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VirtualNodeSpecLoggingAccessLogFile">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecLoggingAccessLogFileArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecLoggingAccessLogFileOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecLoggingAccessLogFileArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecLoggingAccessLogFile.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The destination path for the health check request. This is only required if the specified protocol is `http`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The destination path for the health check request. This is only required if the specified protocol is `http`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The destination path for the health check request. This is only required if the specified protocol is `http`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The destination path for the health check request. This is only required if the specified protocol is `http`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### VirtualNodeSpecServiceDiscovery
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VirtualNodeSpecServiceDiscovery">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VirtualNodeSpecServiceDiscovery">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecServiceDiscoveryArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecServiceDiscoveryOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecServiceDiscoveryArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecServiceDiscovery.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Aws<wbr>Cloud<wbr>Map<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecservicediscoveryawscloudmap">Virtual<wbr>Node<wbr>Spec<wbr>Service<wbr>Discovery<wbr>Aws<wbr>Cloud<wbr>Map<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Specifies any AWS Cloud Map information for the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dns<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecservicediscoverydns">Virtual<wbr>Node<wbr>Spec<wbr>Service<wbr>Discovery<wbr>Dns<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Specifies the DNS service name for the virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Aws<wbr>Cloud<wbr>Map<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecservicediscoveryawscloudmap">*Virtual<wbr>Node<wbr>Spec<wbr>Service<wbr>Discovery<wbr>Aws<wbr>Cloud<wbr>Map</a></span>
    </dt>
    <dd>{{% md %}}Specifies any AWS Cloud Map information for the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dns<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecservicediscoverydns">*Virtual<wbr>Node<wbr>Spec<wbr>Service<wbr>Discovery<wbr>Dns</a></span>
    </dt>
    <dd>{{% md %}}Specifies the DNS service name for the virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">aws<wbr>Cloud<wbr>Map<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecservicediscoveryawscloudmap">Virtual<wbr>Node<wbr>Spec<wbr>Service<wbr>Discovery<wbr>Aws<wbr>Cloud<wbr>Map?</a></span>
    </dt>
    <dd>{{% md %}}Specifies any AWS Cloud Map information for the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dns<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecservicediscoverydns">Virtual<wbr>Node<wbr>Spec<wbr>Service<wbr>Discovery<wbr>Dns?</a></span>
    </dt>
    <dd>{{% md %}}Specifies the DNS service name for the virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">aws<wbr>Cloud<wbr>Map<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecservicediscoveryawscloudmap">Dict[Virtual<wbr>Node<wbr>Spec<wbr>Service<wbr>Discovery<wbr>Aws<wbr>Cloud<wbr>Map]</a></span>
    </dt>
    <dd>{{% md %}}Specifies any AWS Cloud Map information for the virtual node.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dns<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualnodespecservicediscoverydns">Dict[Virtual<wbr>Node<wbr>Spec<wbr>Service<wbr>Discovery<wbr>Dns]</a></span>
    </dt>
    <dd>{{% md %}}Specifies the DNS service name for the virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### VirtualNodeSpecServiceDiscoveryAwsCloudMap
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VirtualNodeSpecServiceDiscoveryAwsCloudMap">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VirtualNodeSpecServiceDiscoveryAwsCloudMap">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecServiceDiscoveryAwsCloudMapArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecServiceDiscoveryAwsCloudMapOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecServiceDiscoveryAwsCloudMapArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecServiceDiscoveryAwsCloudMap.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Attributes<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A string map that contains attributes with values that you can use to filter instances by any custom attribute that you specified when you registered the instance. Only instances that match all of the specified key/value pairs will be returned.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Namespace<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Cloud Map namespace to use.
Use the [`aws.servicediscovery.HttpNamespace`](https://www.terraform.io/docs/providers/aws/r/service_discovery_http_namespace.html) resource to configure a Cloud Map namespace.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Cloud Map service to use. Use the [`aws.servicediscovery.Service`](https://www.terraform.io/docs/providers/aws/r/service_discovery_service.html) resource to configure a Cloud Map service.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Attributes<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A string map that contains attributes with values that you can use to filter instances by any custom attribute that you specified when you registered the instance. Only instances that match all of the specified key/value pairs will be returned.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Namespace<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Cloud Map namespace to use.
Use the [`aws.servicediscovery.HttpNamespace`](https://www.terraform.io/docs/providers/aws/r/service_discovery_http_namespace.html) resource to configure a Cloud Map namespace.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Cloud Map service to use. Use the [`aws.servicediscovery.Service`](https://www.terraform.io/docs/providers/aws/r/service_discovery_service.html) resource to configure a Cloud Map service.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">attributes<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A string map that contains attributes with values that you can use to filter instances by any custom attribute that you specified when you registered the instance. Only instances that match all of the specified key/value pairs will be returned.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">namespace<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Cloud Map namespace to use.
Use the [`aws.servicediscovery.HttpNamespace`](https://www.terraform.io/docs/providers/aws/r/service_discovery_http_namespace.html) resource to configure a Cloud Map namespace.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Cloud Map service to use. Use the [`aws.servicediscovery.Service`](https://www.terraform.io/docs/providers/aws/r/service_discovery_service.html) resource to configure a Cloud Map service.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">attributes<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A string map that contains attributes with values that you can use to filter instances by any custom attribute that you specified when you registered the instance. Only instances that match all of the specified key/value pairs will be returned.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">namespace<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Cloud Map namespace to use.
Use the [`aws.servicediscovery.HttpNamespace`](https://www.terraform.io/docs/providers/aws/r/service_discovery_http_namespace.html) resource to configure a Cloud Map namespace.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Cloud Map service to use. Use the [`aws.servicediscovery.Service`](https://www.terraform.io/docs/providers/aws/r/service_discovery_service.html) resource to configure a Cloud Map service.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### VirtualNodeSpecServiceDiscoveryDns
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VirtualNodeSpecServiceDiscoveryDns">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VirtualNodeSpecServiceDiscoveryDns">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecServiceDiscoveryDnsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualNodeSpecServiceDiscoveryDnsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecServiceDiscoveryDnsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualNodeSpecServiceDiscoveryDns.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Hostname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS host name for your virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Hostname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS host name for your virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">hostname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS host name for your virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">hostname<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS host name for your virtual node.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








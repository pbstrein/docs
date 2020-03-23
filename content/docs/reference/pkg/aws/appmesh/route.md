
---
title: "Route"
block_external_search_index: true
---

Provides an AWS App Mesh route resource.

## Example Usage

### HTTP Routing

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const serviceb = new aws.appmesh.Route("serviceb", {
    meshName: aws_appmesh_mesh_simple.id,
    spec: {
        httpRoute: {
            action: {
                weightedTargets: [
                    {
                        virtualNode: aws_appmesh_virtual_node_serviceb1.name,
                        weight: 90,
                    },
                    {
                        virtualNode: aws_appmesh_virtual_node_serviceb2.name,
                        weight: 10,
                    },
                ],
            },
            match: {
                prefix: "/",
            },
        },
    },
    virtualRouterName: aws_appmesh_virtual_router_serviceb.name,
});
```

### HTTP Header Routing

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const serviceb = new aws.appmesh.Route("serviceb", {
    meshName: aws_appmesh_mesh_simple.id,
    spec: {
        httpRoute: {
            action: {
                weightedTargets: [{
                    virtualNode: aws_appmesh_virtual_node_serviceb.name,
                    weight: 100,
                }],
            },
            match: {
                headers: [{
                    match: {
                        prefix: "123",
                    },
                    name: "clientRequestId",
                }],
                method: "POST",
                prefix: "/",
                scheme: "https",
            },
        },
    },
    virtualRouterName: aws_appmesh_virtual_router_serviceb.name,
});
```

### TCP Routing

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const serviceb = new aws.appmesh.Route("serviceb", {
    meshName: aws_appmesh_mesh_simple.id,
    spec: {
        tcpRoute: {
            action: {
                weightedTargets: [{
                    virtualNode: aws_appmesh_virtual_node_serviceb1.name,
                    weight: 100,
                }],
            },
        },
    },
    virtualRouterName: aws_appmesh_virtual_router_serviceb.name,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/appmesh_route.html.markdown.



## Create a Route Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appmesh/#Route">Route</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appmesh/#RouteArgs">RouteArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Route</span><span class="p">(resource_name, opts=None, </span>mesh_name=None<span class="p">, </span>name=None<span class="p">, </span>spec=None<span class="p">, </span>tags=None<span class="p">, </span>virtual_router_name=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewRoute<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteArgs">RouteArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#Route">Route</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.Route.html">Route</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteArgs.html">RouteArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
    <dd>{{% md %}}The name of the service mesh in which to create the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespec">Route<wbr>Spec<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The route specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Virtual<wbr>Router<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the virtual router in which to create the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespec">Route<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The route specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Virtual<wbr>Router<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the virtual router in which to create the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespec">Route<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The route specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">virtual<wbr>Router<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the virtual router in which to create the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">mesh_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespec">Dict[Route<wbr>Spec]</a></span>
    </dt>
    <dd>{{% md %}}The route specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">virtual_<wbr>router_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the virtual router in which to create the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Route Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The creation date of the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The last update date of the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespec">Route<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The route specification to apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Virtual<wbr>Router<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the virtual router in which to create the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The creation date of the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The last update date of the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespec">Route<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The route specification to apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Virtual<wbr>Router<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the virtual router in which to create the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The creation date of the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The last update date of the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespec">Route<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The route specification to apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">virtual<wbr>Router<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the virtual router in which to create the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The creation date of the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last_<wbr>updated_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The last update date of the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">mesh_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the route.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespec">Dict[Route<wbr>Spec]</a></span>
    </dt>
    <dd>{{% md %}}The route specification to apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">virtual_<wbr>router_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the virtual router in which to create the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Route Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appmesh/#RouteState">RouteState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appmesh/#Route">Route</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>created_date=None<span class="p">, </span>last_updated_date=None<span class="p">, </span>mesh_name=None<span class="p">, </span>name=None<span class="p">, </span>spec=None<span class="p">, </span>tags=None<span class="p">, </span>virtual_router_name=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetRoute<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteState">RouteState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#Route">Route</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.Route.html">Route</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteState.html">RouteState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Route resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The ARN of the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The creation date of the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The last update date of the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespec">Route<wbr>Spec<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The route specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtual<wbr>Router<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the virtual router in which to create the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The creation date of the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The last update date of the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespec">*Route<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The route specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtual<wbr>Router<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the virtual router in which to create the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The creation date of the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The last update date of the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespec">Route<wbr>Spec?</a></span>
    </dt>
    <dd>{{% md %}}The route specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtual<wbr>Router<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the virtual router in which to create the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The creation date of the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last_<wbr>updated_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The last update date of the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mesh_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespec">Dict[Route<wbr>Spec]</a></span>
    </dt>
    <dd>{{% md %}}The route specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtual_<wbr>router_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the virtual router in which to create the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### RouteSpec
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#RouteSpec">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#RouteSpec">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpec.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Http<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproute">Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The HTTP routing information for the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Priority<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The priority for the route, between `0` and `1000`.
Routes are matched based on the specified value, where `0` is the highest priority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tcp<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespectcproute">Route<wbr>Spec<wbr>Tcp<wbr>Route<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The TCP routing information for the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Http<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproute">*Route<wbr>Spec<wbr>Http<wbr>Route</a></span>
    </dt>
    <dd>{{% md %}}The HTTP routing information for the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Priority<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The priority for the route, between `0` and `1000`.
Routes are matched based on the specified value, where `0` is the highest priority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tcp<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespectcproute">*Route<wbr>Spec<wbr>Tcp<wbr>Route</a></span>
    </dt>
    <dd>{{% md %}}The TCP routing information for the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">http<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproute">Route<wbr>Spec<wbr>Http<wbr>Route?</a></span>
    </dt>
    <dd>{{% md %}}The HTTP routing information for the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">priority<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The priority for the route, between `0` and `1000`.
Routes are matched based on the specified value, where `0` is the highest priority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tcp<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespectcproute">Route<wbr>Spec<wbr>Tcp<wbr>Route?</a></span>
    </dt>
    <dd>{{% md %}}The TCP routing information for the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">http<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproute">Dict[Route<wbr>Spec<wbr>Http<wbr>Route]</a></span>
    </dt>
    <dd>{{% md %}}The HTTP routing information for the route.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">priority<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The priority for the route, between `0` and `1000`.
Routes are matched based on the specified value, where `0` is the highest priority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tcp<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespectcproute">Dict[Route<wbr>Spec<wbr>Tcp<wbr>Route]</a></span>
    </dt>
    <dd>{{% md %}}The TCP routing information for the route.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### RouteSpecHttpRoute
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#RouteSpecHttpRoute">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#RouteSpecHttpRoute">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecHttpRouteArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecHttpRouteOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecHttpRouteArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecHttpRoute.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttprouteaction">Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Action<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The action to take if a match is determined.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Match<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematch">Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The method and value to match the header value sent with a request. Specify one match method.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttprouteaction">Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}The action to take if a match is determined.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Match<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematch">Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match</a></span>
    </dt>
    <dd>{{% md %}}The method and value to match the header value sent with a request. Specify one match method.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">action<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttprouteaction">Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}The action to take if a match is determined.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">match<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematch">Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match</a></span>
    </dt>
    <dd>{{% md %}}The method and value to match the header value sent with a request. Specify one match method.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">action<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttprouteaction">Dict[Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}The action to take if a match is determined.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">match<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematch">Dict[Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match]</a></span>
    </dt>
    <dd>{{% md %}}The method and value to match the header value sent with a request. Specify one match method.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### RouteSpecHttpRouteAction
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#RouteSpecHttpRouteAction">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#RouteSpecHttpRouteAction">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecHttpRouteActionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecHttpRouteActionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecHttpRouteActionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecHttpRouteAction.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Weighted<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttprouteactionweightedtarget">List&lt;Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Action<wbr>Weighted<wbr>Target<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}The targets that traffic is routed to when a request matches the route.
You can specify one or more targets and their relative weights with which to distribute traffic.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Weighted<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttprouteactionweightedtarget">[]Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Action<wbr>Weighted<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}The targets that traffic is routed to when a request matches the route.
You can specify one or more targets and their relative weights with which to distribute traffic.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">weighted<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttprouteactionweightedtarget">Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Action<wbr>Weighted<wbr>Target[]</a></span>
    </dt>
    <dd>{{% md %}}The targets that traffic is routed to when a request matches the route.
You can specify one or more targets and their relative weights with which to distribute traffic.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">weighted<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttprouteactionweightedtarget">List[Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Action<wbr>Weighted<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}The targets that traffic is routed to when a request matches the route.
You can specify one or more targets and their relative weights with which to distribute traffic.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### RouteSpecHttpRouteActionWeightedTarget
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#RouteSpecHttpRouteActionWeightedTarget">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#RouteSpecHttpRouteActionWeightedTarget">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecHttpRouteActionWeightedTargetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecHttpRouteActionWeightedTargetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecHttpRouteActionWeightedTargetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecHttpRouteActionWeightedTarget.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Virtual<wbr>Node<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The virtual node to associate with the weighted target.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Weight<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The relative weight of the weighted target. An integer between 0 and 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Virtual<wbr>Node<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The virtual node to associate with the weighted target.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Weight<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The relative weight of the weighted target. An integer between 0 and 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">virtual<wbr>Node<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The virtual node to associate with the weighted target.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">weight<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The relative weight of the weighted target. An integer between 0 and 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">virtual<wbr>Node<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The virtual node to associate with the weighted target.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">weight<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The relative weight of the weighted target. An integer between 0 and 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### RouteSpecHttpRouteMatch
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#RouteSpecHttpRouteMatch">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#RouteSpecHttpRouteMatch">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecHttpRouteMatchArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecHttpRouteMatchOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecHttpRouteMatchArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecHttpRouteMatch.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Headers<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematchheader">List&lt;Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match<wbr>Header<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The client request headers to match on.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The client request header method to match on. Valid values: `GET`, `HEAD`, `POST`, `PUT`, `DELETE`, `CONNECT`, `OPTIONS`, `TRACE`, `PATCH`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must begin with the specified characters.
* `range`- (Optional) The object that specifies the range of numbers that the header value sent by the client must be included in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scheme<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The client request header scheme to match on. Valid values: `http`, `https`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Headers<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematchheader">[]Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match<wbr>Header</a></span>
    </dt>
    <dd>{{% md %}}The client request headers to match on.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Method<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The client request header method to match on. Valid values: `GET`, `HEAD`, `POST`, `PUT`, `DELETE`, `CONNECT`, `OPTIONS`, `TRACE`, `PATCH`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must begin with the specified characters.
* `range`- (Optional) The object that specifies the range of numbers that the header value sent by the client must be included in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scheme<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The client request header scheme to match on. Valid values: `http`, `https`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">headers<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematchheader">Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match<wbr>Header[]?</a></span>
    </dt>
    <dd>{{% md %}}The client request headers to match on.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The client request header method to match on. Valid values: `GET`, `HEAD`, `POST`, `PUT`, `DELETE`, `CONNECT`, `OPTIONS`, `TRACE`, `PATCH`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must begin with the specified characters.
* `range`- (Optional) The object that specifies the range of numbers that the header value sent by the client must be included in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scheme<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The client request header scheme to match on. Valid values: `http`, `https`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">headers<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematchheader">List[Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match<wbr>Header]</a></span>
    </dt>
    <dd>{{% md %}}The client request headers to match on.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The client request header method to match on. Valid values: `GET`, `HEAD`, `POST`, `PUT`, `DELETE`, `CONNECT`, `OPTIONS`, `TRACE`, `PATCH`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must begin with the specified characters.
* `range`- (Optional) The object that specifies the range of numbers that the header value sent by the client must be included in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scheme<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The client request header scheme to match on. Valid values: `http`, `https`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### RouteSpecHttpRouteMatchHeader
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#RouteSpecHttpRouteMatchHeader">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#RouteSpecHttpRouteMatchHeader">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecHttpRouteMatchHeaderArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecHttpRouteMatchHeaderOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecHttpRouteMatchHeaderArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecHttpRouteMatchHeader.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Invert<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If `true`, the match is on the opposite of the `match` method and value. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Match<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematchheadermatch">Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match<wbr>Header<wbr>Match<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The method and value to match the header value sent with a request. Specify one match method.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Invert<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If `true`, the match is on the opposite of the `match` method and value. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Match<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematchheadermatch">*Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match<wbr>Header<wbr>Match</a></span>
    </dt>
    <dd>{{% md %}}The method and value to match the header value sent with a request. Specify one match method.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">invert<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If `true`, the match is on the opposite of the `match` method and value. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">match<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematchheadermatch">Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match<wbr>Header<wbr>Match?</a></span>
    </dt>
    <dd>{{% md %}}The method and value to match the header value sent with a request. Specify one match method.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">invert<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `true`, the match is on the opposite of the `match` method and value. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">match<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematchheadermatch">Dict[Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match<wbr>Header<wbr>Match]</a></span>
    </dt>
    <dd>{{% md %}}The method and value to match the header value sent with a request. Specify one match method.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A name for the HTTP header in the client request that will be matched on.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### RouteSpecHttpRouteMatchHeaderMatch
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#RouteSpecHttpRouteMatchHeaderMatch">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#RouteSpecHttpRouteMatchHeaderMatch">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecHttpRouteMatchHeaderMatchArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecHttpRouteMatchHeaderMatchOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecHttpRouteMatchHeaderMatchArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecHttpRouteMatchHeaderMatch.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Exact<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must match the specified value exactly.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must begin with the specified characters.
* `range`- (Optional) The object that specifies the range of numbers that the header value sent by the client must be included in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematchheadermatchrange">Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match<wbr>Header<wbr>Match<wbr>Range<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Regex<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must include the specified characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Suffix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must end with the specified characters.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Exact<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must match the specified value exactly.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must begin with the specified characters.
* `range`- (Optional) The object that specifies the range of numbers that the header value sent by the client must be included in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematchheadermatchrange">*Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match<wbr>Header<wbr>Match<wbr>Range</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Regex<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must include the specified characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Suffix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must end with the specified characters.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">exact<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must match the specified value exactly.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must begin with the specified characters.
* `range`- (Optional) The object that specifies the range of numbers that the header value sent by the client must be included in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">range<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematchheadermatchrange">Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match<wbr>Header<wbr>Match<wbr>Range?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">regex<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must include the specified characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">suffix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must end with the specified characters.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">exact<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must match the specified value exactly.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must begin with the specified characters.
* `range`- (Optional) The object that specifies the range of numbers that the header value sent by the client must be included in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">range<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespechttproutematchheadermatchrange">Dict[Route<wbr>Spec<wbr>Http<wbr>Route<wbr>Match<wbr>Header<wbr>Match<wbr>Range]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">regex<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must include the specified characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">suffix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The header value sent by the client must end with the specified characters.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### RouteSpecHttpRouteMatchHeaderMatchRange
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#RouteSpecHttpRouteMatchHeaderMatchRange">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#RouteSpecHttpRouteMatchHeaderMatchRange">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecHttpRouteMatchHeaderMatchRangeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecHttpRouteMatchHeaderMatchRangeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecHttpRouteMatchHeaderMatchRangeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecHttpRouteMatchHeaderMatchRange.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">End<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The end of the range.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Start<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The start of the range.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">End<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The end of the range.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Start<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The start of the range.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">end<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The end of the range.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">start<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The start of the range.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">end<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The end of the range.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">start<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The start of the range.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### RouteSpecTcpRoute
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#RouteSpecTcpRoute">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#RouteSpecTcpRoute">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecTcpRouteArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecTcpRouteOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecTcpRouteArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecTcpRoute.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespectcprouteaction">Route<wbr>Spec<wbr>Tcp<wbr>Route<wbr>Action<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The action to take if a match is determined.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespectcprouteaction">Route<wbr>Spec<wbr>Tcp<wbr>Route<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}The action to take if a match is determined.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">action<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespectcprouteaction">Route<wbr>Spec<wbr>Tcp<wbr>Route<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}The action to take if a match is determined.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">action<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespectcprouteaction">Dict[Route<wbr>Spec<wbr>Tcp<wbr>Route<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}The action to take if a match is determined.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### RouteSpecTcpRouteAction
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#RouteSpecTcpRouteAction">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#RouteSpecTcpRouteAction">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecTcpRouteActionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecTcpRouteActionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecTcpRouteActionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecTcpRouteAction.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Weighted<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespectcprouteactionweightedtarget">List&lt;Route<wbr>Spec<wbr>Tcp<wbr>Route<wbr>Action<wbr>Weighted<wbr>Target<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}The targets that traffic is routed to when a request matches the route.
You can specify one or more targets and their relative weights with which to distribute traffic.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Weighted<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespectcprouteactionweightedtarget">[]Route<wbr>Spec<wbr>Tcp<wbr>Route<wbr>Action<wbr>Weighted<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}The targets that traffic is routed to when a request matches the route.
You can specify one or more targets and their relative weights with which to distribute traffic.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">weighted<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespectcprouteactionweightedtarget">Route<wbr>Spec<wbr>Tcp<wbr>Route<wbr>Action<wbr>Weighted<wbr>Target[]</a></span>
    </dt>
    <dd>{{% md %}}The targets that traffic is routed to when a request matches the route.
You can specify one or more targets and their relative weights with which to distribute traffic.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">weighted<wbr>Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#routespectcprouteactionweightedtarget">List[Route<wbr>Spec<wbr>Tcp<wbr>Route<wbr>Action<wbr>Weighted<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}The targets that traffic is routed to when a request matches the route.
You can specify one or more targets and their relative weights with which to distribute traffic.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### RouteSpecTcpRouteActionWeightedTarget
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#RouteSpecTcpRouteActionWeightedTarget">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#RouteSpecTcpRouteActionWeightedTarget">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecTcpRouteActionWeightedTargetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#RouteSpecTcpRouteActionWeightedTargetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecTcpRouteActionWeightedTargetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.RouteSpecTcpRouteActionWeightedTarget.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Virtual<wbr>Node<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The virtual node to associate with the weighted target.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Weight<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The relative weight of the weighted target. An integer between 0 and 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Virtual<wbr>Node<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The virtual node to associate with the weighted target.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Weight<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The relative weight of the weighted target. An integer between 0 and 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">virtual<wbr>Node<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The virtual node to associate with the weighted target.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">weight<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The relative weight of the weighted target. An integer between 0 and 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">virtual<wbr>Node<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The virtual node to associate with the weighted target.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">weight<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The relative weight of the weighted target. An integer between 0 and 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








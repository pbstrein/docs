
---
title: "VirtualRouter"
block_external_search_index: true
---

Provides an AWS App Mesh virtual router resource.

## Breaking Changes

Because of backward incompatible API changes (read [here](https://github.com/awslabs/aws-app-mesh-examples/issues/92) and [here](https://github.com/awslabs/aws-app-mesh-examples/issues/94)), `aws.appmesh.VirtualRouter` resource definitions created with provider versions earlier than v2.3.0 will need to be modified:

* Remove service `service_names` from the `spec` argument.
AWS has created a `aws.appmesh.VirtualService` resource for each of service names.
These resource can be imported using `import`.

* Add a `listener` configuration block to the `spec` argument.

The state associated with existing resources will automatically be migrated.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const serviceb = new aws.appmesh.VirtualRouter("serviceb", {
    meshName: aws_appmesh_mesh_simple.id,
    spec: {
        listener: {
            portMapping: {
                port: 8080,
                protocol: "http",
            },
        },
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/appmesh_virtual_router.html.markdown.



## Create a VirtualRouter Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appmesh/#VirtualRouter">VirtualRouter</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appmesh/#VirtualRouterArgs">VirtualRouterArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">VirtualRouter</span><span class="p">(resource_name, opts=None, </span>mesh_name=None<span class="p">, </span>name=None<span class="p">, </span>spec=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewVirtualRouter<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualRouterArgs">VirtualRouterArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualRouter">VirtualRouter</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualRouter.html">VirtualRouter</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualRouterArgs.html">VirtualRouterArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
    <dd>{{% md %}}The name of the service mesh in which to create the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual router.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspec">Virtual<wbr>Router<wbr>Spec<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The virtual router specification to apply.
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
    <dd>{{% md %}}The name of the service mesh in which to create the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual router.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspec">Virtual<wbr>Router<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The virtual router specification to apply.
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
    <dd>{{% md %}}The name of the service mesh in which to create the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual router.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspec">Virtual<wbr>Router<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The virtual router specification to apply.
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
    <dd>{{% md %}}The name of the service mesh in which to create the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual router.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspec">Dict[Virtual<wbr>Router<wbr>Spec]</a></span>
    </dt>
    <dd>{{% md %}}The virtual router specification to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## VirtualRouter Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspec">Virtual<wbr>Router<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The virtual router specification to apply.
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
    <dd>{{% md %}}The ARN of the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspec">Virtual<wbr>Router<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The virtual router specification to apply.
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
    <dd>{{% md %}}The ARN of the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspec">Virtual<wbr>Router<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The virtual router specification to apply.
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
    <dd>{{% md %}}The ARN of the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last_<wbr>updated_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">mesh_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual router.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspec">Dict[Virtual<wbr>Router<wbr>Spec]</a></span>
    </dt>
    <dd>{{% md %}}The virtual router specification to apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing VirtualRouter Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appmesh/#VirtualRouterState">VirtualRouterState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/appmesh/#VirtualRouter">VirtualRouter</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>created_date=None<span class="p">, </span>last_updated_date=None<span class="p">, </span>mesh_name=None<span class="p">, </span>name=None<span class="p">, </span>spec=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetVirtualRouter<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualRouterState">VirtualRouterState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualRouter">VirtualRouter</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualRouter.html">VirtualRouter</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualRouterState.html">VirtualRouterState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing VirtualRouter resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The ARN of the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspec">Virtual<wbr>Router<wbr>Spec<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The virtual router specification to apply.
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
    <dd>{{% md %}}The ARN of the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspec">*Virtual<wbr>Router<wbr>Spec</a></span>
    </dt>
    <dd>{{% md %}}The virtual router specification to apply.
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
    <dd>{{% md %}}The ARN of the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last<wbr>Updated<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mesh<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspec">Virtual<wbr>Router<wbr>Spec?</a></span>
    </dt>
    <dd>{{% md %}}The virtual router specification to apply.
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
    <dd>{{% md %}}The ARN of the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The creation date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last_<wbr>updated_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The last update date of the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mesh_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the service mesh in which to create the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name to use for the virtual router.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spec<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspec">Dict[Virtual<wbr>Router<wbr>Spec]</a></span>
    </dt>
    <dd>{{% md %}}The virtual router specification to apply.
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

#### VirtualRouterSpec
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VirtualRouterSpec">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VirtualRouterSpec">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualRouterSpecArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualRouterSpecOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualRouterSpecArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualRouterSpec.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Listener<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspeclistener">Virtual<wbr>Router<wbr>Spec<wbr>Listener<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The listeners that the virtual router is expected to receive inbound traffic from.
Currently only one listener is supported per virtual router.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Listener<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspeclistener">Virtual<wbr>Router<wbr>Spec<wbr>Listener</a></span>
    </dt>
    <dd>{{% md %}}The listeners that the virtual router is expected to receive inbound traffic from.
Currently only one listener is supported per virtual router.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">listener<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspeclistener">Virtual<wbr>Router<wbr>Spec<wbr>Listener</a></span>
    </dt>
    <dd>{{% md %}}The listeners that the virtual router is expected to receive inbound traffic from.
Currently only one listener is supported per virtual router.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">listener<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspeclistener">Dict[Virtual<wbr>Router<wbr>Spec<wbr>Listener]</a></span>
    </dt>
    <dd>{{% md %}}The listeners that the virtual router is expected to receive inbound traffic from.
Currently only one listener is supported per virtual router.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### VirtualRouterSpecListener
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VirtualRouterSpecListener">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VirtualRouterSpecListener">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualRouterSpecListenerArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualRouterSpecListenerOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualRouterSpecListenerArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualRouterSpecListener.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Port<wbr>Mapping<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspeclistenerportmapping">Virtual<wbr>Router<wbr>Spec<wbr>Listener<wbr>Port<wbr>Mapping<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The port mapping information for the listener.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Port<wbr>Mapping<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspeclistenerportmapping">Virtual<wbr>Router<wbr>Spec<wbr>Listener<wbr>Port<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}The port mapping information for the listener.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">port<wbr>Mapping<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspeclistenerportmapping">Virtual<wbr>Router<wbr>Spec<wbr>Listener<wbr>Port<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}The port mapping information for the listener.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">port<wbr>Mapping<span class="property-indicator"></span>
        <span class="property-type"><a href="#virtualrouterspeclistenerportmapping">Dict[Virtual<wbr>Router<wbr>Spec<wbr>Listener<wbr>Port<wbr>Mapping]</a></span>
    </dt>
    <dd>{{% md %}}The port mapping information for the listener.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### VirtualRouterSpecListenerPortMapping
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VirtualRouterSpecListenerPortMapping">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VirtualRouterSpecListenerPortMapping">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualRouterSpecListenerPortMappingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/appmesh?tab=doc#VirtualRouterSpecListenerPortMappingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualRouterSpecListenerPortMappingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Appmesh.VirtualRouterSpecListenerPortMapping.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port used for the port mapping.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol used for the port mapping. Valid values are `http` and `tcp`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port used for the port mapping.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol used for the port mapping. Valid values are `http` and `tcp`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The port used for the port mapping.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol used for the port mapping. Valid values are `http` and `tcp`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port used for the port mapping.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol used for the port mapping. Valid values are `http` and `tcp`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








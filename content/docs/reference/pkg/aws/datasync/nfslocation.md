
---
title: "NfsLocation"
block_external_search_index: true
---

Manages an NFS Location within AWS DataSync.

> **NOTE:** The DataSync Agents must be available before creating this resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.datasync.NfsLocation("example", {
    onPremConfig: {
        agentArns: [aws_datasync_agent_example.arn],
    },
    serverHostname: "nfs.example.com",
    subdirectory: "/exported/path",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/datasync_location_nfs.html.markdown.



## Create a NfsLocation Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/datasync/#NfsLocation">NfsLocation</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/datasync/#NfsLocationArgs">NfsLocationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">NfsLocation</span><span class="p">(resource_name, opts=None, </span>on_prem_config=None<span class="p">, </span>server_hostname=None<span class="p">, </span>subdirectory=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewNfsLocation<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/datasync?tab=doc#NfsLocationArgs">NfsLocationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/datasync?tab=doc#NfsLocation">NfsLocation</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Datasync.NfsLocation.html">NfsLocation</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Datasync.NfsLocationArgs.html">NfsLocationArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">On<wbr>Prem<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfslocationonpremconfig">Nfs<wbr>Location<wbr>On<wbr>Prem<wbr>Config<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing information for connecting to the NFS File System.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Server<wbr>Hostname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the IP address or DNS name of the NFS server. The DataSync Agent(s) use this to mount the NFS server.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subdirectory<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Should be exported by the NFS server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">On<wbr>Prem<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfslocationonpremconfig">Nfs<wbr>Location<wbr>On<wbr>Prem<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing information for connecting to the NFS File System.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Server<wbr>Hostname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the IP address or DNS name of the NFS server. The DataSync Agent(s) use this to mount the NFS server.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subdirectory<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Should be exported by the NFS server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">on<wbr>Prem<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfslocationonpremconfig">Nfs<wbr>Location<wbr>On<wbr>Prem<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing information for connecting to the NFS File System.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">server<wbr>Hostname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the IP address or DNS name of the NFS server. The DataSync Agent(s) use this to mount the NFS server.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subdirectory<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Should be exported by the NFS server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">on_<wbr>prem_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfslocationonpremconfig">Dict[Nfs<wbr>Location<wbr>On<wbr>Prem<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing information for connecting to the NFS File System.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">server_<wbr>hostname<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the IP address or DNS name of the NFS server. The DataSync Agent(s) use this to mount the NFS server.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subdirectory<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Should be exported by the NFS server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## NfsLocation Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">On<wbr>Prem<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfslocationonpremconfig">Nfs<wbr>Location<wbr>On<wbr>Prem<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing information for connecting to the NFS File System.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Server<wbr>Hostname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the IP address or DNS name of the NFS server. The DataSync Agent(s) use this to mount the NFS server.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subdirectory<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Should be exported by the NFS server.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Uri<span class="property-indicator"></span>
        <span class="property-type">string</span>
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
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">On<wbr>Prem<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfslocationonpremconfig">Nfs<wbr>Location<wbr>On<wbr>Prem<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing information for connecting to the NFS File System.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Server<wbr>Hostname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the IP address or DNS name of the NFS server. The DataSync Agent(s) use this to mount the NFS server.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subdirectory<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Should be exported by the NFS server.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Uri<span class="property-indicator"></span>
        <span class="property-type">string</span>
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
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">on<wbr>Prem<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfslocationonpremconfig">Nfs<wbr>Location<wbr>On<wbr>Prem<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing information for connecting to the NFS File System.
{{% /md %}}</dd>

    <dt class="property-"
            title="">server<wbr>Hostname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the IP address or DNS name of the NFS server. The DataSync Agent(s) use this to mount the NFS server.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subdirectory<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Should be exported by the NFS server.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">uri<span class="property-indicator"></span>
        <span class="property-type">string</span>
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
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">on_<wbr>prem_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfslocationonpremconfig">Dict[Nfs<wbr>Location<wbr>On<wbr>Prem<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing information for connecting to the NFS File System.
{{% /md %}}</dd>

    <dt class="property-"
            title="">server_<wbr>hostname<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the IP address or DNS name of the NFS server. The DataSync Agent(s) use this to mount the NFS server.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subdirectory<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Should be exported by the NFS server.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">uri<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing NfsLocation Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/datasync/#NfsLocationState">NfsLocationState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/datasync/#NfsLocation">NfsLocation</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>on_prem_config=None<span class="p">, </span>server_hostname=None<span class="p">, </span>subdirectory=None<span class="p">, </span>tags=None<span class="p">, </span>uri=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetNfsLocation<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/datasync?tab=doc#NfsLocationState">NfsLocationState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/datasync?tab=doc#NfsLocation">NfsLocation</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Datasync.NfsLocation.html">NfsLocation</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Datasync.NfsLocationState.html">NfsLocationState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing NfsLocation resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">On<wbr>Prem<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfslocationonpremconfig">Nfs<wbr>Location<wbr>On<wbr>Prem<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing information for connecting to the NFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Hostname<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the IP address or DNS name of the NFS server. The DataSync Agent(s) use this to mount the NFS server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subdirectory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Should be exported by the NFS server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
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
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">On<wbr>Prem<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfslocationonpremconfig">*Nfs<wbr>Location<wbr>On<wbr>Prem<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing information for connecting to the NFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Hostname<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the IP address or DNS name of the NFS server. The DataSync Agent(s) use this to mount the NFS server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subdirectory<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Should be exported by the NFS server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Uri<span class="property-indicator"></span>
        <span class="property-type">*string</span>
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
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">on<wbr>Prem<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfslocationonpremconfig">Nfs<wbr>Location<wbr>On<wbr>Prem<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing information for connecting to the NFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server<wbr>Hostname<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the IP address or DNS name of the NFS server. The DataSync Agent(s) use this to mount the NFS server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subdirectory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Should be exported by the NFS server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
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
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">on_<wbr>prem_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfslocationonpremconfig">Dict[Nfs<wbr>Location<wbr>On<wbr>Prem<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing information for connecting to the NFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server_<wbr>hostname<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the IP address or DNS name of the NFS server. The DataSync Agent(s) use this to mount the NFS server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subdirectory<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Should be exported by the NFS server.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">uri<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### NfsLocationOnPremConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#NfsLocationOnPremConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#NfsLocationOnPremConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/datasync?tab=doc#NfsLocationOnPremConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/datasync?tab=doc#NfsLocationOnPremConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Datasync.NfsLocationOnPremConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Datasync.NfsLocationOnPremConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Agent<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the DataSync Agents used to connect to the NFS server.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Agent<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the DataSync Agents used to connect to the NFS server.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">agent<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the DataSync Agents used to connect to the NFS server.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">agent_<wbr>arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the DataSync Agents used to connect to the NFS server.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








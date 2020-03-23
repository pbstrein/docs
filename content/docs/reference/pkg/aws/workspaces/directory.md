
---
title: "Directory"
block_external_search_index: true
---

Provides a directory registration in AWS WorkSpaces Service

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const mainVpc = new aws.ec2.Vpc("main", {
    cidrBlock: "10.0.0.0/16",
});
const private_a = new aws.ec2.Subnet("private-a", {
    availabilityZone: "us-east-1a",
    cidrBlock: "10.0.0.0/24",
    vpcId: mainVpc.id,
});
const private_b = new aws.ec2.Subnet("private-b", {
    availabilityZone: "us-east-1b",
    cidrBlock: "10.0.1.0/24",
    vpcId: mainVpc.id,
});
const mainDirectory = new aws.directoryservice.Directory("main", {
    password: "#S1ncerely",
    size: "Small",
    vpcSettings: {
        subnetIds: [
            private_a.id,
            private_b.id,
        ],
        vpcId: mainVpc.id,
    },
});
const mainWorkspacesDirectory = new aws.workspaces.Directory("main", {
    directoryId: mainDirectory.id,
    selfServicePermissions: {
        increaseVolumeSize: true,
        rebuildWorkspace: true,
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/workspaces_directory.html.markdown.



## Create a Directory Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/workspaces/#Directory">Directory</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/workspaces/#DirectoryArgs">DirectoryArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Directory</span><span class="p">(resource_name, opts=None, </span>directory_id=None<span class="p">, </span>self_service_permissions=None<span class="p">, </span>subnet_ids=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDirectory<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/workspaces?tab=doc#DirectoryArgs">DirectoryArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/workspaces?tab=doc#Directory">Directory</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Workspaces.Directory.html">Directory</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Workspaces.DirectoryArgs.html">DirectoryArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The directory identifier for registration in WorkSpaces service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Self<wbr>Service<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryselfservicepermissions">Directory<wbr>Self<wbr>Service<wbr>Permissions<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The permissions to enable or disable self-service capabilities.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets where the directory resides.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the WorkSpaces directory.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The directory identifier for registration in WorkSpaces service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Self<wbr>Service<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryselfservicepermissions">*Directory<wbr>Self<wbr>Service<wbr>Permissions</a></span>
    </dt>
    <dd>{{% md %}}The permissions to enable or disable self-service capabilities.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets where the directory resides.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the WorkSpaces directory.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The directory identifier for registration in WorkSpaces service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">self<wbr>Service<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryselfservicepermissions">Directory<wbr>Self<wbr>Service<wbr>Permissions?</a></span>
    </dt>
    <dd>{{% md %}}The permissions to enable or disable self-service capabilities.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets where the directory resides.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the WorkSpaces directory.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">directory_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The directory identifier for registration in WorkSpaces service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">self_<wbr>service_<wbr>permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryselfservicepermissions">Dict[Directory<wbr>Self<wbr>Service<wbr>Permissions]</a></span>
    </dt>
    <dd>{{% md %}}The permissions to enable or disable self-service capabilities.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets where the directory resides.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the WorkSpaces directory.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Directory Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The directory identifier for registration in WorkSpaces service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Self<wbr>Service<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryselfservicepermissions">Directory<wbr>Self<wbr>Service<wbr>Permissions</a></span>
    </dt>
    <dd>{{% md %}}The permissions to enable or disable self-service capabilities.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets where the directory resides.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the WorkSpaces directory.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The directory identifier for registration in WorkSpaces service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Self<wbr>Service<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryselfservicepermissions">Directory<wbr>Self<wbr>Service<wbr>Permissions</a></span>
    </dt>
    <dd>{{% md %}}The permissions to enable or disable self-service capabilities.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets where the directory resides.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the WorkSpaces directory.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The directory identifier for registration in WorkSpaces service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">self<wbr>Service<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryselfservicepermissions">Directory<wbr>Self<wbr>Service<wbr>Permissions</a></span>
    </dt>
    <dd>{{% md %}}The permissions to enable or disable self-service capabilities.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets where the directory resides.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the WorkSpaces directory.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">directory_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The directory identifier for registration in WorkSpaces service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">self_<wbr>service_<wbr>permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryselfservicepermissions">Dict[Directory<wbr>Self<wbr>Service<wbr>Permissions]</a></span>
    </dt>
    <dd>{{% md %}}The permissions to enable or disable self-service capabilities.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets where the directory resides.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the WorkSpaces directory.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Directory Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/workspaces/#DirectoryState">DirectoryState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/workspaces/#Directory">Directory</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>directory_id=None<span class="p">, </span>self_service_permissions=None<span class="p">, </span>subnet_ids=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDirectory<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/workspaces?tab=doc#DirectoryState">DirectoryState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/workspaces?tab=doc#Directory">Directory</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Workspaces.Directory.html">Directory</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Workspaces.DirectoryState.html">DirectoryState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Directory resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The directory identifier for registration in WorkSpaces service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Self<wbr>Service<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryselfservicepermissions">Directory<wbr>Self<wbr>Service<wbr>Permissions<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The permissions to enable or disable self-service capabilities.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets where the directory resides.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the WorkSpaces directory.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The directory identifier for registration in WorkSpaces service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Self<wbr>Service<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryselfservicepermissions">*Directory<wbr>Self<wbr>Service<wbr>Permissions</a></span>
    </dt>
    <dd>{{% md %}}The permissions to enable or disable self-service capabilities.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets where the directory resides.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the WorkSpaces directory.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The directory identifier for registration in WorkSpaces service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">self<wbr>Service<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryselfservicepermissions">Directory<wbr>Self<wbr>Service<wbr>Permissions?</a></span>
    </dt>
    <dd>{{% md %}}The permissions to enable or disable self-service capabilities.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets where the directory resides.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the WorkSpaces directory.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">directory_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The directory identifier for registration in WorkSpaces service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">self_<wbr>service_<wbr>permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryselfservicepermissions">Dict[Directory<wbr>Self<wbr>Service<wbr>Permissions]</a></span>
    </dt>
    <dd>{{% md %}}The permissions to enable or disable self-service capabilities.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets where the directory resides.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the WorkSpaces directory.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### DirectorySelfServicePermissions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DirectorySelfServicePermissions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DirectorySelfServicePermissions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/workspaces?tab=doc#DirectorySelfServicePermissionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/workspaces?tab=doc#DirectorySelfServicePermissionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Workspaces.DirectorySelfServicePermissionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Workspaces.DirectorySelfServicePermissions.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Change<wbr>Compute<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can change the compute type (bundle) for their workspace. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Increase<wbr>Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can increase the volume size of the drives on their workspace. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rebuild<wbr>Workspace<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can rebuild the operating system of a workspace to its original state. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Restart<wbr>Workspace<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can restart their workspace. Default `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Switch<wbr>Running<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can switch the running mode of their workspace. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Change<wbr>Compute<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can change the compute type (bundle) for their workspace. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Increase<wbr>Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can increase the volume size of the drives on their workspace. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rebuild<wbr>Workspace<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can rebuild the operating system of a workspace to its original state. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Restart<wbr>Workspace<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can restart their workspace. Default `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Switch<wbr>Running<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can switch the running mode of their workspace. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">change<wbr>Compute<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can change the compute type (bundle) for their workspace. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">increase<wbr>Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can increase the volume size of the drives on their workspace. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rebuild<wbr>Workspace<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can rebuild the operating system of a workspace to its original state. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">restart<wbr>Workspace<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can restart their workspace. Default `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">switch<wbr>Running<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can switch the running mode of their workspace. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">change<wbr>Compute<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can change the compute type (bundle) for their workspace. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">increase<wbr>Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can increase the volume size of the drives on their workspace. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rebuild<wbr>Workspace<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can rebuild the operating system of a workspace to its original state. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">restart<wbr>Workspace<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can restart their workspace. Default `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">switch<wbr>Running<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether WorkSpaces directory users can switch the running mode of their workspace. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








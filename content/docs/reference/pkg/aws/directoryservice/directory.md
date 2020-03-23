
---
title: "Directory"
block_external_search_index: true
---

Provides a Simple or Managed Microsoft directory in AWS Directory Service.

> **Note:** All arguments including the password and customer username will be stored in the raw state as plain-text.
[Read more about sensitive data in state](https://www.terraform.io/docs/state/sensitive-data.html).

## Example Usage

### SimpleAD

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const main = new aws.ec2.Vpc("main", {
    cidrBlock: "10.0.0.0/16",
});
const foo = new aws.ec2.Subnet("foo", {
    availabilityZone: "us-west-2a",
    cidrBlock: "10.0.1.0/24",
    vpcId: main.id,
});
const barSubnet = new aws.ec2.Subnet("bar", {
    availabilityZone: "us-west-2b",
    cidrBlock: "10.0.2.0/24",
    vpcId: main.id,
});
const barDirectory = new aws.directoryservice.Directory("bar", {
    password: "SuperSecretPassw0rd",
    size: "Small",
    tags: {
        Project: "foo",
    },
    vpcSettings: {
        subnetIds: [
            foo.id,
            barSubnet.id,
        ],
        vpcId: main.id,
    },
});
```

### Microsoft Active Directory (MicrosoftAD)

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const main = new aws.ec2.Vpc("main", {
    cidrBlock: "10.0.0.0/16",
});
const foo = new aws.ec2.Subnet("foo", {
    availabilityZone: "us-west-2a",
    cidrBlock: "10.0.1.0/24",
    vpcId: main.id,
});
const barSubnet = new aws.ec2.Subnet("bar", {
    availabilityZone: "us-west-2b",
    cidrBlock: "10.0.2.0/24",
    vpcId: main.id,
});
const barDirectory = new aws.directoryservice.Directory("bar", {
    edition: "Standard",
    password: "SuperSecretPassw0rd",
    tags: {
        Project: "foo",
    },
    type: "MicrosoftAD",
    vpcSettings: {
        subnetIds: [
            foo.id,
            barSubnet.id,
        ],
        vpcId: main.id,
    },
});
```

### Microsoft Active Directory Connector (ADConnector)

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const main = new aws.ec2.Vpc("main", {
    cidrBlock: "10.0.0.0/16",
});
const foo = new aws.ec2.Subnet("foo", {
    availabilityZone: "us-west-2a",
    cidrBlock: "10.0.1.0/24",
    vpcId: main.id,
});
const bar = new aws.ec2.Subnet("bar", {
    availabilityZone: "us-west-2b",
    cidrBlock: "10.0.2.0/24",
    vpcId: main.id,
});
const connector = new aws.directoryservice.Directory("connector", {
    connectSettings: {
        customerDnsIps: ["A.B.C.D"],
        customerUsername: "Admin",
        subnetIds: [
            foo.id,
            bar.id,
        ],
        vpcId: main.id,
    },
    password: "SuperSecretPassw0rd",
    size: "Small",
    type: "ADConnector",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/directory_service_directory.html.markdown.



## Create a Directory Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directoryservice/#Directory">Directory</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directoryservice/#DirectoryArgs">DirectoryArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Directory</span><span class="p">(resource_name, opts=None, </span>alias=None<span class="p">, </span>connect_settings=None<span class="p">, </span>description=None<span class="p">, </span>edition=None<span class="p">, </span>enable_sso=None<span class="p">, </span>name=None<span class="p">, </span>password=None<span class="p">, </span>short_name=None<span class="p">, </span>size=None<span class="p">, </span>tags=None<span class="p">, </span>type=None<span class="p">, </span>vpc_settings=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDirectory<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directoryservice?tab=doc#DirectoryArgs">DirectoryArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directoryservice?tab=doc#Directory">Directory</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directoryservice.Directory.html">Directory</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directoryservice.DirectoryArgs.html">DirectoryArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Alias<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The alias for the directory (must be unique amongst all aliases in AWS). Required for `enable_sso`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connect<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryconnectsettings">Directory<wbr>Connect<wbr>Settings<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Connector related information about the directory. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A textual description for the directory.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Edition<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The MicrosoftAD edition (`Standard` or `Enterprise`). Defaults to `Enterprise` (applies to MicrosoftAD type only).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Sso<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable single-sign on for the directory. Requires `alias`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The fully qualified name for the directory, such as `corp.example.com`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Password<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The password for the directory administrator or connector user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The short name of the directory, such as `CORP`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Size<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The size of the directory (`Small` or `Large` are accepted values).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The directory type (`SimpleAD`, `ADConnector` or `MicrosoftAD` are accepted values). Defaults to `SimpleAD`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryvpcsettings">Directory<wbr>Vpc<wbr>Settings<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}VPC related information about the directory. Fields documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Alias<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The alias for the directory (must be unique amongst all aliases in AWS). Required for `enable_sso`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connect<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryconnectsettings">*Directory<wbr>Connect<wbr>Settings</a></span>
    </dt>
    <dd>{{% md %}}Connector related information about the directory. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A textual description for the directory.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Edition<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The MicrosoftAD edition (`Standard` or `Enterprise`). Defaults to `Enterprise` (applies to MicrosoftAD type only).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Sso<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable single-sign on for the directory. Requires `alias`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The fully qualified name for the directory, such as `corp.example.com`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Password<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The password for the directory administrator or connector user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The short name of the directory, such as `CORP`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Size<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The size of the directory (`Small` or `Large` are accepted values).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The directory type (`SimpleAD`, `ADConnector` or `MicrosoftAD` are accepted values). Defaults to `SimpleAD`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryvpcsettings">*Directory<wbr>Vpc<wbr>Settings</a></span>
    </dt>
    <dd>{{% md %}}VPC related information about the directory. Fields documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">alias<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The alias for the directory (must be unique amongst all aliases in AWS). Required for `enable_sso`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connect<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryconnectsettings">Directory<wbr>Connect<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}Connector related information about the directory. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A textual description for the directory.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">edition<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The MicrosoftAD edition (`Standard` or `Enterprise`). Defaults to `Enterprise` (applies to MicrosoftAD type only).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Sso<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable single-sign on for the directory. Requires `alias`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The fully qualified name for the directory, such as `corp.example.com`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">password<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The password for the directory administrator or connector user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The short name of the directory, such as `CORP`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">size<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The size of the directory (`Small` or `Large` are accepted values).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The directory type (`SimpleAD`, `ADConnector` or `MicrosoftAD` are accepted values). Defaults to `SimpleAD`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryvpcsettings">Directory<wbr>Vpc<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}VPC related information about the directory. Fields documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">alias<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The alias for the directory (must be unique amongst all aliases in AWS). Required for `enable_sso`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connect_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryconnectsettings">Dict[Directory<wbr>Connect<wbr>Settings]</a></span>
    </dt>
    <dd>{{% md %}}Connector related information about the directory. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A textual description for the directory.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">edition<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The MicrosoftAD edition (`Standard` or `Enterprise`). Defaults to `Enterprise` (applies to MicrosoftAD type only).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>sso<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable single-sign on for the directory. Requires `alias`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The fully qualified name for the directory, such as `corp.example.com`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">password<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The password for the directory administrator or connector user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">short_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The short name of the directory, such as `CORP`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">size<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The size of the directory (`Small` or `Large` are accepted values).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The directory type (`SimpleAD`, `ADConnector` or `MicrosoftAD` are accepted values). Defaults to `SimpleAD`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryvpcsettings">Dict[Directory<wbr>Vpc<wbr>Settings]</a></span>
    </dt>
    <dd>{{% md %}}VPC related information about the directory. Fields documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Directory Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Access<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The access URL for the directory, such as `http://alias.awsapps.com`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Alias<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The alias for the directory (must be unique amongst all aliases in AWS). Required for `enable_sso`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connect<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryconnectsettings">Directory<wbr>Connect<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}Connector related information about the directory. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A textual description for the directory.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dns<wbr>Ip<wbr>Addresses<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of IP addresses of the DNS servers for the directory or connector.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Edition<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The MicrosoftAD edition (`Standard` or `Enterprise`). Defaults to `Enterprise` (applies to MicrosoftAD type only).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Sso<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable single-sign on for the directory. Requires `alias`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The fully qualified name for the directory, such as `corp.example.com`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Password<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The password for the directory administrator or connector user.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by the directory.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The short name of the directory, such as `CORP`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Size<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The size of the directory (`Small` or `Large` are accepted values).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The directory type (`SimpleAD`, `ADConnector` or `MicrosoftAD` are accepted values). Defaults to `SimpleAD`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryvpcsettings">Directory<wbr>Vpc<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}VPC related information about the directory. Fields documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Access<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The access URL for the directory, such as `http://alias.awsapps.com`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Alias<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The alias for the directory (must be unique amongst all aliases in AWS). Required for `enable_sso`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connect<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryconnectsettings">*Directory<wbr>Connect<wbr>Settings</a></span>
    </dt>
    <dd>{{% md %}}Connector related information about the directory. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A textual description for the directory.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dns<wbr>Ip<wbr>Addresses<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of IP addresses of the DNS servers for the directory or connector.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Edition<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The MicrosoftAD edition (`Standard` or `Enterprise`). Defaults to `Enterprise` (applies to MicrosoftAD type only).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Sso<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable single-sign on for the directory. Requires `alias`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The fully qualified name for the directory, such as `corp.example.com`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Password<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The password for the directory administrator or connector user.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by the directory.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The short name of the directory, such as `CORP`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Size<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The size of the directory (`Small` or `Large` are accepted values).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The directory type (`SimpleAD`, `ADConnector` or `MicrosoftAD` are accepted values). Defaults to `SimpleAD`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryvpcsettings">*Directory<wbr>Vpc<wbr>Settings</a></span>
    </dt>
    <dd>{{% md %}}VPC related information about the directory. Fields documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">access<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The access URL for the directory, such as `http://alias.awsapps.com`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">alias<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The alias for the directory (must be unique amongst all aliases in AWS). Required for `enable_sso`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">connect<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryconnectsettings">Directory<wbr>Connect<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}Connector related information about the directory. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A textual description for the directory.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dns<wbr>Ip<wbr>Addresses<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of IP addresses of the DNS servers for the directory or connector.
{{% /md %}}</dd>

    <dt class="property-"
            title="">edition<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The MicrosoftAD edition (`Standard` or `Enterprise`). Defaults to `Enterprise` (applies to MicrosoftAD type only).
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable<wbr>Sso<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable single-sign on for the directory. Requires `alias`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The fully qualified name for the directory, such as `corp.example.com`
{{% /md %}}</dd>

    <dt class="property-"
            title="">password<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The password for the directory administrator or connector user.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by the directory.
{{% /md %}}</dd>

    <dt class="property-"
            title="">short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The short name of the directory, such as `CORP`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">size<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The size of the directory (`Small` or `Large` are accepted values).
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The directory type (`SimpleAD`, `ADConnector` or `MicrosoftAD` are accepted values). Defaults to `SimpleAD`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryvpcsettings">Directory<wbr>Vpc<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}VPC related information about the directory. Fields documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">access_<wbr>url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The access URL for the directory, such as `http://alias.awsapps.com`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">alias<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The alias for the directory (must be unique amongst all aliases in AWS). Required for `enable_sso`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">connect_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryconnectsettings">Dict[Directory<wbr>Connect<wbr>Settings]</a></span>
    </dt>
    <dd>{{% md %}}Connector related information about the directory. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A textual description for the directory.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dns_<wbr>ip_<wbr>addresses<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of IP addresses of the DNS servers for the directory or connector.
{{% /md %}}</dd>

    <dt class="property-"
            title="">edition<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The MicrosoftAD edition (`Standard` or `Enterprise`). Defaults to `Enterprise` (applies to MicrosoftAD type only).
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable_<wbr>sso<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable single-sign on for the directory. Requires `alias`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The fully qualified name for the directory, such as `corp.example.com`
{{% /md %}}</dd>

    <dt class="property-"
            title="">password<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The password for the directory administrator or connector user.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by the directory.
{{% /md %}}</dd>

    <dt class="property-"
            title="">short_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The short name of the directory, such as `CORP`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">size<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The size of the directory (`Small` or `Large` are accepted values).
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The directory type (`SimpleAD`, `ADConnector` or `MicrosoftAD` are accepted values). Defaults to `SimpleAD`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryvpcsettings">Dict[Directory<wbr>Vpc<wbr>Settings]</a></span>
    </dt>
    <dd>{{% md %}}VPC related information about the directory. Fields documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Directory Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directoryservice/#DirectoryState">DirectoryState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directoryservice/#Directory">Directory</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>access_url=None<span class="p">, </span>alias=None<span class="p">, </span>connect_settings=None<span class="p">, </span>description=None<span class="p">, </span>dns_ip_addresses=None<span class="p">, </span>edition=None<span class="p">, </span>enable_sso=None<span class="p">, </span>name=None<span class="p">, </span>password=None<span class="p">, </span>security_group_id=None<span class="p">, </span>short_name=None<span class="p">, </span>size=None<span class="p">, </span>tags=None<span class="p">, </span>type=None<span class="p">, </span>vpc_settings=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDirectory<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directoryservice?tab=doc#DirectoryState">DirectoryState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directoryservice?tab=doc#Directory">Directory</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directoryservice.Directory.html">Directory</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directoryservice.DirectoryState.html">DirectoryState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Access<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The access URL for the directory, such as `http://alias.awsapps.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Alias<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The alias for the directory (must be unique amongst all aliases in AWS). Required for `enable_sso`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connect<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryconnectsettings">Directory<wbr>Connect<wbr>Settings<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Connector related information about the directory. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A textual description for the directory.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dns<wbr>Ip<wbr>Addresses<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of IP addresses of the DNS servers for the directory or connector.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Edition<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The MicrosoftAD edition (`Standard` or `Enterprise`). Defaults to `Enterprise` (applies to MicrosoftAD type only).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Sso<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable single-sign on for the directory. Requires `alias`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The fully qualified name for the directory, such as `corp.example.com`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The password for the directory administrator or connector user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by the directory.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The short name of the directory, such as `CORP`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Size<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The size of the directory (`Small` or `Large` are accepted values).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The directory type (`SimpleAD`, `ADConnector` or `MicrosoftAD` are accepted values). Defaults to `SimpleAD`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryvpcsettings">Directory<wbr>Vpc<wbr>Settings<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}VPC related information about the directory. Fields documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Access<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The access URL for the directory, such as `http://alias.awsapps.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Alias<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The alias for the directory (must be unique amongst all aliases in AWS). Required for `enable_sso`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connect<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryconnectsettings">*Directory<wbr>Connect<wbr>Settings</a></span>
    </dt>
    <dd>{{% md %}}Connector related information about the directory. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A textual description for the directory.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dns<wbr>Ip<wbr>Addresses<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of IP addresses of the DNS servers for the directory or connector.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Edition<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The MicrosoftAD edition (`Standard` or `Enterprise`). Defaults to `Enterprise` (applies to MicrosoftAD type only).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Sso<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable single-sign on for the directory. Requires `alias`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The fully qualified name for the directory, such as `corp.example.com`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Password<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The password for the directory administrator or connector user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by the directory.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The short name of the directory, such as `CORP`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Size<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The size of the directory (`Small` or `Large` are accepted values).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The directory type (`SimpleAD`, `ADConnector` or `MicrosoftAD` are accepted values). Defaults to `SimpleAD`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryvpcsettings">*Directory<wbr>Vpc<wbr>Settings</a></span>
    </dt>
    <dd>{{% md %}}VPC related information about the directory. Fields documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The access URL for the directory, such as `http://alias.awsapps.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">alias<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The alias for the directory (must be unique amongst all aliases in AWS). Required for `enable_sso`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connect<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryconnectsettings">Directory<wbr>Connect<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}Connector related information about the directory. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A textual description for the directory.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dns<wbr>Ip<wbr>Addresses<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of IP addresses of the DNS servers for the directory or connector.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">edition<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The MicrosoftAD edition (`Standard` or `Enterprise`). Defaults to `Enterprise` (applies to MicrosoftAD type only).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Sso<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable single-sign on for the directory. Requires `alias`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The fully qualified name for the directory, such as `corp.example.com`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The password for the directory administrator or connector user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by the directory.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">short<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The short name of the directory, such as `CORP`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">size<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The size of the directory (`Small` or `Large` are accepted values).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The directory type (`SimpleAD`, `ADConnector` or `MicrosoftAD` are accepted values). Defaults to `SimpleAD`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryvpcsettings">Directory<wbr>Vpc<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}VPC related information about the directory. Fields documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access_<wbr>url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The access URL for the directory, such as `http://alias.awsapps.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">alias<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The alias for the directory (must be unique amongst all aliases in AWS). Required for `enable_sso`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connect_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryconnectsettings">Dict[Directory<wbr>Connect<wbr>Settings]</a></span>
    </dt>
    <dd>{{% md %}}Connector related information about the directory. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A textual description for the directory.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dns_<wbr>ip_<wbr>addresses<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of IP addresses of the DNS servers for the directory or connector.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">edition<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The MicrosoftAD edition (`Standard` or `Enterprise`). Defaults to `Enterprise` (applies to MicrosoftAD type only).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>sso<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable single-sign on for the directory. Requires `alias`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The fully qualified name for the directory, such as `corp.example.com`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">password<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The password for the directory administrator or connector user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by the directory.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">short_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The short name of the directory, such as `CORP`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">size<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The size of the directory (`Small` or `Large` are accepted values).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The directory type (`SimpleAD`, `ADConnector` or `MicrosoftAD` are accepted values). Defaults to `SimpleAD`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#directoryvpcsettings">Dict[Directory<wbr>Vpc<wbr>Settings]</a></span>
    </dt>
    <dd>{{% md %}}VPC related information about the directory. Fields documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### DirectoryConnectSettings
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DirectoryConnectSettings">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DirectoryConnectSettings">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directoryservice?tab=doc#DirectoryConnectSettingsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directoryservice?tab=doc#DirectoryConnectSettingsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directoryservice.DirectoryConnectSettingsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directoryservice.DirectoryConnectSettings.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Customer<wbr>Dns<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The DNS IP addresses of the domain to connect to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Customer<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The username corresponding to the password provided.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets for the directory servers (2 subnets in 2 different AZs).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC that the directory is in.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Customer<wbr>Dns<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The DNS IP addresses of the domain to connect to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Customer<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The username corresponding to the password provided.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets for the directory servers (2 subnets in 2 different AZs).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC that the directory is in.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">customer<wbr>Dns<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The DNS IP addresses of the domain to connect to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">customer<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The username corresponding to the password provided.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets for the directory servers (2 subnets in 2 different AZs).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC that the directory is in.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">customer<wbr>Dns<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The DNS IP addresses of the domain to connect to.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">customer<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The username corresponding to the password provided.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets for the directory servers (2 subnets in 2 different AZs).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC that the directory is in.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DirectoryVpcSettings
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DirectoryVpcSettings">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DirectoryVpcSettings">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directoryservice?tab=doc#DirectoryVpcSettingsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directoryservice?tab=doc#DirectoryVpcSettingsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directoryservice.DirectoryVpcSettingsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directoryservice.DirectoryVpcSettings.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets for the directory servers (2 subnets in 2 different AZs).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC that the directory is in.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets for the directory servers (2 subnets in 2 different AZs).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC that the directory is in.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets for the directory servers (2 subnets in 2 different AZs).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC that the directory is in.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The identifiers of the subnets for the directory servers (2 subnets in 2 different AZs).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC that the directory is in.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








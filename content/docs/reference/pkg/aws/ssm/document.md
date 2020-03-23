
---
title: "Document"
block_external_search_index: true
---

Provides an SSM Document resource

> **NOTE on updating SSM documents:** Only documents with a schema version of 2.0
or greater can update their content once created, see [SSM Schema Features][1]. To update a document with an older
schema version you must recreate the resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const foo = new aws.ssm.Document("foo", {
    content: `  {
    "schemaVersion": "1.2",
    "description": "Check ip configuration of a Linux instance.",
    "parameters": {

    },
    "runtimeConfig": {
      "aws:runShellScript": {
        "properties": [
          {
            "id": "0.aws:runShellScript",
            "runCommand": ["ifconfig"]
          }
        ]
      }
    }
  }
`,
    documentType: "Command",
});
```

## attachments_source

The `attachments_source` block supports the following:

* `key` - (Required) The key describing the location of an attachment to a document. Valid key types include: `SourceUrl` and `S3FileUrl`
* `values` - (Required) The value describing the location of an attachment to a document
* `name` - (Optional) The name of the document attachment file

## Permissions

The permissions attribute specifies how you want to share the document. If you share a document privately,
you must specify the AWS user account IDs for those people who can use the document. If you share a document
publicly, you must specify All as the account ID.

The permissions mapping supports the following:

* `type` - The permission type for the document. The permission type can be `Share`.
* `account_ids` - The AWS user accounts that should have access to the document. The account IDs can either be a group of account IDs or `All`.

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/ssm_document.html.markdown.



## Create a Document Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#Document">Document</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#DocumentArgs">DocumentArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Document</span><span class="p">(resource_name, opts=None, </span>attachments_sources=None<span class="p">, </span>content=None<span class="p">, </span>document_format=None<span class="p">, </span>document_type=None<span class="p">, </span>name=None<span class="p">, </span>permissions=None<span class="p">, </span>tags=None<span class="p">, </span>target_type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDocument<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#DocumentArgs">DocumentArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#Document">Document</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.Document.html">Document</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.DocumentArgs.html">DocumentArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Attachments<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentattachmentssource">List&lt;Document<wbr>Attachments<wbr>Source<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks describing attachments sources to a version of a document. Defined below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Content<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The JSON or YAML content of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The format of the document. Valid document types include: `JSON` and `YAML`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Document<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the document. Valid document types include: `Automation`, `Command`, `Package`, `Policy`, and `Session`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentpermissions">Document<wbr>Permissions<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Additional Permissions to attach to the document. See Permissions below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The target type which defines the kinds of resources the document can run on. For example, /AWS::EC2::Instance. For a list of valid resource types, see AWS Resource Types Reference (http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Attachments<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentattachmentssource">[]Document<wbr>Attachments<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks describing attachments sources to a version of a document. Defined below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Content<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The JSON or YAML content of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The format of the document. Valid document types include: `JSON` and `YAML`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Document<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the document. Valid document types include: `Automation`, `Command`, `Package`, `Policy`, and `Session`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentpermissions">*Document<wbr>Permissions</a></span>
    </dt>
    <dd>{{% md %}}Additional Permissions to attach to the document. See Permissions below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The target type which defines the kinds of resources the document can run on. For example, /AWS::EC2::Instance. For a list of valid resource types, see AWS Resource Types Reference (http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">attachments<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentattachmentssource">Document<wbr>Attachments<wbr>Source[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks describing attachments sources to a version of a document. Defined below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">content<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The JSON or YAML content of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The format of the document. Valid document types include: `JSON` and `YAML`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">document<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the document. Valid document types include: `Automation`, `Command`, `Package`, `Policy`, and `Session`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentpermissions">Document<wbr>Permissions?</a></span>
    </dt>
    <dd>{{% md %}}Additional Permissions to attach to the document. See Permissions below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The target type which defines the kinds of resources the document can run on. For example, /AWS::EC2::Instance. For a list of valid resource types, see AWS Resource Types Reference (http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">attachments_<wbr>sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentattachmentssource">List[Document<wbr>Attachments<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks describing attachments sources to a version of a document. Defined below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">content<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The JSON or YAML content of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document_<wbr>format<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The format of the document. Valid document types include: `JSON` and `YAML`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">document_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the document. Valid document types include: `Automation`, `Command`, `Package`, `Policy`, and `Session`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentpermissions">Dict[Document<wbr>Permissions]</a></span>
    </dt>
    <dd>{{% md %}}Additional Permissions to attach to the document. See Permissions below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The target type which defines the kinds of resources the document can run on. For example, /AWS::EC2::Instance. For a list of valid resource types, see AWS Resource Types Reference (http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Document Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Attachments<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentattachmentssource">List&lt;Document<wbr>Attachments<wbr>Source&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks describing attachments sources to a version of a document. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The JSON or YAML content of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date the document was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The default version of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The description of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Document<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The format of the document. Valid document types include: `JSON` and `YAML`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Document<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the document. Valid document types include: `Automation`, `Command`, `Package`, `Policy`, and `Session`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hash<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The sha1 or sha256 of the document content
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hash<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}&#34;Sha1&#34; &#34;Sha256&#34;. The hashing algorithm used when hashing the content.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Latest<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The latest version of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS user account of the person who created the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentparameter">List&lt;Document<wbr>Parameter&gt;</a></span>
    </dt>
    <dd>{{% md %}}The parameters that are available to this document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentpermissions">Document<wbr>Permissions?</a></span>
    </dt>
    <dd>{{% md %}}Additional Permissions to attach to the document. See Permissions below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Platform<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of OS platforms compatible with this SSM document, either &#34;Windows&#34; or &#34;Linux&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Schema<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The schema version of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}&#34;Creating&#34;, &#34;Active&#34; or &#34;Deleting&#34;. The current status of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The target type which defines the kinds of resources the document can run on. For example, /AWS::EC2::Instance. For a list of valid resource types, see AWS Resource Types Reference (http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Attachments<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentattachmentssource">[]Document<wbr>Attachments<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks describing attachments sources to a version of a document. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The JSON or YAML content of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date the document was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The default version of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The description of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Document<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The format of the document. Valid document types include: `JSON` and `YAML`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Document<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the document. Valid document types include: `Automation`, `Command`, `Package`, `Policy`, and `Session`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hash<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The sha1 or sha256 of the document content
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hash<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}&#34;Sha1&#34; &#34;Sha256&#34;. The hashing algorithm used when hashing the content.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Latest<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The latest version of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS user account of the person who created the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentparameter">[]Document<wbr>Parameter</a></span>
    </dt>
    <dd>{{% md %}}The parameters that are available to this document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentpermissions">*Document<wbr>Permissions</a></span>
    </dt>
    <dd>{{% md %}}Additional Permissions to attach to the document. See Permissions below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Platform<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of OS platforms compatible with this SSM document, either &#34;Windows&#34; or &#34;Linux&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Schema<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The schema version of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}&#34;Creating&#34;, &#34;Active&#34; or &#34;Deleting&#34;. The current status of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The target type which defines the kinds of resources the document can run on. For example, /AWS::EC2::Instance. For a list of valid resource types, see AWS Resource Types Reference (http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">attachments<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentattachmentssource">Document<wbr>Attachments<wbr>Source[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks describing attachments sources to a version of a document. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The JSON or YAML content of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date the document was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The default version of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The description of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">document<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The format of the document. Valid document types include: `JSON` and `YAML`
{{% /md %}}</dd>

    <dt class="property-"
            title="">document<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the document. Valid document types include: `Automation`, `Command`, `Package`, `Policy`, and `Session`
{{% /md %}}</dd>

    <dt class="property-"
            title="">hash<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The sha1 or sha256 of the document content
{{% /md %}}</dd>

    <dt class="property-"
            title="">hash<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}&#34;Sha1&#34; &#34;Sha256&#34;. The hashing algorithm used when hashing the content.
{{% /md %}}</dd>

    <dt class="property-"
            title="">latest<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The latest version of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS user account of the person who created the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentparameter">Document<wbr>Parameter[]</a></span>
    </dt>
    <dd>{{% md %}}The parameters that are available to this document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentpermissions">Document<wbr>Permissions?</a></span>
    </dt>
    <dd>{{% md %}}Additional Permissions to attach to the document. See Permissions below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">platform<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of OS platforms compatible with this SSM document, either &#34;Windows&#34; or &#34;Linux&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">schema<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The schema version of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}&#34;Creating&#34;, &#34;Active&#34; or &#34;Deleting&#34;. The current status of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The target type which defines the kinds of resources the document can run on. For example, /AWS::EC2::Instance. For a list of valid resource types, see AWS Resource Types Reference (http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">attachments_<wbr>sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentattachmentssource">List[Document<wbr>Attachments<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks describing attachments sources to a version of a document. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The JSON or YAML content of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date the document was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The default version of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">document_<wbr>format<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The format of the document. Valid document types include: `JSON` and `YAML`
{{% /md %}}</dd>

    <dt class="property-"
            title="">document_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the document. Valid document types include: `Automation`, `Command`, `Package`, `Policy`, and `Session`
{{% /md %}}</dd>

    <dt class="property-"
            title="">hash<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The sha1 or sha256 of the document content
{{% /md %}}</dd>

    <dt class="property-"
            title="">hash_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}&#34;Sha1&#34; &#34;Sha256&#34;. The hashing algorithm used when hashing the content.
{{% /md %}}</dd>

    <dt class="property-"
            title="">latest_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The latest version of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS user account of the person who created the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentparameter">List[Document<wbr>Parameter]</a></span>
    </dt>
    <dd>{{% md %}}The parameters that are available to this document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentpermissions">Dict[Document<wbr>Permissions]</a></span>
    </dt>
    <dd>{{% md %}}Additional Permissions to attach to the document. See Permissions below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">platform_<wbr>types<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of OS platforms compatible with this SSM document, either &#34;Windows&#34; or &#34;Linux&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">schema_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The schema version of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}&#34;Creating&#34;, &#34;Active&#34; or &#34;Deleting&#34;. The current status of the document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">target_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The target type which defines the kinds of resources the document can run on. For example, /AWS::EC2::Instance. For a list of valid resource types, see AWS Resource Types Reference (http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Document Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#DocumentState">DocumentState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#Document">Document</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>attachments_sources=None<span class="p">, </span>content=None<span class="p">, </span>created_date=None<span class="p">, </span>default_version=None<span class="p">, </span>description=None<span class="p">, </span>document_format=None<span class="p">, </span>document_type=None<span class="p">, </span>hash=None<span class="p">, </span>hash_type=None<span class="p">, </span>latest_version=None<span class="p">, </span>name=None<span class="p">, </span>owner=None<span class="p">, </span>parameters=None<span class="p">, </span>permissions=None<span class="p">, </span>platform_types=None<span class="p">, </span>schema_version=None<span class="p">, </span>status=None<span class="p">, </span>tags=None<span class="p">, </span>target_type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDocument<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#DocumentState">DocumentState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#Document">Document</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.Document.html">Document</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.DocumentState.html">DocumentState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Document resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Attachments<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentattachmentssource">List&lt;Document<wbr>Attachments<wbr>Source<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks describing attachments sources to a version of a document. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The JSON or YAML content of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date the document was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default version of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The format of the document. Valid document types include: `JSON` and `YAML`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the document. Valid document types include: `Automation`, `Command`, `Package`, `Policy`, and `Session`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hash<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The sha1 or sha256 of the document content
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hash<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}&#34;Sha1&#34; &#34;Sha256&#34;. The hashing algorithm used when hashing the content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Latest<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The latest version of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS user account of the person who created the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentparameter">List&lt;Document<wbr>Parameter<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The parameters that are available to this document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentpermissions">Document<wbr>Permissions<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Additional Permissions to attach to the document. See Permissions below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Platform<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of OS platforms compatible with this SSM document, either &#34;Windows&#34; or &#34;Linux&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schema<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The schema version of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}&#34;Creating&#34;, &#34;Active&#34; or &#34;Deleting&#34;. The current status of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The target type which defines the kinds of resources the document can run on. For example, /AWS::EC2::Instance. For a list of valid resource types, see AWS Resource Types Reference (http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Attachments<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentattachmentssource">[]Document<wbr>Attachments<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks describing attachments sources to a version of a document. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The JSON or YAML content of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The date the document was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The default version of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The format of the document. Valid document types include: `JSON` and `YAML`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the document. Valid document types include: `Automation`, `Command`, `Package`, `Policy`, and `Session`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hash<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The sha1 or sha256 of the document content
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hash<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}&#34;Sha1&#34; &#34;Sha256&#34;. The hashing algorithm used when hashing the content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Latest<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The latest version of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS user account of the person who created the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentparameter">[]Document<wbr>Parameter</a></span>
    </dt>
    <dd>{{% md %}}The parameters that are available to this document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentpermissions">*Document<wbr>Permissions</a></span>
    </dt>
    <dd>{{% md %}}Additional Permissions to attach to the document. See Permissions below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Platform<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of OS platforms compatible with this SSM document, either &#34;Windows&#34; or &#34;Linux&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schema<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The schema version of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}&#34;Creating&#34;, &#34;Active&#34; or &#34;Deleting&#34;. The current status of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The target type which defines the kinds of resources the document can run on. For example, /AWS::EC2::Instance. For a list of valid resource types, see AWS Resource Types Reference (http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">attachments<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentattachmentssource">Document<wbr>Attachments<wbr>Source[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks describing attachments sources to a version of a document. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The JSON or YAML content of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date the document was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default version of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The format of the document. Valid document types include: `JSON` and `YAML`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the document. Valid document types include: `Automation`, `Command`, `Package`, `Policy`, and `Session`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hash<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The sha1 or sha256 of the document content
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hash<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}&#34;Sha1&#34; &#34;Sha256&#34;. The hashing algorithm used when hashing the content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">latest<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The latest version of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS user account of the person who created the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentparameter">Document<wbr>Parameter[]?</a></span>
    </dt>
    <dd>{{% md %}}The parameters that are available to this document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentpermissions">Document<wbr>Permissions?</a></span>
    </dt>
    <dd>{{% md %}}Additional Permissions to attach to the document. See Permissions below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">platform<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of OS platforms compatible with this SSM document, either &#34;Windows&#34; or &#34;Linux&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schema<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The schema version of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}&#34;Creating&#34;, &#34;Active&#34; or &#34;Deleting&#34;. The current status of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The target type which defines the kinds of resources the document can run on. For example, /AWS::EC2::Instance. For a list of valid resource types, see AWS Resource Types Reference (http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">attachments_<wbr>sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentattachmentssource">List[Document<wbr>Attachments<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}One or more configuration blocks describing attachments sources to a version of a document. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The JSON or YAML content of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date the document was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The default version of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document_<wbr>format<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The format of the document. Valid document types include: `JSON` and `YAML`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the document. Valid document types include: `Automation`, `Command`, `Package`, `Policy`, and `Session`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hash<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The sha1 or sha256 of the document content
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hash_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}&#34;Sha1&#34; &#34;Sha256&#34;. The hashing algorithm used when hashing the content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">latest_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The latest version of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS user account of the person who created the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentparameter">List[Document<wbr>Parameter]</a></span>
    </dt>
    <dd>{{% md %}}The parameters that are available to this document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentpermissions">Dict[Document<wbr>Permissions]</a></span>
    </dt>
    <dd>{{% md %}}Additional Permissions to attach to the document. See Permissions below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">platform_<wbr>types<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of OS platforms compatible with this SSM document, either &#34;Windows&#34; or &#34;Linux&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schema_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The schema version of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}&#34;Creating&#34;, &#34;Active&#34; or &#34;Deleting&#34;. The current status of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The target type which defines the kinds of resources the document can run on. For example, /AWS::EC2::Instance. For a list of valid resource types, see AWS Resource Types Reference (http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### DocumentAttachmentsSource
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DocumentAttachmentsSource">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DocumentAttachmentsSource">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#DocumentAttachmentsSourceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#DocumentAttachmentsSourceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.DocumentAttachmentsSourceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.DocumentAttachmentsSource.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
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
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
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
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
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
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DocumentParameter
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DocumentParameter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#DocumentParameterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.DocumentParameter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Default<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

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
            title="Optional">Default<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

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
            title="Optional">default<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

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
            title="Optional">default_<wbr>value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DocumentPermissions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DocumentPermissions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DocumentPermissions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#DocumentPermissionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#DocumentPermissionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.DocumentPermissionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.DocumentPermissions.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Account<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Account<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">account<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">account_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








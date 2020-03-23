
---
title: "NfsFileShare"
block_external_search_index: true
---

Manages an AWS Storage Gateway NFS File Share.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.storagegateway.NfsFileShare("example", {
    clientLists: ["0.0.0.0/0"],
    gatewayArn: aws_storagegateway_gateway_example.arn,
    locationArn: aws_s3_bucket_example.arn,
    roleArn: aws_iam_role_example.arn,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/storagegateway_nfs_file_share.html.markdown.



## Create a NfsFileShare Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/storagegateway/#NfsFileShare">NfsFileShare</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/storagegateway/#NfsFileShareArgs">NfsFileShareArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">NfsFileShare</span><span class="p">(resource_name, opts=None, </span>client_lists=None<span class="p">, </span>default_storage_class=None<span class="p">, </span>gateway_arn=None<span class="p">, </span>guess_mime_type_enabled=None<span class="p">, </span>kms_encrypted=None<span class="p">, </span>kms_key_arn=None<span class="p">, </span>location_arn=None<span class="p">, </span>nfs_file_share_defaults=None<span class="p">, </span>object_acl=None<span class="p">, </span>read_only=None<span class="p">, </span>requester_pays=None<span class="p">, </span>role_arn=None<span class="p">, </span>squash=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewNfsFileShare<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/storagegateway?tab=doc#NfsFileShareArgs">NfsFileShareArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/storagegateway?tab=doc#NfsFileShare">NfsFileShare</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Storagegateway.NfsFileShare.html">NfsFileShare</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Storagegateway.NfsFileShareArgs.html">NfsFileShareArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Client<wbr>Lists<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The list of clients that are allowed to access the file gateway. The list must contain either valid IP addresses or valid CIDR blocks. Set to `[&#34;0.0.0.0/0&#34;]` to not limit access. Minimum 1 item. Maximum 100 items.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default storage class for objects put into an Amazon S3 bucket by the file gateway. Defaults to `S3_STANDARD`. Valid values: `S3_STANDARD`, `S3_STANDARD_IA`, `S3_ONEZONE_IA`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Gateway<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the file gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Guess<wbr>Mime<wbr>Type<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value that enables guessing of the MIME type for uploaded objects based on file extensions. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value if `true` to use Amazon S3 server side encryption with your own AWS KMS key, or `false` to use a key managed by Amazon S3. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) for KMS key used for Amazon S3 server side encryption. This value can only be set when `kms_encrypted` is true.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Location<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the backed storage used for storing file data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Nfs<wbr>File<wbr>Share<wbr>Defaults<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfsfilesharenfsfilesharedefaults">Nfs<wbr>File<wbr>Share<wbr>Nfs<wbr>File<wbr>Share<wbr>Defaults<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument with file share default values. More information below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Access Control List permission for S3 bucket objects. Defaults to `private`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean to indicate write status of file share. File share does not accept writes if `true`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requester<wbr>Pays<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean who pays the cost of the request and the data download from the Amazon S3 bucket. Set this value to `true` if you want the requester to pay instead of the bucket owner. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the AWS Identity and Access Management (IAM) role that a file gateway assumes when it accesses the underlying storage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Squash<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Maps a user to anonymous user. Defaults to `RootSquash`. Valid values: `RootSquash` (only root is mapped to anonymous user), `NoSquash` (no one is mapped to anonymous user), `AllSquash` (everyone is mapped to anonymous user)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Client<wbr>Lists<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of clients that are allowed to access the file gateway. The list must contain either valid IP addresses or valid CIDR blocks. Set to `[&#34;0.0.0.0/0&#34;]` to not limit access. Minimum 1 item. Maximum 100 items.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The default storage class for objects put into an Amazon S3 bucket by the file gateway. Defaults to `S3_STANDARD`. Valid values: `S3_STANDARD`, `S3_STANDARD_IA`, `S3_ONEZONE_IA`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Gateway<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the file gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Guess<wbr>Mime<wbr>Type<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value that enables guessing of the MIME type for uploaded objects based on file extensions. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value if `true` to use Amazon S3 server side encryption with your own AWS KMS key, or `false` to use a key managed by Amazon S3. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) for KMS key used for Amazon S3 server side encryption. This value can only be set when `kms_encrypted` is true.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Location<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the backed storage used for storing file data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Nfs<wbr>File<wbr>Share<wbr>Defaults<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfsfilesharenfsfilesharedefaults">*Nfs<wbr>File<wbr>Share<wbr>Nfs<wbr>File<wbr>Share<wbr>Defaults</a></span>
    </dt>
    <dd>{{% md %}}Nested argument with file share default values. More information below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Acl<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Access Control List permission for S3 bucket objects. Defaults to `private`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean to indicate write status of file share. File share does not accept writes if `true`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requester<wbr>Pays<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean who pays the cost of the request and the data download from the Amazon S3 bucket. Set this value to `true` if you want the requester to pay instead of the bucket owner. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the AWS Identity and Access Management (IAM) role that a file gateway assumes when it accesses the underlying storage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Squash<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Maps a user to anonymous user. Defaults to `RootSquash`. Valid values: `RootSquash` (only root is mapped to anonymous user), `NoSquash` (no one is mapped to anonymous user), `AllSquash` (everyone is mapped to anonymous user)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">client<wbr>Lists<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The list of clients that are allowed to access the file gateway. The list must contain either valid IP addresses or valid CIDR blocks. Set to `[&#34;0.0.0.0/0&#34;]` to not limit access. Minimum 1 item. Maximum 100 items.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default storage class for objects put into an Amazon S3 bucket by the file gateway. Defaults to `S3_STANDARD`. Valid values: `S3_STANDARD`, `S3_STANDARD_IA`, `S3_ONEZONE_IA`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">gateway<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the file gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">guess<wbr>Mime<wbr>Type<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value that enables guessing of the MIME type for uploaded objects based on file extensions. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value if `true` to use Amazon S3 server side encryption with your own AWS KMS key, or `false` to use a key managed by Amazon S3. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) for KMS key used for Amazon S3 server side encryption. This value can only be set when `kms_encrypted` is true.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">location<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the backed storage used for storing file data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">nfs<wbr>File<wbr>Share<wbr>Defaults<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfsfilesharenfsfilesharedefaults">Nfs<wbr>File<wbr>Share<wbr>Nfs<wbr>File<wbr>Share<wbr>Defaults?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument with file share default values. More information below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object<wbr>Acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Access Control List permission for S3 bucket objects. Defaults to `private`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean to indicate write status of file share. File share does not accept writes if `true`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requester<wbr>Pays<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean who pays the cost of the request and the data download from the Amazon S3 bucket. Set this value to `true` if you want the requester to pay instead of the bucket owner. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the AWS Identity and Access Management (IAM) role that a file gateway assumes when it accesses the underlying storage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">squash<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Maps a user to anonymous user. Defaults to `RootSquash`. Valid values: `RootSquash` (only root is mapped to anonymous user), `NoSquash` (no one is mapped to anonymous user), `AllSquash` (everyone is mapped to anonymous user)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">client_<wbr>lists<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of clients that are allowed to access the file gateway. The list must contain either valid IP addresses or valid CIDR blocks. Set to `[&#34;0.0.0.0/0&#34;]` to not limit access. Minimum 1 item. Maximum 100 items.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>storage_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The default storage class for objects put into an Amazon S3 bucket by the file gateway. Defaults to `S3_STANDARD`. Valid values: `S3_STANDARD`, `S3_STANDARD_IA`, `S3_ONEZONE_IA`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">gateway_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the file gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">guess_<wbr>mime_<wbr>type_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value that enables guessing of the MIME type for uploaded objects based on file extensions. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value if `true` to use Amazon S3 server side encryption with your own AWS KMS key, or `false` to use a key managed by Amazon S3. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) for KMS key used for Amazon S3 server side encryption. This value can only be set when `kms_encrypted` is true.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">location_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the backed storage used for storing file data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">nfs_<wbr>file_<wbr>share_<wbr>defaults<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfsfilesharenfsfilesharedefaults">Dict[Nfs<wbr>File<wbr>Share<wbr>Nfs<wbr>File<wbr>Share<wbr>Defaults]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument with file share default values. More information below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object_<wbr>acl<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Access Control List permission for S3 bucket objects. Defaults to `private`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read_<wbr>only<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean to indicate write status of file share. File share does not accept writes if `true`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requester_<wbr>pays<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean who pays the cost of the request and the data download from the Amazon S3 bucket. Set this value to `true` if you want the requester to pay instead of the bucket owner. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the AWS Identity and Access Management (IAM) role that a file gateway assumes when it accesses the underlying storage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">squash<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Maps a user to anonymous user. Defaults to `RootSquash`. Valid values: `RootSquash` (only root is mapped to anonymous user), `NoSquash` (no one is mapped to anonymous user), `AllSquash` (everyone is mapped to anonymous user)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## NfsFileShare Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Client<wbr>Lists<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The list of clients that are allowed to access the file gateway. The list must contain either valid IP addresses or valid CIDR blocks. Set to `[&#34;0.0.0.0/0&#34;]` to not limit access. Minimum 1 item. Maximum 100 items.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default storage class for objects put into an Amazon S3 bucket by the file gateway. Defaults to `S3_STANDARD`. Valid values: `S3_STANDARD`, `S3_STANDARD_IA`, `S3_ONEZONE_IA`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Fileshare<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Gateway<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the file gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Guess<wbr>Mime<wbr>Type<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value that enables guessing of the MIME type for uploaded objects based on file extensions. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value if `true` to use Amazon S3 server side encryption with your own AWS KMS key, or `false` to use a key managed by Amazon S3. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) for KMS key used for Amazon S3 server side encryption. This value can only be set when `kms_encrypted` is true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Location<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the backed storage used for storing file data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Nfs<wbr>File<wbr>Share<wbr>Defaults<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfsfilesharenfsfilesharedefaults">Nfs<wbr>File<wbr>Share<wbr>Nfs<wbr>File<wbr>Share<wbr>Defaults?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument with file share default values. More information below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Object<wbr>Acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Access Control List permission for S3 bucket objects. Defaults to `private`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Read<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean to indicate write status of file share. File share does not accept writes if `true`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Requester<wbr>Pays<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean who pays the cost of the request and the data download from the Amazon S3 bucket. Set this value to `true` if you want the requester to pay instead of the bucket owner. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the AWS Identity and Access Management (IAM) role that a file gateway assumes when it accesses the underlying storage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Squash<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Maps a user to anonymous user. Defaults to `RootSquash`. Valid values: `RootSquash` (only root is mapped to anonymous user), `NoSquash` (no one is mapped to anonymous user), `AllSquash` (everyone is mapped to anonymous user)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Client<wbr>Lists<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of clients that are allowed to access the file gateway. The list must contain either valid IP addresses or valid CIDR blocks. Set to `[&#34;0.0.0.0/0&#34;]` to not limit access. Minimum 1 item. Maximum 100 items.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The default storage class for objects put into an Amazon S3 bucket by the file gateway. Defaults to `S3_STANDARD`. Valid values: `S3_STANDARD`, `S3_STANDARD_IA`, `S3_ONEZONE_IA`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Fileshare<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Gateway<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the file gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Guess<wbr>Mime<wbr>Type<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value that enables guessing of the MIME type for uploaded objects based on file extensions. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value if `true` to use Amazon S3 server side encryption with your own AWS KMS key, or `false` to use a key managed by Amazon S3. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) for KMS key used for Amazon S3 server side encryption. This value can only be set when `kms_encrypted` is true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Location<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the backed storage used for storing file data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Nfs<wbr>File<wbr>Share<wbr>Defaults<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfsfilesharenfsfilesharedefaults">*Nfs<wbr>File<wbr>Share<wbr>Nfs<wbr>File<wbr>Share<wbr>Defaults</a></span>
    </dt>
    <dd>{{% md %}}Nested argument with file share default values. More information below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Object<wbr>Acl<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Access Control List permission for S3 bucket objects. Defaults to `private`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Read<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean to indicate write status of file share. File share does not accept writes if `true`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Requester<wbr>Pays<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean who pays the cost of the request and the data download from the Amazon S3 bucket. Set this value to `true` if you want the requester to pay instead of the bucket owner. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the AWS Identity and Access Management (IAM) role that a file gateway assumes when it accesses the underlying storage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Squash<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Maps a user to anonymous user. Defaults to `RootSquash`. Valid values: `RootSquash` (only root is mapped to anonymous user), `NoSquash` (no one is mapped to anonymous user), `AllSquash` (everyone is mapped to anonymous user)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-"
            title="">client<wbr>Lists<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The list of clients that are allowed to access the file gateway. The list must contain either valid IP addresses or valid CIDR blocks. Set to `[&#34;0.0.0.0/0&#34;]` to not limit access. Minimum 1 item. Maximum 100 items.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default storage class for objects put into an Amazon S3 bucket by the file gateway. Defaults to `S3_STANDARD`. Valid values: `S3_STANDARD`, `S3_STANDARD_IA`, `S3_ONEZONE_IA`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">fileshare<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-"
            title="">gateway<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the file gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">guess<wbr>Mime<wbr>Type<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value that enables guessing of the MIME type for uploaded objects based on file extensions. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value if `true` to use Amazon S3 server side encryption with your own AWS KMS key, or `false` to use a key managed by Amazon S3. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) for KMS key used for Amazon S3 server side encryption. This value can only be set when `kms_encrypted` is true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">location<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the backed storage used for storing file data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">nfs<wbr>File<wbr>Share<wbr>Defaults<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfsfilesharenfsfilesharedefaults">Nfs<wbr>File<wbr>Share<wbr>Nfs<wbr>File<wbr>Share<wbr>Defaults?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument with file share default values. More information below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">object<wbr>Acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Access Control List permission for S3 bucket objects. Defaults to `private`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">read<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean to indicate write status of file share. File share does not accept writes if `true`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">requester<wbr>Pays<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean who pays the cost of the request and the data download from the Amazon S3 bucket. Set this value to `true` if you want the requester to pay instead of the bucket owner. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the AWS Identity and Access Management (IAM) role that a file gateway assumes when it accesses the underlying storage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">squash<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Maps a user to anonymous user. Defaults to `RootSquash`. Valid values: `RootSquash` (only root is mapped to anonymous user), `NoSquash` (no one is mapped to anonymous user), `AllSquash` (everyone is mapped to anonymous user)
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-"
            title="">client_<wbr>lists<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of clients that are allowed to access the file gateway. The list must contain either valid IP addresses or valid CIDR blocks. Set to `[&#34;0.0.0.0/0&#34;]` to not limit access. Minimum 1 item. Maximum 100 items.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>storage_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The default storage class for objects put into an Amazon S3 bucket by the file gateway. Defaults to `S3_STANDARD`. Valid values: `S3_STANDARD`, `S3_STANDARD_IA`, `S3_ONEZONE_IA`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">fileshare_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ID of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-"
            title="">gateway_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the file gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">guess_<wbr>mime_<wbr>type_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value that enables guessing of the MIME type for uploaded objects based on file extensions. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms_<wbr>encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value if `true` to use Amazon S3 server side encryption with your own AWS KMS key, or `false` to use a key managed by Amazon S3. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms_<wbr>key_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) for KMS key used for Amazon S3 server side encryption. This value can only be set when `kms_encrypted` is true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">location_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the backed storage used for storing file data.
{{% /md %}}</dd>

    <dt class="property-"
            title="">nfs_<wbr>file_<wbr>share_<wbr>defaults<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfsfilesharenfsfilesharedefaults">Dict[Nfs<wbr>File<wbr>Share<wbr>Nfs<wbr>File<wbr>Share<wbr>Defaults]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument with file share default values. More information below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">object_<wbr>acl<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Access Control List permission for S3 bucket objects. Defaults to `private`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">read_<wbr>only<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean to indicate write status of file share. File share does not accept writes if `true`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">requester_<wbr>pays<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean who pays the cost of the request and the data download from the Amazon S3 bucket. Set this value to `true` if you want the requester to pay instead of the bucket owner. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the AWS Identity and Access Management (IAM) role that a file gateway assumes when it accesses the underlying storage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">squash<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Maps a user to anonymous user. Defaults to `RootSquash`. Valid values: `RootSquash` (only root is mapped to anonymous user), `NoSquash` (no one is mapped to anonymous user), `AllSquash` (everyone is mapped to anonymous user)
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing NfsFileShare Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/storagegateway/#NfsFileShareState">NfsFileShareState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/storagegateway/#NfsFileShare">NfsFileShare</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>client_lists=None<span class="p">, </span>default_storage_class=None<span class="p">, </span>fileshare_id=None<span class="p">, </span>gateway_arn=None<span class="p">, </span>guess_mime_type_enabled=None<span class="p">, </span>kms_encrypted=None<span class="p">, </span>kms_key_arn=None<span class="p">, </span>location_arn=None<span class="p">, </span>nfs_file_share_defaults=None<span class="p">, </span>object_acl=None<span class="p">, </span>read_only=None<span class="p">, </span>requester_pays=None<span class="p">, </span>role_arn=None<span class="p">, </span>squash=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetNfsFileShare<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/storagegateway?tab=doc#NfsFileShareState">NfsFileShareState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/storagegateway?tab=doc#NfsFileShare">NfsFileShare</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Storagegateway.NfsFileShare.html">NfsFileShare</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Storagegateway.NfsFileShareState.html">NfsFileShareState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing NfsFileShare resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}Amazon Resource Name (ARN) of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Lists<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of clients that are allowed to access the file gateway. The list must contain either valid IP addresses or valid CIDR blocks. Set to `[&#34;0.0.0.0/0&#34;]` to not limit access. Minimum 1 item. Maximum 100 items.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default storage class for objects put into an Amazon S3 bucket by the file gateway. Defaults to `S3_STANDARD`. Valid values: `S3_STANDARD`, `S3_STANDARD_IA`, `S3_ONEZONE_IA`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Fileshare<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ID of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Gateway<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the file gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Guess<wbr>Mime<wbr>Type<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value that enables guessing of the MIME type for uploaded objects based on file extensions. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value if `true` to use Amazon S3 server side encryption with your own AWS KMS key, or `false` to use a key managed by Amazon S3. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) for KMS key used for Amazon S3 server side encryption. This value can only be set when `kms_encrypted` is true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Location<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the backed storage used for storing file data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Nfs<wbr>File<wbr>Share<wbr>Defaults<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfsfilesharenfsfilesharedefaults">Nfs<wbr>File<wbr>Share<wbr>Nfs<wbr>File<wbr>Share<wbr>Defaults<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument with file share default values. More information below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Access Control List permission for S3 bucket objects. Defaults to `private`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean to indicate write status of file share. File share does not accept writes if `true`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requester<wbr>Pays<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean who pays the cost of the request and the data download from the Amazon S3 bucket. Set this value to `true` if you want the requester to pay instead of the bucket owner. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the AWS Identity and Access Management (IAM) role that a file gateway assumes when it accesses the underlying storage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Squash<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Maps a user to anonymous user. Defaults to `RootSquash`. Valid values: `RootSquash` (only root is mapped to anonymous user), `NoSquash` (no one is mapped to anonymous user), `AllSquash` (everyone is mapped to anonymous user)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Lists<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of clients that are allowed to access the file gateway. The list must contain either valid IP addresses or valid CIDR blocks. Set to `[&#34;0.0.0.0/0&#34;]` to not limit access. Minimum 1 item. Maximum 100 items.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The default storage class for objects put into an Amazon S3 bucket by the file gateway. Defaults to `S3_STANDARD`. Valid values: `S3_STANDARD`, `S3_STANDARD_IA`, `S3_ONEZONE_IA`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Fileshare<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ID of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Gateway<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the file gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Guess<wbr>Mime<wbr>Type<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value that enables guessing of the MIME type for uploaded objects based on file extensions. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value if `true` to use Amazon S3 server side encryption with your own AWS KMS key, or `false` to use a key managed by Amazon S3. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) for KMS key used for Amazon S3 server side encryption. This value can only be set when `kms_encrypted` is true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Location<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the backed storage used for storing file data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Nfs<wbr>File<wbr>Share<wbr>Defaults<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfsfilesharenfsfilesharedefaults">*Nfs<wbr>File<wbr>Share<wbr>Nfs<wbr>File<wbr>Share<wbr>Defaults</a></span>
    </dt>
    <dd>{{% md %}}Nested argument with file share default values. More information below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Acl<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Access Control List permission for S3 bucket objects. Defaults to `private`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean to indicate write status of file share. File share does not accept writes if `true`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requester<wbr>Pays<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean who pays the cost of the request and the data download from the Amazon S3 bucket. Set this value to `true` if you want the requester to pay instead of the bucket owner. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the AWS Identity and Access Management (IAM) role that a file gateway assumes when it accesses the underlying storage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Squash<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Maps a user to anonymous user. Defaults to `RootSquash`. Valid values: `RootSquash` (only root is mapped to anonymous user), `NoSquash` (no one is mapped to anonymous user), `AllSquash` (everyone is mapped to anonymous user)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client<wbr>Lists<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The list of clients that are allowed to access the file gateway. The list must contain either valid IP addresses or valid CIDR blocks. Set to `[&#34;0.0.0.0/0&#34;]` to not limit access. Minimum 1 item. Maximum 100 items.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default storage class for objects put into an Amazon S3 bucket by the file gateway. Defaults to `S3_STANDARD`. Valid values: `S3_STANDARD`, `S3_STANDARD_IA`, `S3_ONEZONE_IA`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">fileshare<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ID of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">gateway<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the file gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">guess<wbr>Mime<wbr>Type<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value that enables guessing of the MIME type for uploaded objects based on file extensions. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value if `true` to use Amazon S3 server side encryption with your own AWS KMS key, or `false` to use a key managed by Amazon S3. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) for KMS key used for Amazon S3 server side encryption. This value can only be set when `kms_encrypted` is true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">location<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the backed storage used for storing file data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">nfs<wbr>File<wbr>Share<wbr>Defaults<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfsfilesharenfsfilesharedefaults">Nfs<wbr>File<wbr>Share<wbr>Nfs<wbr>File<wbr>Share<wbr>Defaults?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument with file share default values. More information below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object<wbr>Acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Access Control List permission for S3 bucket objects. Defaults to `private`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean to indicate write status of file share. File share does not accept writes if `true`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requester<wbr>Pays<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean who pays the cost of the request and the data download from the Amazon S3 bucket. Set this value to `true` if you want the requester to pay instead of the bucket owner. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the AWS Identity and Access Management (IAM) role that a file gateway assumes when it accesses the underlying storage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">squash<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Maps a user to anonymous user. Defaults to `RootSquash`. Valid values: `RootSquash` (only root is mapped to anonymous user), `NoSquash` (no one is mapped to anonymous user), `AllSquash` (everyone is mapped to anonymous user)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client_<wbr>lists<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of clients that are allowed to access the file gateway. The list must contain either valid IP addresses or valid CIDR blocks. Set to `[&#34;0.0.0.0/0&#34;]` to not limit access. Minimum 1 item. Maximum 100 items.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>storage_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The default storage class for objects put into an Amazon S3 bucket by the file gateway. Defaults to `S3_STANDARD`. Valid values: `S3_STANDARD`, `S3_STANDARD_IA`, `S3_ONEZONE_IA`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">fileshare_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ID of the NFS File Share.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">gateway_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the file gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">guess_<wbr>mime_<wbr>type_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value that enables guessing of the MIME type for uploaded objects based on file extensions. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value if `true` to use Amazon S3 server side encryption with your own AWS KMS key, or `false` to use a key managed by Amazon S3. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) for KMS key used for Amazon S3 server side encryption. This value can only be set when `kms_encrypted` is true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">location_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the backed storage used for storing file data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">nfs_<wbr>file_<wbr>share_<wbr>defaults<span class="property-indicator"></span>
        <span class="property-type"><a href="#nfsfilesharenfsfilesharedefaults">Dict[Nfs<wbr>File<wbr>Share<wbr>Nfs<wbr>File<wbr>Share<wbr>Defaults]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument with file share default values. More information below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object_<wbr>acl<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Access Control List permission for S3 bucket objects. Defaults to `private`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read_<wbr>only<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean to indicate write status of file share. File share does not accept writes if `true`. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requester_<wbr>pays<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean who pays the cost of the request and the data download from the Amazon S3 bucket. Set this value to `true` if you want the requester to pay instead of the bucket owner. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the AWS Identity and Access Management (IAM) role that a file gateway assumes when it accesses the underlying storage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">squash<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Maps a user to anonymous user. Defaults to `RootSquash`. Valid values: `RootSquash` (only root is mapped to anonymous user), `NoSquash` (no one is mapped to anonymous user), `AllSquash` (everyone is mapped to anonymous user)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### NfsFileShareNfsFileShareDefaults
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#NfsFileShareNfsFileShareDefaults">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#NfsFileShareNfsFileShareDefaults">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/storagegateway?tab=doc#NfsFileShareNfsFileShareDefaultsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/storagegateway?tab=doc#NfsFileShareNfsFileShareDefaultsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Storagegateway.NfsFileShareNfsFileShareDefaultsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Storagegateway.NfsFileShareNfsFileShareDefaults.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Directory<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Unix directory mode in the string form &#34;nnnn&#34;. Defaults to `&#34;0777&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">File<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Unix file mode in the string form &#34;nnnn&#34;. Defaults to `&#34;0666&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The default group ID for the file share (unless the files have another group ID specified). Defaults to `65534` (`nfsnobody`). Valid values: `0` through `4294967294`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The default owner ID for the file share (unless the files have another owner ID specified). Defaults to `65534` (`nfsnobody`). Valid values: `0` through `4294967294`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Directory<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Unix directory mode in the string form &#34;nnnn&#34;. Defaults to `&#34;0777&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">File<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Unix file mode in the string form &#34;nnnn&#34;. Defaults to `&#34;0666&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The default group ID for the file share (unless the files have another group ID specified). Defaults to `65534` (`nfsnobody`). Valid values: `0` through `4294967294`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The default owner ID for the file share (unless the files have another owner ID specified). Defaults to `65534` (`nfsnobody`). Valid values: `0` through `4294967294`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">directory<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Unix directory mode in the string form &#34;nnnn&#34;. Defaults to `&#34;0777&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">file<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Unix file mode in the string form &#34;nnnn&#34;. Defaults to `&#34;0666&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The default group ID for the file share (unless the files have another group ID specified). Defaults to `65534` (`nfsnobody`). Valid values: `0` through `4294967294`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The default owner ID for the file share (unless the files have another owner ID specified). Defaults to `65534` (`nfsnobody`). Valid values: `0` through `4294967294`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">directory<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Unix directory mode in the string form &#34;nnnn&#34;. Defaults to `&#34;0777&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">file<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Unix file mode in the string form &#34;nnnn&#34;. Defaults to `&#34;0666&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The default group ID for the file share (unless the files have another group ID specified). Defaults to `65534` (`nfsnobody`). Valid values: `0` through `4294967294`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The default owner ID for the file share (unless the files have another owner ID specified). Defaults to `65534` (`nfsnobody`). Valid values: `0` through `4294967294`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}









---
title: "BucketObject"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Creates a new object inside an existing bucket in Google cloud storage service (GCS). 
[ACLs](https://cloud.google.com/storage/docs/access-control/lists) can be applied using the `gcp.storage.ObjectACL` resource.
 For more information see 
[the official documentation](https://cloud.google.com/storage/docs/key-terms#objects) 
and 
[API](https://cloud.google.com/storage/docs/json_api/v1/objects).


## Example Usage

Example creating a public object in an existing `image-store` bucket.

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const picture = new gcp.storage.BucketObject("picture", {
    bucket: "image-store",
    source: new pulumi.asset.FileAsset("/images/nature/garden-tiger-moth.jpg"),
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/storage_bucket_object.html.markdown.



## Create a BucketObject Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#BucketObject">BucketObject</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#BucketObjectArgs">BucketObjectArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">BucketObject</span><span class="p">(resource_name, opts=None, </span>bucket=None<span class="p">, </span>cache_control=None<span class="p">, </span>content=None<span class="p">, </span>content_disposition=None<span class="p">, </span>content_encoding=None<span class="p">, </span>content_language=None<span class="p">, </span>content_type=None<span class="p">, </span>detect_md5hash=None<span class="p">, </span>metadata=None<span class="p">, </span>name=None<span class="p">, </span>source=None<span class="p">, </span>storage_class=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewBucketObject<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketObjectArgs">BucketObjectArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketObject">BucketObject</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketObject.html">BucketObject</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketObjectArgs.html">BucketObjectArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a BucketObject resource with the given unique name, arguments, and options.

{{% lang nodejs %}}

<ul class="pl-10">
    <li><strong>name</strong> &ndash; (Required) The unique name of the resulting resource.</li>
    <li><strong>args</strong> &ndash;  (Optional)  The arguments to use to populate this resource's properties.</li>
    <li><strong>opts</strong> &ndash; (Optional) A bag of options that control this resource's behavior.</li>
</ul>

{{% /lang %}}

{{% lang go %}}

<ul class="pl-10">
    <li><strong>name</strong> &ndash; (Required) The unique name of the resulting resource.</li>
    <li><strong>args</strong> &ndash;  (Optional)  The arguments to use to populate this resource's properties.</li>
    <li><strong>opts</strong> &ndash; (Optional) A bag of options that control this resource's behavior.</li>
</ul>

{{% /lang %}}

{{% lang csharp %}}

<ul class="pl-10">
    <li><strong>name</strong> &ndash; (Required) The unique name of the resulting resource.</li>
    <li><strong>args</strong> &ndash;  (Optional)  The arguments to use to populate this resource's properties.</li>
    <li><strong>opts</strong> &ndash; (Optional) A bag of options that control this resource's behavior.</li>
</ul>

{{% /lang %}}

The following arguments are supported:


{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the containing bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cache<wbr>Control</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Disposition</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Encoding</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Language</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to &#34;application/octet-stream&#34; or &#34;text/plain; charset=utf-8&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Detect<wbr>Md5hash</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-provided metadata, in key/value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the object. If you&#39;re interpolating the name of this object, see `output_name` instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source</td>
            <td class="align-top">
                
                <code>AssetOrArchive?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A path to the data you want to upload. Must be defined
if `content` is not.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Class</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket&#39;s default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the containing bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cache<wbr>Control</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Disposition</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Encoding</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Language</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to &#34;application/octet-stream&#34; or &#34;text/plain; charset=utf-8&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Detect<wbr>Md5hash</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-provided metadata, in key/value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the object. If you&#39;re interpolating the name of this object, see `output_name` instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source</td>
            <td class="align-top">
                
                <code>pulumi.AssetOrArchive</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A path to the data you want to upload. Must be defined
if `content` is not.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Class</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket&#39;s default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the containing bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cache<wbr>Control</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content<wbr>Disposition</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content<wbr>Encoding</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content<wbr>Language</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to &#34;application/octet-stream&#34; or &#34;text/plain; charset=utf-8&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">detect<wbr>Md5hash</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-provided metadata, in key/value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the object. If you&#39;re interpolating the name of this object, see `output_name` instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source</td>
            <td class="align-top">
                
                <code>pulumi.asset.Asset | pulumi.asset.Archive?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A path to the data you want to upload. Must be defined
if `content` is not.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Class</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket&#39;s default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">bucket</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the containing bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cache_<wbr>control</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content_<wbr>disposition</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content_<wbr>encoding</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content_<wbr>language</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to &#34;application/octet-stream&#34; or &#34;text/plain; charset=utf-8&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">detect_<wbr>md5hash</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-provided metadata, in key/value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the object. If you&#39;re interpolating the name of this object, see `output_name` instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source</td>
            <td class="align-top">
                
                <code>Union[pulumi.Asset, pulumi.Archive]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A path to the data you want to upload. Must be defined
if `content` is not.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage_<wbr>class</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket&#39;s default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## BucketObject Output Properties

The following output properties are available:



{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the containing bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cache<wbr>Control</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} [Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Disposition</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Encoding</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Language</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to &#34;application/octet-stream&#34; or &#34;text/plain; charset=utf-8&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Crc32c</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) Base 64 CRC32 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Detect<wbr>Md5hash</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Md5hash</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) Base 64 MD5 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} User-provided metadata, in key/value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the object. If you&#39;re interpolating the name of this object, see `output_name` instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Output<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) A url reference to this object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source</td>
            <td class="align-top">
                
                <code>AssetOrArchive?</code>
            </td>
            <td class="align-top">{{% md %}} A path to the data you want to upload. Must be defined
if `content` is not.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Class</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket&#39;s default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the containing bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cache<wbr>Control</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} [Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Disposition</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Encoding</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Language</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to &#34;application/octet-stream&#34; or &#34;text/plain; charset=utf-8&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Crc32c</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) Base 64 CRC32 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Detect<wbr>Md5hash</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Md5hash</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) Base 64 MD5 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} User-provided metadata, in key/value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the object. If you&#39;re interpolating the name of this object, see `output_name` instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Output<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) A url reference to this object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source</td>
            <td class="align-top">
                
                <code>pulumi.AssetOrArchive</code>
            </td>
            <td class="align-top">{{% md %}} A path to the data you want to upload. Must be defined
if `content` is not.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Class</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket&#39;s default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the containing bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cache<wbr>Control</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} [Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content<wbr>Disposition</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content<wbr>Encoding</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content<wbr>Language</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to &#34;application/octet-stream&#34; or &#34;text/plain; charset=utf-8&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">crc32c</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) Base 64 CRC32 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">detect<wbr>Md5hash</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">md5hash</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) Base 64 MD5 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} User-provided metadata, in key/value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the object. If you&#39;re interpolating the name of this object, see `output_name` instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">output<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) A url reference to this object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source</td>
            <td class="align-top">
                
                <code>pulumi.asset.Asset | pulumi.asset.Archive?</code>
            </td>
            <td class="align-top">{{% md %}} A path to the data you want to upload. Must be defined
if `content` is not.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Class</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket&#39;s default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">bucket</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the containing bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cache_<wbr>control</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} [Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content_<wbr>disposition</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content_<wbr>encoding</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content_<wbr>language</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} [Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to &#34;application/octet-stream&#34; or &#34;text/plain; charset=utf-8&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">crc32c</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) Base 64 CRC32 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">detect_<wbr>md5hash</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">md5hash</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) Base 64 MD5 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} User-provided metadata, in key/value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the object. If you&#39;re interpolating the name of this object, see `output_name` instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">output_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self_<wbr>link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) A url reference to this object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source</td>
            <td class="align-top">
                
                <code>Union[pulumi.Asset, pulumi.Archive]</code>
            </td>
            <td class="align-top">{{% md %}} A path to the data you want to upload. Must be defined
if `content` is not.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage_<wbr>class</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket&#39;s default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing BucketObject Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#BucketObjectState">BucketObjectState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#BucketObject">BucketObject</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>bucket=None<span class="p">, </span>cache_control=None<span class="p">, </span>content=None<span class="p">, </span>content_disposition=None<span class="p">, </span>content_encoding=None<span class="p">, </span>content_language=None<span class="p">, </span>content_type=None<span class="p">, </span>crc32c=None<span class="p">, </span>detect_md5hash=None<span class="p">, </span>md5hash=None<span class="p">, </span>metadata=None<span class="p">, </span>name=None<span class="p">, </span>output_name=None<span class="p">, </span>self_link=None<span class="p">, </span>source=None<span class="p">, </span>storage_class=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetBucketObject<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketObjectState">BucketObjectState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketObject">BucketObject</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketObject.html">BucketObject</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketObjectState.html">BucketObjectState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing BucketObject resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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


{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Bucket</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the containing bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cache<wbr>Control</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Disposition</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Encoding</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Language</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to &#34;application/octet-stream&#34; or &#34;text/plain; charset=utf-8&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Crc32c</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) Base 64 CRC32 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Detect<wbr>Md5hash</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Md5hash</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) Base 64 MD5 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-provided metadata, in key/value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the object. If you&#39;re interpolating the name of this object, see `output_name` instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Output<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) A url reference to this object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source</td>
            <td class="align-top">
                
                <code>AssetOrArchive?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A path to the data you want to upload. Must be defined
if `content` is not.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Class</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket&#39;s default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Bucket</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the containing bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cache<wbr>Control</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Disposition</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Encoding</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Language</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Content<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to &#34;application/octet-stream&#34; or &#34;text/plain; charset=utf-8&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Crc32c</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) Base 64 CRC32 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Detect<wbr>Md5hash</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Md5hash</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) Base 64 MD5 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-provided metadata, in key/value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the object. If you&#39;re interpolating the name of this object, see `output_name` instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Output<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) A url reference to this object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source</td>
            <td class="align-top">
                
                <code>pulumi.AssetOrArchive</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A path to the data you want to upload. Must be defined
if `content` is not.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Class</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket&#39;s default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">bucket</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the containing bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cache<wbr>Control</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content<wbr>Disposition</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content<wbr>Encoding</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content<wbr>Language</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to &#34;application/octet-stream&#34; or &#34;text/plain; charset=utf-8&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">crc32c</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) Base 64 CRC32 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">detect<wbr>Md5hash</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">md5hash</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) Base 64 MD5 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-provided metadata, in key/value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the object. If you&#39;re interpolating the name of this object, see `output_name` instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">output<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) A url reference to this object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source</td>
            <td class="align-top">
                
                <code>pulumi.asset.Asset | pulumi.asset.Archive?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A path to the data you want to upload. Must be defined
if `content` is not.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Class</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket&#39;s default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">bucket</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the containing bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cache_<wbr>control</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Cache-Control](https://tools.ietf.org/html/rfc7234#section-5.2)
directive to specify caching behavior of object data. If omitted and object is accessible to all anonymous users, the default will be public, max-age=3600
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data as `string` to be uploaded. Must be defined if `source` is not. **Note**: The `content` field is marked as sensitive.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content_<wbr>disposition</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Disposition](https://tools.ietf.org/html/rfc6266) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content_<wbr>encoding</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Encoding](https://tools.ietf.org/html/rfc7231#section-3.1.2.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content_<wbr>language</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Language](https://tools.ietf.org/html/rfc7231#section-3.1.3.2) of the object data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">content_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Content-Type](https://tools.ietf.org/html/rfc7231#section-3.1.1.5) of the object data. Defaults to &#34;application/octet-stream&#34; or &#34;text/plain; charset=utf-8&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">crc32c</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) Base 64 CRC32 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">detect_<wbr>md5hash</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">md5hash</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) Base 64 MD5 hash of the uploaded data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-provided metadata, in key/value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the object. If you&#39;re interpolating the name of this object, see `output_name` instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">output_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) The name of the object. Use this field in interpolations with `gcp.storage.ObjectACL` to recreate
`gcp.storage.ObjectACL` resources when your `gcp.storage.BucketObject` is recreated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self_<wbr>link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) A url reference to this object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source</td>
            <td class="align-top">
                
                <code>Union[pulumi.Asset, pulumi.Archive]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A path to the data you want to upload. Must be defined
if `content` is not.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage_<wbr>class</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [StorageClass](https://cloud.google.com/storage/docs/storage-classes) of the new bucket object.
Supported values include: `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`. If not provided, this defaults to the bucket&#39;s default
storage class or to a [standard](https://cloud.google.com/storage/docs/storage-classes#standard) class.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










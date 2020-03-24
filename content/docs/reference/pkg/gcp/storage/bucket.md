
---
title: "Bucket"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Creates a new bucket in Google cloud storage service (GCS).
Once a bucket has been created, its location can't be changed.
[ACLs](https://cloud.google.com/storage/docs/access-control/lists) can be applied
using the [`gcp.storage.BucketACL`](https://www.terraform.io/docs/providers/google/r/storage_bucket_acl.html) resource.

For more information see
[the official documentation](https://cloud.google.com/storage/docs/overview)
and
[API](https://cloud.google.com/storage/docs/json_api/v1/buckets).

**Note**: If the project id is not set on the resource or in the provider block it will be dynamically
determined which will require enabling the compute api.


## Example Usage - creating a private bucket in standard storage, in the EU region. Bucket configured as static website and CORS configurations

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const static_site = new gcp.storage.Bucket("static-site", {
    bucketPolicyOnly: true,
    cors: [{
        maxAgeSeconds: 3600,
        methods: [
            "GET",
            "HEAD",
            "PUT",
            "POST",
            "DELETE",
        ],
        origins: ["http://image-store.com"],
        responseHeaders: ["*"],
    }],
    forceDestroy: true,
    location: "EU",
    website: {
        mainPageSuffix: "index.html",
        notFoundPage: "404.html",
    },
});
```

## Example Usage - Life cycle settings for storage bucket objects

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const auto_expire = new gcp.storage.Bucket("auto-expire", {
    forceDestroy: true,
    lifecycleRules: [{
        action: {
            type: "Delete",
        },
        condition: {
            age: 3,
        },
    }],
    location: "US",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/storage_bucket.html.markdown.



## Create a Bucket Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#Bucket">Bucket</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#BucketArgs">BucketArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Bucket</span><span class="p">(resource_name, opts=None, </span>bucket_policy_only=None<span class="p">, </span>cors=None<span class="p">, </span>default_event_based_hold=None<span class="p">, </span>encryption=None<span class="p">, </span>force_destroy=None<span class="p">, </span>labels=None<span class="p">, </span>lifecycle_rules=None<span class="p">, </span>location=None<span class="p">, </span>logging=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>requester_pays=None<span class="p">, </span>retention_policy=None<span class="p">, </span>storage_class=None<span class="p">, </span>versioning=None<span class="p">, </span>website=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewBucket<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketArgs">BucketArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#Bucket">Bucket</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.Bucket.html">Bucket</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketArgs.html">BucketArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Bucket resource with the given unique name, arguments, and options.

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
            <td class="align-top">Bucket<wbr>Policy<wbr>Only</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Bucket Policy Only](https://cloud.google.com/storage/docs/bucket-policy-only) access to a bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cors</td>
            <td class="align-top">
                
                <code><a href="#bucketcor">List&lt;Bucket<wbr>Cor<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Cross-Origin Resource Sharing (CORS)](https://www.w3.org/TR/cors/) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Event<wbr>Based<wbr>Hold</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Encryption</td>
            <td class="align-top">
                
                <code><a href="#bucketencryption">Bucket<wbr>Encryption<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s encryption configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Force<wbr>Destroy</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When deleting a bucket, this
boolean option will delete all contained objects. If you try to delete a
bucket that contains objects, the provider will fail that run.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Lifecycle<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerule">List&lt;Bucket<wbr>Lifecycle<wbr>Rule<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Lifecycle Rules](https://cloud.google.com/storage/docs/lifecycle#configuration) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [GCS location](https://cloud.google.com/storage/docs/bucket-locations)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logging</td>
            <td class="align-top">
                
                <code><a href="#bucketlogging">Bucket<wbr>Logging<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Access &amp; Storage Logs](https://cloud.google.com/storage/docs/access-logs) configuration.
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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Requester<wbr>Pays</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Requester Pays](https://cloud.google.com/storage/docs/requester-pays) on a storage bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retention<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#bucketretentionpolicy">Bucket<wbr>Retention<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of the bucket&#39;s data retention policy for how long objects in the bucket should be retained. Structure is documented below.
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
The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Versioning</td>
            <td class="align-top">
                
                <code><a href="#bucketversioning">Bucket<wbr>Versioning<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Versioning](https://cloud.google.com/storage/docs/object-versioning) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Website</td>
            <td class="align-top">
                
                <code><a href="#bucketwebsite">Bucket<wbr>Website<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration if the bucket acts as a website. Structure is documented below.
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
            <td class="align-top">Bucket<wbr>Policy<wbr>Only</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Bucket Policy Only](https://cloud.google.com/storage/docs/bucket-policy-only) access to a bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cors</td>
            <td class="align-top">
                
                <code><a href="#bucketcor">[]Bucket<wbr>Cor</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Cross-Origin Resource Sharing (CORS)](https://www.w3.org/TR/cors/) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Event<wbr>Based<wbr>Hold</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Encryption</td>
            <td class="align-top">
                
                <code><a href="#bucketencryption">*Bucket<wbr>Encryption</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s encryption configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Force<wbr>Destroy</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When deleting a bucket, this
boolean option will delete all contained objects. If you try to delete a
bucket that contains objects, the provider will fail that run.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Lifecycle<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerule">[]Bucket<wbr>Lifecycle<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Lifecycle Rules](https://cloud.google.com/storage/docs/lifecycle#configuration) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [GCS location](https://cloud.google.com/storage/docs/bucket-locations)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logging</td>
            <td class="align-top">
                
                <code><a href="#bucketlogging">*Bucket<wbr>Logging</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Access &amp; Storage Logs](https://cloud.google.com/storage/docs/access-logs) configuration.
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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Requester<wbr>Pays</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Requester Pays](https://cloud.google.com/storage/docs/requester-pays) on a storage bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retention<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#bucketretentionpolicy">*Bucket<wbr>Retention<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of the bucket&#39;s data retention policy for how long objects in the bucket should be retained. Structure is documented below.
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
The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Versioning</td>
            <td class="align-top">
                
                <code><a href="#bucketversioning">*Bucket<wbr>Versioning</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Versioning](https://cloud.google.com/storage/docs/object-versioning) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Website</td>
            <td class="align-top">
                
                <code><a href="#bucketwebsite">*Bucket<wbr>Website</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration if the bucket acts as a website. Structure is documented below.
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
            <td class="align-top">bucket<wbr>Policy<wbr>Only</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Bucket Policy Only](https://cloud.google.com/storage/docs/bucket-policy-only) access to a bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cors</td>
            <td class="align-top">
                
                <code><a href="#bucketcor">Bucket<wbr>Cor[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Cross-Origin Resource Sharing (CORS)](https://www.w3.org/TR/cors/) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Event<wbr>Based<wbr>Hold</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">encryption</td>
            <td class="align-top">
                
                <code><a href="#bucketencryption">Bucket<wbr>Encryption?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s encryption configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">force<wbr>Destroy</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When deleting a bucket, this
boolean option will delete all contained objects. If you try to delete a
bucket that contains objects, the provider will fail that run.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">lifecycle<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerule">Bucket<wbr>Lifecycle<wbr>Rule[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Lifecycle Rules](https://cloud.google.com/storage/docs/lifecycle#configuration) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [GCS location](https://cloud.google.com/storage/docs/bucket-locations)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logging</td>
            <td class="align-top">
                
                <code><a href="#bucketlogging">Bucket<wbr>Logging?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Access &amp; Storage Logs](https://cloud.google.com/storage/docs/access-logs) configuration.
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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">requester<wbr>Pays</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Requester Pays](https://cloud.google.com/storage/docs/requester-pays) on a storage bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retention<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#bucketretentionpolicy">Bucket<wbr>Retention<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of the bucket&#39;s data retention policy for how long objects in the bucket should be retained. Structure is documented below.
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
The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">versioning</td>
            <td class="align-top">
                
                <code><a href="#bucketversioning">Bucket<wbr>Versioning?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Versioning](https://cloud.google.com/storage/docs/object-versioning) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">website</td>
            <td class="align-top">
                
                <code><a href="#bucketwebsite">Bucket<wbr>Website?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration if the bucket acts as a website. Structure is documented below.
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
            <td class="align-top">bucket_<wbr>policy_<wbr>only</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Bucket Policy Only](https://cloud.google.com/storage/docs/bucket-policy-only) access to a bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cors</td>
            <td class="align-top">
                
                <code><a href="#bucketcor">List[Bucket<wbr>Cor]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Cross-Origin Resource Sharing (CORS)](https://www.w3.org/TR/cors/) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>event_<wbr>based_<wbr>hold</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">encryption</td>
            <td class="align-top">
                
                <code><a href="#bucketencryption">Dict[Bucket<wbr>Encryption]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s encryption configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">force_<wbr>destroy</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When deleting a bucket, this
boolean option will delete all contained objects. If you try to delete a
bucket that contains objects, the provider will fail that run.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">lifecycle_<wbr>rules</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerule">List[Bucket<wbr>Lifecycle<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Lifecycle Rules](https://cloud.google.com/storage/docs/lifecycle#configuration) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [GCS location](https://cloud.google.com/storage/docs/bucket-locations)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logging</td>
            <td class="align-top">
                
                <code><a href="#bucketlogging">Dict[Bucket<wbr>Logging]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Access &amp; Storage Logs](https://cloud.google.com/storage/docs/access-logs) configuration.
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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">requester_<wbr>pays</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Requester Pays](https://cloud.google.com/storage/docs/requester-pays) on a storage bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retention_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#bucketretentionpolicy">Dict[Bucket<wbr>Retention<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of the bucket&#39;s data retention policy for how long objects in the bucket should be retained. Structure is documented below.
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
The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">versioning</td>
            <td class="align-top">
                
                <code><a href="#bucketversioning">Dict[Bucket<wbr>Versioning]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Versioning](https://cloud.google.com/storage/docs/object-versioning) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">website</td>
            <td class="align-top">
                
                <code><a href="#bucketwebsite">Dict[Bucket<wbr>Website]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration if the bucket acts as a website. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Bucket Output Properties

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
            <td class="align-top">Bucket<wbr>Policy<wbr>Only</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Enables [Bucket Policy Only](https://cloud.google.com/storage/docs/bucket-policy-only) access to a bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cors</td>
            <td class="align-top">
                
                <code><a href="#bucketcor">List&lt;Bucket<wbr>Cor&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Cross-Origin Resource Sharing (CORS)](https://www.w3.org/TR/cors/) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Event<wbr>Based<wbr>Hold</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Encryption</td>
            <td class="align-top">
                
                <code><a href="#bucketencryption">Bucket<wbr>Encryption?</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s encryption configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Force<wbr>Destroy</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} When deleting a bucket, this
boolean option will delete all contained objects. If you try to delete a
bucket that contains objects, the provider will fail that run.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Lifecycle<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerule">List&lt;Bucket<wbr>Lifecycle<wbr>Rule&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Lifecycle Rules](https://cloud.google.com/storage/docs/lifecycle#configuration) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The [GCS location](https://cloud.google.com/storage/docs/bucket-locations)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logging</td>
            <td class="align-top">
                
                <code><a href="#bucketlogging">Bucket<wbr>Logging?</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Access &amp; Storage Logs](https://cloud.google.com/storage/docs/access-logs) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Requester<wbr>Pays</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Enables [Requester Pays](https://cloud.google.com/storage/docs/requester-pays) on a storage bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retention<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#bucketretentionpolicy">Bucket<wbr>Retention<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration of the bucket&#39;s data retention policy for how long objects in the bucket should be retained. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Class</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The base URL of the bucket, in the format `gs://&lt;bucket-name&gt;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Versioning</td>
            <td class="align-top">
                
                <code><a href="#bucketversioning">Bucket<wbr>Versioning?</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Versioning](https://cloud.google.com/storage/docs/object-versioning) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Website</td>
            <td class="align-top">
                
                <code><a href="#bucketwebsite">Bucket<wbr>Website?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration if the bucket acts as a website. Structure is documented below.
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
            <td class="align-top">Bucket<wbr>Policy<wbr>Only</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Enables [Bucket Policy Only](https://cloud.google.com/storage/docs/bucket-policy-only) access to a bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cors</td>
            <td class="align-top">
                
                <code><a href="#bucketcor">[]Bucket<wbr>Cor</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Cross-Origin Resource Sharing (CORS)](https://www.w3.org/TR/cors/) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Event<wbr>Based<wbr>Hold</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Encryption</td>
            <td class="align-top">
                
                <code><a href="#bucketencryption">*Bucket<wbr>Encryption</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s encryption configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Force<wbr>Destroy</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} When deleting a bucket, this
boolean option will delete all contained objects. If you try to delete a
bucket that contains objects, the provider will fail that run.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Lifecycle<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerule">[]Bucket<wbr>Lifecycle<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Lifecycle Rules](https://cloud.google.com/storage/docs/lifecycle#configuration) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The [GCS location](https://cloud.google.com/storage/docs/bucket-locations)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logging</td>
            <td class="align-top">
                
                <code><a href="#bucketlogging">*Bucket<wbr>Logging</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Access &amp; Storage Logs](https://cloud.google.com/storage/docs/access-logs) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Requester<wbr>Pays</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Enables [Requester Pays](https://cloud.google.com/storage/docs/requester-pays) on a storage bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retention<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#bucketretentionpolicy">*Bucket<wbr>Retention<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration of the bucket&#39;s data retention policy for how long objects in the bucket should be retained. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Class</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The base URL of the bucket, in the format `gs://&lt;bucket-name&gt;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Versioning</td>
            <td class="align-top">
                
                <code><a href="#bucketversioning">*Bucket<wbr>Versioning</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Versioning](https://cloud.google.com/storage/docs/object-versioning) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Website</td>
            <td class="align-top">
                
                <code><a href="#bucketwebsite">*Bucket<wbr>Website</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration if the bucket acts as a website. Structure is documented below.
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
            <td class="align-top">bucket<wbr>Policy<wbr>Only</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} Enables [Bucket Policy Only](https://cloud.google.com/storage/docs/bucket-policy-only) access to a bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cors</td>
            <td class="align-top">
                
                <code><a href="#bucketcor">Bucket<wbr>Cor[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Cross-Origin Resource Sharing (CORS)](https://www.w3.org/TR/cors/) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Event<wbr>Based<wbr>Hold</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">encryption</td>
            <td class="align-top">
                
                <code><a href="#bucketencryption">Bucket<wbr>Encryption?</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s encryption configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">force<wbr>Destroy</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} When deleting a bucket, this
boolean option will delete all contained objects. If you try to delete a
bucket that contains objects, the provider will fail that run.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">lifecycle<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerule">Bucket<wbr>Lifecycle<wbr>Rule[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Lifecycle Rules](https://cloud.google.com/storage/docs/lifecycle#configuration) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The [GCS location](https://cloud.google.com/storage/docs/bucket-locations)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logging</td>
            <td class="align-top">
                
                <code><a href="#bucketlogging">Bucket<wbr>Logging?</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Access &amp; Storage Logs](https://cloud.google.com/storage/docs/access-logs) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">requester<wbr>Pays</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Enables [Requester Pays](https://cloud.google.com/storage/docs/requester-pays) on a storage bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retention<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#bucketretentionpolicy">Bucket<wbr>Retention<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration of the bucket&#39;s data retention policy for how long objects in the bucket should be retained. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Class</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The base URL of the bucket, in the format `gs://&lt;bucket-name&gt;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">versioning</td>
            <td class="align-top">
                
                <code><a href="#bucketversioning">Bucket<wbr>Versioning?</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Versioning](https://cloud.google.com/storage/docs/object-versioning) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">website</td>
            <td class="align-top">
                
                <code><a href="#bucketwebsite">Bucket<wbr>Website?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration if the bucket acts as a website. Structure is documented below.
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
            <td class="align-top">bucket_<wbr>policy_<wbr>only</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Enables [Bucket Policy Only](https://cloud.google.com/storage/docs/bucket-policy-only) access to a bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cors</td>
            <td class="align-top">
                
                <code><a href="#bucketcor">List[Bucket<wbr>Cor]</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Cross-Origin Resource Sharing (CORS)](https://www.w3.org/TR/cors/) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>event_<wbr>based_<wbr>hold</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">encryption</td>
            <td class="align-top">
                
                <code><a href="#bucketencryption">Dict[Bucket<wbr>Encryption]</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s encryption configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">force_<wbr>destroy</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} When deleting a bucket, this
boolean option will delete all contained objects. If you try to delete a
bucket that contains objects, the provider will fail that run.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">lifecycle_<wbr>rules</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerule">List[Bucket<wbr>Lifecycle<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Lifecycle Rules](https://cloud.google.com/storage/docs/lifecycle#configuration) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The [GCS location](https://cloud.google.com/storage/docs/bucket-locations)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logging</td>
            <td class="align-top">
                
                <code><a href="#bucketlogging">Dict[Bucket<wbr>Logging]</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Access &amp; Storage Logs](https://cloud.google.com/storage/docs/access-logs) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">requester_<wbr>pays</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Enables [Requester Pays](https://cloud.google.com/storage/docs/requester-pays) on a storage bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retention_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#bucketretentionpolicy">Dict[Bucket<wbr>Retention<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration of the bucket&#39;s data retention policy for how long objects in the bucket should be retained. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self_<wbr>link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage_<wbr>class</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The base URL of the bucket, in the format `gs://&lt;bucket-name&gt;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">versioning</td>
            <td class="align-top">
                
                <code><a href="#bucketversioning">Dict[Bucket<wbr>Versioning]</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucket&#39;s [Versioning](https://cloud.google.com/storage/docs/object-versioning) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">website</td>
            <td class="align-top">
                
                <code><a href="#bucketwebsite">Dict[Bucket<wbr>Website]</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration if the bucket acts as a website. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Bucket Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#BucketState">BucketState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#Bucket">Bucket</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>bucket_policy_only=None<span class="p">, </span>cors=None<span class="p">, </span>default_event_based_hold=None<span class="p">, </span>encryption=None<span class="p">, </span>force_destroy=None<span class="p">, </span>labels=None<span class="p">, </span>lifecycle_rules=None<span class="p">, </span>location=None<span class="p">, </span>logging=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>requester_pays=None<span class="p">, </span>retention_policy=None<span class="p">, </span>self_link=None<span class="p">, </span>storage_class=None<span class="p">, </span>url=None<span class="p">, </span>versioning=None<span class="p">, </span>website=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetBucket<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketState">BucketState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#Bucket">Bucket</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.Bucket.html">Bucket</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketState.html">BucketState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Bucket resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Bucket<wbr>Policy<wbr>Only</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Bucket Policy Only](https://cloud.google.com/storage/docs/bucket-policy-only) access to a bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cors</td>
            <td class="align-top">
                
                <code><a href="#bucketcor">List&lt;Bucket<wbr>Cor<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Cross-Origin Resource Sharing (CORS)](https://www.w3.org/TR/cors/) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Event<wbr>Based<wbr>Hold</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Encryption</td>
            <td class="align-top">
                
                <code><a href="#bucketencryption">Bucket<wbr>Encryption<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s encryption configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Force<wbr>Destroy</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When deleting a bucket, this
boolean option will delete all contained objects. If you try to delete a
bucket that contains objects, the provider will fail that run.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Lifecycle<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerule">List&lt;Bucket<wbr>Lifecycle<wbr>Rule<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Lifecycle Rules](https://cloud.google.com/storage/docs/lifecycle#configuration) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [GCS location](https://cloud.google.com/storage/docs/bucket-locations)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logging</td>
            <td class="align-top">
                
                <code><a href="#bucketlogging">Bucket<wbr>Logging<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Access &amp; Storage Logs](https://cloud.google.com/storage/docs/access-logs) configuration.
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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Requester<wbr>Pays</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Requester Pays](https://cloud.google.com/storage/docs/requester-pays) on a storage bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retention<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#bucketretentionpolicy">Bucket<wbr>Retention<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of the bucket&#39;s data retention policy for how long objects in the bucket should be retained. Structure is documented below.
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
The URI of the created resource.
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
The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The base URL of the bucket, in the format `gs://&lt;bucket-name&gt;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Versioning</td>
            <td class="align-top">
                
                <code><a href="#bucketversioning">Bucket<wbr>Versioning<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Versioning](https://cloud.google.com/storage/docs/object-versioning) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Website</td>
            <td class="align-top">
                
                <code><a href="#bucketwebsite">Bucket<wbr>Website<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration if the bucket acts as a website. Structure is documented below.
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
            <td class="align-top">Bucket<wbr>Policy<wbr>Only</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Bucket Policy Only](https://cloud.google.com/storage/docs/bucket-policy-only) access to a bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cors</td>
            <td class="align-top">
                
                <code><a href="#bucketcor">[]Bucket<wbr>Cor</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Cross-Origin Resource Sharing (CORS)](https://www.w3.org/TR/cors/) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Event<wbr>Based<wbr>Hold</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Encryption</td>
            <td class="align-top">
                
                <code><a href="#bucketencryption">*Bucket<wbr>Encryption</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s encryption configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Force<wbr>Destroy</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When deleting a bucket, this
boolean option will delete all contained objects. If you try to delete a
bucket that contains objects, the provider will fail that run.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Lifecycle<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerule">[]Bucket<wbr>Lifecycle<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Lifecycle Rules](https://cloud.google.com/storage/docs/lifecycle#configuration) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [GCS location](https://cloud.google.com/storage/docs/bucket-locations)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logging</td>
            <td class="align-top">
                
                <code><a href="#bucketlogging">*Bucket<wbr>Logging</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Access &amp; Storage Logs](https://cloud.google.com/storage/docs/access-logs) configuration.
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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Requester<wbr>Pays</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Requester Pays](https://cloud.google.com/storage/docs/requester-pays) on a storage bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retention<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#bucketretentionpolicy">*Bucket<wbr>Retention<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of the bucket&#39;s data retention policy for how long objects in the bucket should be retained. Structure is documented below.
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
The URI of the created resource.
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
The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The base URL of the bucket, in the format `gs://&lt;bucket-name&gt;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Versioning</td>
            <td class="align-top">
                
                <code><a href="#bucketversioning">*Bucket<wbr>Versioning</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Versioning](https://cloud.google.com/storage/docs/object-versioning) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Website</td>
            <td class="align-top">
                
                <code><a href="#bucketwebsite">*Bucket<wbr>Website</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration if the bucket acts as a website. Structure is documented below.
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
            <td class="align-top">bucket<wbr>Policy<wbr>Only</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Bucket Policy Only](https://cloud.google.com/storage/docs/bucket-policy-only) access to a bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cors</td>
            <td class="align-top">
                
                <code><a href="#bucketcor">Bucket<wbr>Cor[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Cross-Origin Resource Sharing (CORS)](https://www.w3.org/TR/cors/) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Event<wbr>Based<wbr>Hold</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">encryption</td>
            <td class="align-top">
                
                <code><a href="#bucketencryption">Bucket<wbr>Encryption?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s encryption configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">force<wbr>Destroy</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When deleting a bucket, this
boolean option will delete all contained objects. If you try to delete a
bucket that contains objects, the provider will fail that run.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">lifecycle<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerule">Bucket<wbr>Lifecycle<wbr>Rule[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Lifecycle Rules](https://cloud.google.com/storage/docs/lifecycle#configuration) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [GCS location](https://cloud.google.com/storage/docs/bucket-locations)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logging</td>
            <td class="align-top">
                
                <code><a href="#bucketlogging">Bucket<wbr>Logging?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Access &amp; Storage Logs](https://cloud.google.com/storage/docs/access-logs) configuration.
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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">requester<wbr>Pays</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Requester Pays](https://cloud.google.com/storage/docs/requester-pays) on a storage bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retention<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#bucketretentionpolicy">Bucket<wbr>Retention<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of the bucket&#39;s data retention policy for how long objects in the bucket should be retained. Structure is documented below.
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
The URI of the created resource.
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
The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The base URL of the bucket, in the format `gs://&lt;bucket-name&gt;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">versioning</td>
            <td class="align-top">
                
                <code><a href="#bucketversioning">Bucket<wbr>Versioning?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Versioning](https://cloud.google.com/storage/docs/object-versioning) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">website</td>
            <td class="align-top">
                
                <code><a href="#bucketwebsite">Bucket<wbr>Website?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration if the bucket acts as a website. Structure is documented below.
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
            <td class="align-top">bucket_<wbr>policy_<wbr>only</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Bucket Policy Only](https://cloud.google.com/storage/docs/bucket-policy-only) access to a bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cors</td>
            <td class="align-top">
                
                <code><a href="#bucketcor">List[Bucket<wbr>Cor]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Cross-Origin Resource Sharing (CORS)](https://www.w3.org/TR/cors/) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>event_<wbr>based_<wbr>hold</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">encryption</td>
            <td class="align-top">
                
                <code><a href="#bucketencryption">Dict[Bucket<wbr>Encryption]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s encryption configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">force_<wbr>destroy</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When deleting a bucket, this
boolean option will delete all contained objects. If you try to delete a
bucket that contains objects, the provider will fail that run.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">lifecycle_<wbr>rules</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerule">List[Bucket<wbr>Lifecycle<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Lifecycle Rules](https://cloud.google.com/storage/docs/lifecycle#configuration) configuration. Multiple blocks of this type are permitted. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [GCS location](https://cloud.google.com/storage/docs/bucket-locations)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logging</td>
            <td class="align-top">
                
                <code><a href="#bucketlogging">Dict[Bucket<wbr>Logging]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Access &amp; Storage Logs](https://cloud.google.com/storage/docs/access-logs) configuration.
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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">requester_<wbr>pays</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables [Requester Pays](https://cloud.google.com/storage/docs/requester-pays) on a storage bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retention_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#bucketretentionpolicy">Dict[Bucket<wbr>Retention<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of the bucket&#39;s data retention policy for how long objects in the bucket should be retained. Structure is documented below.
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
The URI of the created resource.
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
The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The base URL of the bucket, in the format `gs://&lt;bucket-name&gt;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">versioning</td>
            <td class="align-top">
                
                <code><a href="#bucketversioning">Dict[Bucket<wbr>Versioning]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucket&#39;s [Versioning](https://cloud.google.com/storage/docs/object-versioning) configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">website</td>
            <td class="align-top">
                
                <code><a href="#bucketwebsite">Dict[Bucket<wbr>Website]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration if the bucket acts as a website. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### BucketCor
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BucketCor">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BucketCor">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketCorArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketCorOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketCorArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketCor.html">output</a> API doc for this type.
{{% /lang %}}



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
            <td class="align-top">Max<wbr>Age<wbr>Seconds</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Methods</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Origins</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Response<wbr>Headers</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Max<wbr>Age<wbr>Seconds</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Methods</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Origins</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Response<wbr>Headers</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">max<wbr>Age<wbr>Seconds</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">methods</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">origins</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">response<wbr>Headers</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">max<wbr>Age<wbr>Seconds</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">methods</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">origins</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">response<wbr>Headers</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### BucketEncryption
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BucketEncryption">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BucketEncryption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketEncryptionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketEncryptionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketEncryptionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketEncryption.html">output</a> API doc for this type.
{{% /lang %}}



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
            <td class="align-top">Default<wbr>Kms<wbr>Key<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">Default<wbr>Kms<wbr>Key<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">default<wbr>Kms<wbr>Key<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">default<wbr>Kms<wbr>Key<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### BucketLifecycleRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BucketLifecycleRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BucketLifecycleRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketLifecycleRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketLifecycleRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketLifecycleRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketLifecycleRule.html">output</a> API doc for this type.
{{% /lang %}}



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
            <td class="align-top">Action</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecycleruleaction">Bucket<wbr>Lifecycle<wbr>Rule<wbr>Action<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Condition</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerulecondition">Bucket<wbr>Lifecycle<wbr>Rule<wbr>Condition<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">Action</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecycleruleaction">Bucket<wbr>Lifecycle<wbr>Rule<wbr>Action</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Condition</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerulecondition">Bucket<wbr>Lifecycle<wbr>Rule<wbr>Condition</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">action</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecycleruleaction">Bucket<wbr>Lifecycle<wbr>Rule<wbr>Action</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">condition</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerulecondition">Bucket<wbr>Lifecycle<wbr>Rule<wbr>Condition</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">action</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecycleruleaction">Dict[Bucket<wbr>Lifecycle<wbr>Rule<wbr>Action]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">condition</td>
            <td class="align-top">
                
                <code><a href="#bucketlifecyclerulecondition">Dict[Bucket<wbr>Lifecycle<wbr>Rule<wbr>Condition]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### BucketLifecycleRuleAction
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BucketLifecycleRuleAction">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BucketLifecycleRuleAction">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketLifecycleRuleActionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketLifecycleRuleActionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketLifecycleRuleActionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketLifecycleRuleAction.html">output</a> API doc for this type.
{{% /lang %}}



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
            <td class="align-top">Storage<wbr>Class</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">Storage<wbr>Class</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">storage<wbr>Class</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">storage_<wbr>class</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The [Storage Class](https://cloud.google.com/storage/docs/storage-classes) of the new bucket. Supported values include: `STANDARD`, `MULTI_REGIONAL`, `REGIONAL`, `NEARLINE`, `COLDLINE`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### BucketLifecycleRuleCondition
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BucketLifecycleRuleCondition">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BucketLifecycleRuleCondition">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketLifecycleRuleConditionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketLifecycleRuleConditionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketLifecycleRuleConditionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketLifecycleRuleCondition.html">output</a> API doc for this type.
{{% /lang %}}



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
            <td class="align-top">Age</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Created<wbr>Before</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Matches<wbr>Storage<wbr>Classes</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Newer<wbr>Versions</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">With<wbr>State</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Age</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Created<wbr>Before</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Matches<wbr>Storage<wbr>Classes</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Newer<wbr>Versions</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">With<wbr>State</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">age</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">created<wbr>Before</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">matches<wbr>Storage<wbr>Classes</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num<wbr>Newer<wbr>Versions</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">with<wbr>State</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">age</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">created<wbr>Before</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">matches<wbr>Storage<wbr>Classes</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num<wbr>Newer<wbr>Versions</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">with<wbr>State</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### BucketLogging
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BucketLogging">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BucketLogging">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketLoggingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketLoggingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketLoggingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketLogging.html">output</a> API doc for this type.
{{% /lang %}}



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
            <td class="align-top">Log<wbr>Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Object<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Log<wbr>Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Object<wbr>Prefix</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">log<wbr>Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Object<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">log<wbr>Bucket</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Object<wbr>Prefix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### BucketRetentionPolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BucketRetentionPolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BucketRetentionPolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketRetentionPolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketRetentionPolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketRetentionPolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketRetentionPolicy.html">output</a> API doc for this type.
{{% /lang %}}



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
            <td class="align-top">Is<wbr>Locked</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retention<wbr>Period</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">Is<wbr>Locked</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retention<wbr>Period</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">is<wbr>Locked</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retention<wbr>Period</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">is<wbr>Locked</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retention<wbr>Period</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### BucketVersioning
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BucketVersioning">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BucketVersioning">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketVersioningArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketVersioningOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketVersioningArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketVersioning.html">output</a> API doc for this type.
{{% /lang %}}



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
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### BucketWebsite
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BucketWebsite">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BucketWebsite">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketWebsiteArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketWebsiteOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketWebsiteArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketWebsite.html">output</a> API doc for this type.
{{% /lang %}}



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
            <td class="align-top">Main<wbr>Page<wbr>Suffix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Not<wbr>Found<wbr>Page</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Main<wbr>Page<wbr>Suffix</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Not<wbr>Found<wbr>Page</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">main<wbr>Page<wbr>Suffix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">not<wbr>Found<wbr>Page</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">main<wbr>Page<wbr>Suffix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">not<wbr>Found<wbr>Page</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








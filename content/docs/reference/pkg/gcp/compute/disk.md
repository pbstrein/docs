
---
title: "Disk"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a Disk Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#Disk">Disk</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#DiskArgs">DiskArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Disk</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>disk_encryption_key=None<span class="p">, </span>image=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>physical_block_size_bytes=None<span class="p">, </span>project=None<span class="p">, </span>resource_policies=None<span class="p">, </span>size=None<span class="p">, </span>snapshot=None<span class="p">, </span>source_image_encryption_key=None<span class="p">, </span>source_snapshot_encryption_key=None<span class="p">, </span>type=None<span class="p">, </span>zone=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDisk<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#DiskArgs">DiskArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#Disk">Disk</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.Disk.html">Disk</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.DiskArgs.html">DiskArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Disk resource with the given unique name, arguments, and options.

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
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#diskdiskencryptionkey">Disk<wbr>Disk<wbr>Encryption<wbr>Key<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Encrypts the disk using a customer-supplied encryption key. After you encrypt a disk with a customer-supplied key, you
must provide the same key if you use the disk later (e.g. to create a disk snapshot or an image, or to attach the disk
to a virtual machine). Customer-supplied encryption keys do not protect access to metadata of the disk. If you do not
provide an encryption key when creating the disk, then the disk will be encrypted using an automatically generated key
and you do not need to provide a key to use the disk later.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Image</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The image from which to initialize this disk. This can be one of: the image&#39;s &#39;self_link&#39;,
&#39;projects/{project}/global/images/{image}&#39;, &#39;projects/{project}/global/images/family/{family}&#39;, &#39;global/images/{image}&#39;,
&#39;global/images/family/{family}&#39;, &#39;family/{family}&#39;, &#39;{project}/{family}&#39;, &#39;{project}/{image}&#39;, &#39;{family}&#39;, or &#39;{image}&#39;.
If referred by family, the images names must include the family name. If they don&#39;t, use the [google_compute_image data
source](/docs/providers/google/d/datasource_compute_image.html). For instance, the image &#39;centos-6-v20180104&#39; includes
its family name &#39;centos-6&#39;. These images can be referred by family name here.
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
Labels to apply to this disk. A list of key-&gt;value pairs.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Physical<wbr>Block<wbr>Size<wbr>Bytes</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Physical block size of the persistent disk, in bytes. If not present in a request, a default value is used. Currently
supported sizes are 4096 and 16384, other sizes may be added in the future. If an unsupported value is requested, the
error message will list the supported values for the caller&#39;s project.
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
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Policies</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Resource policies applied to this disk for automatic snapshot creations.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Size</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Size of the persistent disk, specified in GB. You can specify this field when creating a persistent disk using the
&#39;image&#39; or &#39;snapshot&#39; parameter, or specify it alone to create an empty persistent disk. If you specify this field along
with &#39;image&#39; or &#39;snapshot&#39;, the value must not be less than the size of the image or the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Snapshot</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. If the
snapshot is in another project than this disk, you must supply a full URL. For example, the following are valid values:
* &#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourceimageencryptionkey">Disk<wbr>Source<wbr>Image<wbr>Encryption<wbr>Key<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source image. Required if the source image is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourcesnapshotencryptionkey">Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source snapshot. Required if the source snapshot is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the disk type resource describing which disk type to use to create the disk. Provide this when creating the disk.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the zone where the disk resides.
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
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#diskdiskencryptionkey">*Disk<wbr>Disk<wbr>Encryption<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Encrypts the disk using a customer-supplied encryption key. After you encrypt a disk with a customer-supplied key, you
must provide the same key if you use the disk later (e.g. to create a disk snapshot or an image, or to attach the disk
to a virtual machine). Customer-supplied encryption keys do not protect access to metadata of the disk. If you do not
provide an encryption key when creating the disk, then the disk will be encrypted using an automatically generated key
and you do not need to provide a key to use the disk later.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Image</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The image from which to initialize this disk. This can be one of: the image&#39;s &#39;self_link&#39;,
&#39;projects/{project}/global/images/{image}&#39;, &#39;projects/{project}/global/images/family/{family}&#39;, &#39;global/images/{image}&#39;,
&#39;global/images/family/{family}&#39;, &#39;family/{family}&#39;, &#39;{project}/{family}&#39;, &#39;{project}/{image}&#39;, &#39;{family}&#39;, or &#39;{image}&#39;.
If referred by family, the images names must include the family name. If they don&#39;t, use the [google_compute_image data
source](/docs/providers/google/d/datasource_compute_image.html). For instance, the image &#39;centos-6-v20180104&#39; includes
its family name &#39;centos-6&#39;. These images can be referred by family name here.
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
Labels to apply to this disk. A list of key-&gt;value pairs.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Physical<wbr>Block<wbr>Size<wbr>Bytes</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Physical block size of the persistent disk, in bytes. If not present in a request, a default value is used. Currently
supported sizes are 4096 and 16384, other sizes may be added in the future. If an unsupported value is requested, the
error message will list the supported values for the caller&#39;s project.
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
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Policies</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Resource policies applied to this disk for automatic snapshot creations.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Size</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Size of the persistent disk, specified in GB. You can specify this field when creating a persistent disk using the
&#39;image&#39; or &#39;snapshot&#39; parameter, or specify it alone to create an empty persistent disk. If you specify this field along
with &#39;image&#39; or &#39;snapshot&#39;, the value must not be less than the size of the image or the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Snapshot</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. If the
snapshot is in another project than this disk, you must supply a full URL. For example, the following are valid values:
* &#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourceimageencryptionkey">*Disk<wbr>Source<wbr>Image<wbr>Encryption<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source image. Required if the source image is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourcesnapshotencryptionkey">*Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source snapshot. Required if the source snapshot is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the disk type resource describing which disk type to use to create the disk. Provide this when creating the disk.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the zone where the disk resides.
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
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#diskdiskencryptionkey">Disk<wbr>Disk<wbr>Encryption<wbr>Key?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Encrypts the disk using a customer-supplied encryption key. After you encrypt a disk with a customer-supplied key, you
must provide the same key if you use the disk later (e.g. to create a disk snapshot or an image, or to attach the disk
to a virtual machine). Customer-supplied encryption keys do not protect access to metadata of the disk. If you do not
provide an encryption key when creating the disk, then the disk will be encrypted using an automatically generated key
and you do not need to provide a key to use the disk later.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">image</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The image from which to initialize this disk. This can be one of: the image&#39;s &#39;self_link&#39;,
&#39;projects/{project}/global/images/{image}&#39;, &#39;projects/{project}/global/images/family/{family}&#39;, &#39;global/images/{image}&#39;,
&#39;global/images/family/{family}&#39;, &#39;family/{family}&#39;, &#39;{project}/{family}&#39;, &#39;{project}/{image}&#39;, &#39;{family}&#39;, or &#39;{image}&#39;.
If referred by family, the images names must include the family name. If they don&#39;t, use the [google_compute_image data
source](/docs/providers/google/d/datasource_compute_image.html). For instance, the image &#39;centos-6-v20180104&#39; includes
its family name &#39;centos-6&#39;. These images can be referred by family name here.
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
Labels to apply to this disk. A list of key-&gt;value pairs.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">physical<wbr>Block<wbr>Size<wbr>Bytes</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Physical block size of the persistent disk, in bytes. If not present in a request, a default value is used. Currently
supported sizes are 4096 and 16384, other sizes may be added in the future. If an unsupported value is requested, the
error message will list the supported values for the caller&#39;s project.
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
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Policies</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Resource policies applied to this disk for automatic snapshot creations.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">size</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Size of the persistent disk, specified in GB. You can specify this field when creating a persistent disk using the
&#39;image&#39; or &#39;snapshot&#39; parameter, or specify it alone to create an empty persistent disk. If you specify this field along
with &#39;image&#39; or &#39;snapshot&#39;, the value must not be less than the size of the image or the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">snapshot</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. If the
snapshot is in another project than this disk, you must supply a full URL. For example, the following are valid values:
* &#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Image<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourceimageencryptionkey">Disk<wbr>Source<wbr>Image<wbr>Encryption<wbr>Key?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source image. Required if the source image is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourcesnapshotencryptionkey">Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source snapshot. Required if the source snapshot is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the disk type resource describing which disk type to use to create the disk. Provide this when creating the disk.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the zone where the disk resides.
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
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk_<wbr>encryption_<wbr>key</td>
            <td class="align-top">
                
                <code><a href="#diskdiskencryptionkey">Dict[Disk<wbr>Disk<wbr>Encryption<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Encrypts the disk using a customer-supplied encryption key. After you encrypt a disk with a customer-supplied key, you
must provide the same key if you use the disk later (e.g. to create a disk snapshot or an image, or to attach the disk
to a virtual machine). Customer-supplied encryption keys do not protect access to metadata of the disk. If you do not
provide an encryption key when creating the disk, then the disk will be encrypted using an automatically generated key
and you do not need to provide a key to use the disk later.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">image</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The image from which to initialize this disk. This can be one of: the image&#39;s &#39;self_link&#39;,
&#39;projects/{project}/global/images/{image}&#39;, &#39;projects/{project}/global/images/family/{family}&#39;, &#39;global/images/{image}&#39;,
&#39;global/images/family/{family}&#39;, &#39;family/{family}&#39;, &#39;{project}/{family}&#39;, &#39;{project}/{image}&#39;, &#39;{family}&#39;, or &#39;{image}&#39;.
If referred by family, the images names must include the family name. If they don&#39;t, use the [google_compute_image data
source](/docs/providers/google/d/datasource_compute_image.html). For instance, the image &#39;centos-6-v20180104&#39; includes
its family name &#39;centos-6&#39;. These images can be referred by family name here.
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
Labels to apply to this disk. A list of key-&gt;value pairs.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">physical_<wbr>block_<wbr>size_<wbr>bytes</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Physical block size of the persistent disk, in bytes. If not present in a request, a default value is used. Currently
supported sizes are 4096 and 16384, other sizes may be added in the future. If an unsupported value is requested, the
error message will list the supported values for the caller&#39;s project.
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
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>policies</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Resource policies applied to this disk for automatic snapshot creations.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">size</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Size of the persistent disk, specified in GB. You can specify this field when creating a persistent disk using the
&#39;image&#39; or &#39;snapshot&#39; parameter, or specify it alone to create an empty persistent disk. If you specify this field along
with &#39;image&#39; or &#39;snapshot&#39;, the value must not be less than the size of the image or the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">snapshot</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. If the
snapshot is in another project than this disk, you must supply a full URL. For example, the following are valid values:
* &#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>image_<wbr>encryption_<wbr>key</td>
            <td class="align-top">
                
                <code><a href="#disksourceimageencryptionkey">Dict[Disk<wbr>Source<wbr>Image<wbr>Encryption<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source image. Required if the source image is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>snapshot_<wbr>encryption_<wbr>key</td>
            <td class="align-top">
                
                <code><a href="#disksourcesnapshotencryptionkey">Dict[Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source snapshot. Required if the source snapshot is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the disk type resource describing which disk type to use to create the disk. Provide this when creating the disk.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the zone where the disk resides.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Disk Output Properties

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
            <td class="align-top">Creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#diskdiskencryptionkey">Disk<wbr>Disk<wbr>Encryption<wbr>Key?</a></code>
            </td>
            <td class="align-top">{{% md %}} Encrypts the disk using a customer-supplied encryption key. After you encrypt a disk with a customer-supplied key, you
must provide the same key if you use the disk later (e.g. to create a disk snapshot or an image, or to attach the disk
to a virtual machine). Customer-supplied encryption keys do not protect access to metadata of the disk. If you do not
provide an encryption key when creating the disk, then the disk will be encrypted using an automatically generated key
and you do not need to provide a key to use the disk later.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Image</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The image from which to initialize this disk. This can be one of: the image&#39;s &#39;self_link&#39;,
&#39;projects/{project}/global/images/{image}&#39;, &#39;projects/{project}/global/images/family/{family}&#39;, &#39;global/images/{image}&#39;,
&#39;global/images/family/{family}&#39;, &#39;family/{family}&#39;, &#39;{project}/{family}&#39;, &#39;{project}/{image}&#39;, &#39;{family}&#39;, or &#39;{image}&#39;.
If referred by family, the images names must include the family name. If they don&#39;t, use the [google_compute_image data
source](/docs/providers/google/d/datasource_compute_image.html). For instance, the image &#39;centos-6-v20180104&#39; includes
its family name &#39;centos-6&#39;. These images can be referred by family name here.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint used for optimistic locking of this resource. Used internally during updates.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} Labels to apply to this disk. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Last<wbr>Attach<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Last attach timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Last<wbr>Detach<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Last detach timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Physical<wbr>Block<wbr>Size<wbr>Bytes</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} Physical block size of the persistent disk, in bytes. If not present in a request, a default value is used. Currently
supported sizes are 4096 and 16384, other sizes may be added in the future. If an unsupported value is requested, the
error message will list the supported values for the caller&#39;s project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Policies</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} Resource policies applied to this disk for automatic snapshot creations.
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
            <td class="align-top">Size</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} Size of the persistent disk, specified in GB. You can specify this field when creating a persistent disk using the
&#39;image&#39; or &#39;snapshot&#39; parameter, or specify it alone to create an empty persistent disk. If you specify this field along
with &#39;image&#39; or &#39;snapshot&#39;, the value must not be less than the size of the image or the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Snapshot</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. If the
snapshot is in another project than this disk, you must supply a full URL. For example, the following are valid values:
* &#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourceimageencryptionkey">Disk<wbr>Source<wbr>Image<wbr>Encryption<wbr>Key?</a></code>
            </td>
            <td class="align-top">{{% md %}} The customer-supplied encryption key of the source image. Required if the source image is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID value of the image used to create this disk. This value identifies the exact image that was used to create this
persistent disk. For example, if you created the persistent disk from an image that was later deleted and recreated
under the same name, the source image ID would identify the exact version of the image that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourcesnapshotencryptionkey">Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key?</a></code>
            </td>
            <td class="align-top">{{% md %}} The customer-supplied encryption key of the source snapshot. Required if the source snapshot is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique ID of the snapshot used to create this disk. This value identifies the exact snapshot that was used to create
this persistent disk. For example, if you created the persistent disk from a snapshot that was later deleted and
recreated under the same name, the source snapshot ID would identify the exact version of the snapshot that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL of the disk type resource describing which disk type to use to create the disk. Provide this when creating the disk.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Users</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} Links to the users of the disk (attached instances) in form: project/zones/zone/instances/instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the zone where the disk resides.
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
            <td class="align-top">Creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#diskdiskencryptionkey">*Disk<wbr>Disk<wbr>Encryption<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} Encrypts the disk using a customer-supplied encryption key. After you encrypt a disk with a customer-supplied key, you
must provide the same key if you use the disk later (e.g. to create a disk snapshot or an image, or to attach the disk
to a virtual machine). Customer-supplied encryption keys do not protect access to metadata of the disk. If you do not
provide an encryption key when creating the disk, then the disk will be encrypted using an automatically generated key
and you do not need to provide a key to use the disk later.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Image</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The image from which to initialize this disk. This can be one of: the image&#39;s &#39;self_link&#39;,
&#39;projects/{project}/global/images/{image}&#39;, &#39;projects/{project}/global/images/family/{family}&#39;, &#39;global/images/{image}&#39;,
&#39;global/images/family/{family}&#39;, &#39;family/{family}&#39;, &#39;{project}/{family}&#39;, &#39;{project}/{image}&#39;, &#39;{family}&#39;, or &#39;{image}&#39;.
If referred by family, the images names must include the family name. If they don&#39;t, use the [google_compute_image data
source](/docs/providers/google/d/datasource_compute_image.html). For instance, the image &#39;centos-6-v20180104&#39; includes
its family name &#39;centos-6&#39;. These images can be referred by family name here.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint used for optimistic locking of this resource. Used internally during updates.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} Labels to apply to this disk. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Last<wbr>Attach<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Last attach timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Last<wbr>Detach<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Last detach timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Physical<wbr>Block<wbr>Size<wbr>Bytes</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} Physical block size of the persistent disk, in bytes. If not present in a request, a default value is used. Currently
supported sizes are 4096 and 16384, other sizes may be added in the future. If an unsupported value is requested, the
error message will list the supported values for the caller&#39;s project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Policies</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} Resource policies applied to this disk for automatic snapshot creations.
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
            <td class="align-top">Size</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} Size of the persistent disk, specified in GB. You can specify this field when creating a persistent disk using the
&#39;image&#39; or &#39;snapshot&#39; parameter, or specify it alone to create an empty persistent disk. If you specify this field along
with &#39;image&#39; or &#39;snapshot&#39;, the value must not be less than the size of the image or the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Snapshot</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. If the
snapshot is in another project than this disk, you must supply a full URL. For example, the following are valid values:
* &#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourceimageencryptionkey">*Disk<wbr>Source<wbr>Image<wbr>Encryption<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} The customer-supplied encryption key of the source image. Required if the source image is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID value of the image used to create this disk. This value identifies the exact image that was used to create this
persistent disk. For example, if you created the persistent disk from an image that was later deleted and recreated
under the same name, the source image ID would identify the exact version of the image that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourcesnapshotencryptionkey">*Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} The customer-supplied encryption key of the source snapshot. Required if the source snapshot is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique ID of the snapshot used to create this disk. This value identifies the exact snapshot that was used to create
this persistent disk. For example, if you created the persistent disk from a snapshot that was later deleted and
recreated under the same name, the source snapshot ID would identify the exact version of the snapshot that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} URL of the disk type resource describing which disk type to use to create the disk. Provide this when creating the disk.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Users</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} Links to the users of the disk (attached instances) in form: project/zones/zone/instances/instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the zone where the disk resides.
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
            <td class="align-top">creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#diskdiskencryptionkey">Disk<wbr>Disk<wbr>Encryption<wbr>Key?</a></code>
            </td>
            <td class="align-top">{{% md %}} Encrypts the disk using a customer-supplied encryption key. After you encrypt a disk with a customer-supplied key, you
must provide the same key if you use the disk later (e.g. to create a disk snapshot or an image, or to attach the disk
to a virtual machine). Customer-supplied encryption keys do not protect access to metadata of the disk. If you do not
provide an encryption key when creating the disk, then the disk will be encrypted using an automatically generated key
and you do not need to provide a key to use the disk later.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">image</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The image from which to initialize this disk. This can be one of: the image&#39;s &#39;self_link&#39;,
&#39;projects/{project}/global/images/{image}&#39;, &#39;projects/{project}/global/images/family/{family}&#39;, &#39;global/images/{image}&#39;,
&#39;global/images/family/{family}&#39;, &#39;family/{family}&#39;, &#39;{project}/{family}&#39;, &#39;{project}/{image}&#39;, &#39;{family}&#39;, or &#39;{image}&#39;.
If referred by family, the images names must include the family name. If they don&#39;t, use the [google_compute_image data
source](/docs/providers/google/d/datasource_compute_image.html). For instance, the image &#39;centos-6-v20180104&#39; includes
its family name &#39;centos-6&#39;. These images can be referred by family name here.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint used for optimistic locking of this resource. Used internally during updates.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} Labels to apply to this disk. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">last<wbr>Attach<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Last attach timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">last<wbr>Detach<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Last detach timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">physical<wbr>Block<wbr>Size<wbr>Bytes</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} Physical block size of the persistent disk, in bytes. If not present in a request, a default value is used. Currently
supported sizes are 4096 and 16384, other sizes may be added in the future. If an unsupported value is requested, the
error message will list the supported values for the caller&#39;s project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Policies</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} Resource policies applied to this disk for automatic snapshot creations.
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
            <td class="align-top">size</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} Size of the persistent disk, specified in GB. You can specify this field when creating a persistent disk using the
&#39;image&#39; or &#39;snapshot&#39; parameter, or specify it alone to create an empty persistent disk. If you specify this field along
with &#39;image&#39; or &#39;snapshot&#39;, the value must not be less than the size of the image or the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">snapshot</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. If the
snapshot is in another project than this disk, you must supply a full URL. For example, the following are valid values:
* &#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Image<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourceimageencryptionkey">Disk<wbr>Source<wbr>Image<wbr>Encryption<wbr>Key?</a></code>
            </td>
            <td class="align-top">{{% md %}} The customer-supplied encryption key of the source image. Required if the source image is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Image<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID value of the image used to create this disk. This value identifies the exact image that was used to create this
persistent disk. For example, if you created the persistent disk from an image that was later deleted and recreated
under the same name, the source image ID would identify the exact version of the image that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourcesnapshotencryptionkey">Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key?</a></code>
            </td>
            <td class="align-top">{{% md %}} The customer-supplied encryption key of the source snapshot. Required if the source snapshot is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Snapshot<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique ID of the snapshot used to create this disk. This value identifies the exact snapshot that was used to create
this persistent disk. For example, if you created the persistent disk from a snapshot that was later deleted and
recreated under the same name, the source snapshot ID would identify the exact version of the snapshot that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL of the disk type resource describing which disk type to use to create the disk. Provide this when creating the disk.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">users</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} Links to the users of the disk (attached instances) in form: project/zones/zone/instances/instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the zone where the disk resides.
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
            <td class="align-top">creation_<wbr>timestamp</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk_<wbr>encryption_<wbr>key</td>
            <td class="align-top">
                
                <code><a href="#diskdiskencryptionkey">Dict[Disk<wbr>Disk<wbr>Encryption<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} Encrypts the disk using a customer-supplied encryption key. After you encrypt a disk with a customer-supplied key, you
must provide the same key if you use the disk later (e.g. to create a disk snapshot or an image, or to attach the disk
to a virtual machine). Customer-supplied encryption keys do not protect access to metadata of the disk. If you do not
provide an encryption key when creating the disk, then the disk will be encrypted using an automatically generated key
and you do not need to provide a key to use the disk later.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">image</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The image from which to initialize this disk. This can be one of: the image&#39;s &#39;self_link&#39;,
&#39;projects/{project}/global/images/{image}&#39;, &#39;projects/{project}/global/images/family/{family}&#39;, &#39;global/images/{image}&#39;,
&#39;global/images/family/{family}&#39;, &#39;family/{family}&#39;, &#39;{project}/{family}&#39;, &#39;{project}/{image}&#39;, &#39;{family}&#39;, or &#39;{image}&#39;.
If referred by family, the images names must include the family name. If they don&#39;t, use the [google_compute_image data
source](/docs/providers/google/d/datasource_compute_image.html). For instance, the image &#39;centos-6-v20180104&#39; includes
its family name &#39;centos-6&#39;. These images can be referred by family name here.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label_<wbr>fingerprint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint used for optimistic locking of this resource. Used internally during updates.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} Labels to apply to this disk. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">last_<wbr>attach_<wbr>timestamp</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Last attach timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">last_<wbr>detach_<wbr>timestamp</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Last detach timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">physical_<wbr>block_<wbr>size_<wbr>bytes</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} Physical block size of the persistent disk, in bytes. If not present in a request, a default value is used. Currently
supported sizes are 4096 and 16384, other sizes may be added in the future. If an unsupported value is requested, the
error message will list the supported values for the caller&#39;s project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>policies</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} Resource policies applied to this disk for automatic snapshot creations.
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
            <td class="align-top">size</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} Size of the persistent disk, specified in GB. You can specify this field when creating a persistent disk using the
&#39;image&#39; or &#39;snapshot&#39; parameter, or specify it alone to create an empty persistent disk. If you specify this field along
with &#39;image&#39; or &#39;snapshot&#39;, the value must not be less than the size of the image or the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">snapshot</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. If the
snapshot is in another project than this disk, you must supply a full URL. For example, the following are valid values:
* &#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>image_<wbr>encryption_<wbr>key</td>
            <td class="align-top">
                
                <code><a href="#disksourceimageencryptionkey">Dict[Disk<wbr>Source<wbr>Image<wbr>Encryption<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} The customer-supplied encryption key of the source image. Required if the source image is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>image_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The ID value of the image used to create this disk. This value identifies the exact image that was used to create this
persistent disk. For example, if you created the persistent disk from an image that was later deleted and recreated
under the same name, the source image ID would identify the exact version of the image that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>snapshot_<wbr>encryption_<wbr>key</td>
            <td class="align-top">
                
                <code><a href="#disksourcesnapshotencryptionkey">Dict[Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} The customer-supplied encryption key of the source snapshot. Required if the source snapshot is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>snapshot_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The unique ID of the snapshot used to create this disk. This value identifies the exact snapshot that was used to create
this persistent disk. For example, if you created the persistent disk from a snapshot that was later deleted and
recreated under the same name, the source snapshot ID would identify the exact version of the snapshot that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} URL of the disk type resource describing which disk type to use to create the disk. Provide this when creating the disk.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">users</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} Links to the users of the disk (attached instances) in form: project/zones/zone/instances/instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the zone where the disk resides.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Disk Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#DiskState">DiskState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#Disk">Disk</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>creation_timestamp=None<span class="p">, </span>description=None<span class="p">, </span>disk_encryption_key=None<span class="p">, </span>image=None<span class="p">, </span>label_fingerprint=None<span class="p">, </span>labels=None<span class="p">, </span>last_attach_timestamp=None<span class="p">, </span>last_detach_timestamp=None<span class="p">, </span>name=None<span class="p">, </span>physical_block_size_bytes=None<span class="p">, </span>project=None<span class="p">, </span>resource_policies=None<span class="p">, </span>self_link=None<span class="p">, </span>size=None<span class="p">, </span>snapshot=None<span class="p">, </span>source_image_encryption_key=None<span class="p">, </span>source_image_id=None<span class="p">, </span>source_snapshot_encryption_key=None<span class="p">, </span>source_snapshot_id=None<span class="p">, </span>type=None<span class="p">, </span>users=None<span class="p">, </span>zone=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDisk<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#DiskState">DiskState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#Disk">Disk</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.Disk.html">Disk</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.DiskState.html">DiskState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Disk resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#diskdiskencryptionkey">Disk<wbr>Disk<wbr>Encryption<wbr>Key<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Encrypts the disk using a customer-supplied encryption key. After you encrypt a disk with a customer-supplied key, you
must provide the same key if you use the disk later (e.g. to create a disk snapshot or an image, or to attach the disk
to a virtual machine). Customer-supplied encryption keys do not protect access to metadata of the disk. If you do not
provide an encryption key when creating the disk, then the disk will be encrypted using an automatically generated key
and you do not need to provide a key to use the disk later.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Image</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The image from which to initialize this disk. This can be one of: the image&#39;s &#39;self_link&#39;,
&#39;projects/{project}/global/images/{image}&#39;, &#39;projects/{project}/global/images/family/{family}&#39;, &#39;global/images/{image}&#39;,
&#39;global/images/family/{family}&#39;, &#39;family/{family}&#39;, &#39;{project}/{family}&#39;, &#39;{project}/{image}&#39;, &#39;{family}&#39;, or &#39;{image}&#39;.
If referred by family, the images names must include the family name. If they don&#39;t, use the [google_compute_image data
source](/docs/providers/google/d/datasource_compute_image.html). For instance, the image &#39;centos-6-v20180104&#39; includes
its family name &#39;centos-6&#39;. These images can be referred by family name here.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The fingerprint used for optimistic locking of this resource. Used internally during updates.
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
Labels to apply to this disk. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Last<wbr>Attach<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Last attach timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Last<wbr>Detach<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Last detach timestamp in RFC3339 text format.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Physical<wbr>Block<wbr>Size<wbr>Bytes</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Physical block size of the persistent disk, in bytes. If not present in a request, a default value is used. Currently
supported sizes are 4096 and 16384, other sizes may be added in the future. If an unsupported value is requested, the
error message will list the supported values for the caller&#39;s project.
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
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Policies</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Resource policies applied to this disk for automatic snapshot creations.
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
            <td class="align-top">Size</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Size of the persistent disk, specified in GB. You can specify this field when creating a persistent disk using the
&#39;image&#39; or &#39;snapshot&#39; parameter, or specify it alone to create an empty persistent disk. If you specify this field along
with &#39;image&#39; or &#39;snapshot&#39;, the value must not be less than the size of the image or the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Snapshot</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. If the
snapshot is in another project than this disk, you must supply a full URL. For example, the following are valid values:
* &#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourceimageencryptionkey">Disk<wbr>Source<wbr>Image<wbr>Encryption<wbr>Key<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source image. Required if the source image is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID value of the image used to create this disk. This value identifies the exact image that was used to create this
persistent disk. For example, if you created the persistent disk from an image that was later deleted and recreated
under the same name, the source image ID would identify the exact version of the image that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourcesnapshotencryptionkey">Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source snapshot. Required if the source snapshot is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique ID of the snapshot used to create this disk. This value identifies the exact snapshot that was used to create
this persistent disk. For example, if you created the persistent disk from a snapshot that was later deleted and
recreated under the same name, the source snapshot ID would identify the exact version of the snapshot that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the disk type resource describing which disk type to use to create the disk. Provide this when creating the disk.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Users</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Links to the users of the disk (attached instances) in form: project/zones/zone/instances/instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the zone where the disk resides.
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
            <td class="align-top">Creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#diskdiskencryptionkey">*Disk<wbr>Disk<wbr>Encryption<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Encrypts the disk using a customer-supplied encryption key. After you encrypt a disk with a customer-supplied key, you
must provide the same key if you use the disk later (e.g. to create a disk snapshot or an image, or to attach the disk
to a virtual machine). Customer-supplied encryption keys do not protect access to metadata of the disk. If you do not
provide an encryption key when creating the disk, then the disk will be encrypted using an automatically generated key
and you do not need to provide a key to use the disk later.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Image</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The image from which to initialize this disk. This can be one of: the image&#39;s &#39;self_link&#39;,
&#39;projects/{project}/global/images/{image}&#39;, &#39;projects/{project}/global/images/family/{family}&#39;, &#39;global/images/{image}&#39;,
&#39;global/images/family/{family}&#39;, &#39;family/{family}&#39;, &#39;{project}/{family}&#39;, &#39;{project}/{image}&#39;, &#39;{family}&#39;, or &#39;{image}&#39;.
If referred by family, the images names must include the family name. If they don&#39;t, use the [google_compute_image data
source](/docs/providers/google/d/datasource_compute_image.html). For instance, the image &#39;centos-6-v20180104&#39; includes
its family name &#39;centos-6&#39;. These images can be referred by family name here.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The fingerprint used for optimistic locking of this resource. Used internally during updates.
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
Labels to apply to this disk. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Last<wbr>Attach<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Last attach timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Last<wbr>Detach<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Last detach timestamp in RFC3339 text format.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Physical<wbr>Block<wbr>Size<wbr>Bytes</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Physical block size of the persistent disk, in bytes. If not present in a request, a default value is used. Currently
supported sizes are 4096 and 16384, other sizes may be added in the future. If an unsupported value is requested, the
error message will list the supported values for the caller&#39;s project.
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
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Policies</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Resource policies applied to this disk for automatic snapshot creations.
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
            <td class="align-top">Size</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Size of the persistent disk, specified in GB. You can specify this field when creating a persistent disk using the
&#39;image&#39; or &#39;snapshot&#39; parameter, or specify it alone to create an empty persistent disk. If you specify this field along
with &#39;image&#39; or &#39;snapshot&#39;, the value must not be less than the size of the image or the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Snapshot</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. If the
snapshot is in another project than this disk, you must supply a full URL. For example, the following are valid values:
* &#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourceimageencryptionkey">*Disk<wbr>Source<wbr>Image<wbr>Encryption<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source image. Required if the source image is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID value of the image used to create this disk. This value identifies the exact image that was used to create this
persistent disk. For example, if you created the persistent disk from an image that was later deleted and recreated
under the same name, the source image ID would identify the exact version of the image that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourcesnapshotencryptionkey">*Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source snapshot. Required if the source snapshot is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique ID of the snapshot used to create this disk. This value identifies the exact snapshot that was used to create
this persistent disk. For example, if you created the persistent disk from a snapshot that was later deleted and
recreated under the same name, the source snapshot ID would identify the exact version of the snapshot that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the disk type resource describing which disk type to use to create the disk. Provide this when creating the disk.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Users</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Links to the users of the disk (attached instances) in form: project/zones/zone/instances/instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the zone where the disk resides.
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
            <td class="align-top">creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#diskdiskencryptionkey">Disk<wbr>Disk<wbr>Encryption<wbr>Key?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Encrypts the disk using a customer-supplied encryption key. After you encrypt a disk with a customer-supplied key, you
must provide the same key if you use the disk later (e.g. to create a disk snapshot or an image, or to attach the disk
to a virtual machine). Customer-supplied encryption keys do not protect access to metadata of the disk. If you do not
provide an encryption key when creating the disk, then the disk will be encrypted using an automatically generated key
and you do not need to provide a key to use the disk later.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">image</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The image from which to initialize this disk. This can be one of: the image&#39;s &#39;self_link&#39;,
&#39;projects/{project}/global/images/{image}&#39;, &#39;projects/{project}/global/images/family/{family}&#39;, &#39;global/images/{image}&#39;,
&#39;global/images/family/{family}&#39;, &#39;family/{family}&#39;, &#39;{project}/{family}&#39;, &#39;{project}/{image}&#39;, &#39;{family}&#39;, or &#39;{image}&#39;.
If referred by family, the images names must include the family name. If they don&#39;t, use the [google_compute_image data
source](/docs/providers/google/d/datasource_compute_image.html). For instance, the image &#39;centos-6-v20180104&#39; includes
its family name &#39;centos-6&#39;. These images can be referred by family name here.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The fingerprint used for optimistic locking of this resource. Used internally during updates.
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
Labels to apply to this disk. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">last<wbr>Attach<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Last attach timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">last<wbr>Detach<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Last detach timestamp in RFC3339 text format.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">physical<wbr>Block<wbr>Size<wbr>Bytes</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Physical block size of the persistent disk, in bytes. If not present in a request, a default value is used. Currently
supported sizes are 4096 and 16384, other sizes may be added in the future. If an unsupported value is requested, the
error message will list the supported values for the caller&#39;s project.
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
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Policies</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Resource policies applied to this disk for automatic snapshot creations.
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
            <td class="align-top">size</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Size of the persistent disk, specified in GB. You can specify this field when creating a persistent disk using the
&#39;image&#39; or &#39;snapshot&#39; parameter, or specify it alone to create an empty persistent disk. If you specify this field along
with &#39;image&#39; or &#39;snapshot&#39;, the value must not be less than the size of the image or the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">snapshot</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. If the
snapshot is in another project than this disk, you must supply a full URL. For example, the following are valid values:
* &#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Image<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourceimageencryptionkey">Disk<wbr>Source<wbr>Image<wbr>Encryption<wbr>Key?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source image. Required if the source image is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Image<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID value of the image used to create this disk. This value identifies the exact image that was used to create this
persistent disk. For example, if you created the persistent disk from an image that was later deleted and recreated
under the same name, the source image ID would identify the exact version of the image that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#disksourcesnapshotencryptionkey">Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source snapshot. Required if the source snapshot is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Snapshot<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique ID of the snapshot used to create this disk. This value identifies the exact snapshot that was used to create
this persistent disk. For example, if you created the persistent disk from a snapshot that was later deleted and
recreated under the same name, the source snapshot ID would identify the exact version of the snapshot that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the disk type resource describing which disk type to use to create the disk. Provide this when creating the disk.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">users</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Links to the users of the disk (attached instances) in form: project/zones/zone/instances/instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the zone where the disk resides.
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
            <td class="align-top">creation_<wbr>timestamp</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk_<wbr>encryption_<wbr>key</td>
            <td class="align-top">
                
                <code><a href="#diskdiskencryptionkey">Dict[Disk<wbr>Disk<wbr>Encryption<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Encrypts the disk using a customer-supplied encryption key. After you encrypt a disk with a customer-supplied key, you
must provide the same key if you use the disk later (e.g. to create a disk snapshot or an image, or to attach the disk
to a virtual machine). Customer-supplied encryption keys do not protect access to metadata of the disk. If you do not
provide an encryption key when creating the disk, then the disk will be encrypted using an automatically generated key
and you do not need to provide a key to use the disk later.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">image</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The image from which to initialize this disk. This can be one of: the image&#39;s &#39;self_link&#39;,
&#39;projects/{project}/global/images/{image}&#39;, &#39;projects/{project}/global/images/family/{family}&#39;, &#39;global/images/{image}&#39;,
&#39;global/images/family/{family}&#39;, &#39;family/{family}&#39;, &#39;{project}/{family}&#39;, &#39;{project}/{image}&#39;, &#39;{family}&#39;, or &#39;{image}&#39;.
If referred by family, the images names must include the family name. If they don&#39;t, use the [google_compute_image data
source](/docs/providers/google/d/datasource_compute_image.html). For instance, the image &#39;centos-6-v20180104&#39; includes
its family name &#39;centos-6&#39;. These images can be referred by family name here.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label_<wbr>fingerprint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The fingerprint used for optimistic locking of this resource. Used internally during updates.
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
Labels to apply to this disk. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">last_<wbr>attach_<wbr>timestamp</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Last attach timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">last_<wbr>detach_<wbr>timestamp</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Last detach timestamp in RFC3339 text format.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">physical_<wbr>block_<wbr>size_<wbr>bytes</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Physical block size of the persistent disk, in bytes. If not present in a request, a default value is used. Currently
supported sizes are 4096 and 16384, other sizes may be added in the future. If an unsupported value is requested, the
error message will list the supported values for the caller&#39;s project.
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
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>policies</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Resource policies applied to this disk for automatic snapshot creations.
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
            <td class="align-top">size</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Size of the persistent disk, specified in GB. You can specify this field when creating a persistent disk using the
&#39;image&#39; or &#39;snapshot&#39; parameter, or specify it alone to create an empty persistent disk. If you specify this field along
with &#39;image&#39; or &#39;snapshot&#39;, the value must not be less than the size of the image or the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">snapshot</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. If the
snapshot is in another project than this disk, you must supply a full URL. For example, the following are valid values:
* &#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>image_<wbr>encryption_<wbr>key</td>
            <td class="align-top">
                
                <code><a href="#disksourceimageencryptionkey">Dict[Disk<wbr>Source<wbr>Image<wbr>Encryption<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source image. Required if the source image is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>image_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID value of the image used to create this disk. This value identifies the exact image that was used to create this
persistent disk. For example, if you created the persistent disk from an image that was later deleted and recreated
under the same name, the source image ID would identify the exact version of the image that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>snapshot_<wbr>encryption_<wbr>key</td>
            <td class="align-top">
                
                <code><a href="#disksourcesnapshotencryptionkey">Dict[Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The customer-supplied encryption key of the source snapshot. Required if the source snapshot is protected by a
customer-supplied encryption key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>snapshot_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique ID of the snapshot used to create this disk. This value identifies the exact snapshot that was used to create
this persistent disk. For example, if you created the persistent disk from a snapshot that was later deleted and
recreated under the same name, the source snapshot ID would identify the exact version of the snapshot that was used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the disk type resource describing which disk type to use to create the disk. Provide this when creating the disk.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">users</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Links to the users of the disk (attached instances) in form: project/zones/zone/instances/instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the zone where the disk resides.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### DiskDiskEncryptionKey
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#DiskDiskEncryptionKey">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#DiskDiskEncryptionKey">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#DiskDiskEncryptionKeyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#DiskDiskEncryptionKeyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.DiskDiskEncryptionKeyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.DiskDiskEncryptionKey.html">output</a> API doc for this type.
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
            <td class="align-top">Kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Raw<wbr>Key</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sha256</td>
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
            <td class="align-top">Kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Raw<wbr>Key</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sha256</td>
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
            <td class="align-top">kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">raw<wbr>Key</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sha256</td>
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
            <td class="align-top">kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">raw<wbr>Key</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sha256</td>
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





#### DiskSourceImageEncryptionKey
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#DiskSourceImageEncryptionKey">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#DiskSourceImageEncryptionKey">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#DiskSourceImageEncryptionKeyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#DiskSourceImageEncryptionKeyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.DiskSourceImageEncryptionKeyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.DiskSourceImageEncryptionKey.html">output</a> API doc for this type.
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
            <td class="align-top">Kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Raw<wbr>Key</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sha256</td>
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
            <td class="align-top">Kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Raw<wbr>Key</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sha256</td>
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
            <td class="align-top">kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">raw<wbr>Key</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sha256</td>
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
            <td class="align-top">kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">raw<wbr>Key</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sha256</td>
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





#### DiskSourceSnapshotEncryptionKey
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#DiskSourceSnapshotEncryptionKey">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#DiskSourceSnapshotEncryptionKey">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#DiskSourceSnapshotEncryptionKeyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#DiskSourceSnapshotEncryptionKeyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.DiskSourceSnapshotEncryptionKeyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.DiskSourceSnapshotEncryptionKey.html">output</a> API doc for this type.
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
            <td class="align-top">Kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Raw<wbr>Key</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sha256</td>
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
            <td class="align-top">Kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Raw<wbr>Key</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sha256</td>
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
            <td class="align-top">kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">raw<wbr>Key</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sha256</td>
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
            <td class="align-top">kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">raw<wbr>Key</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sha256</td>
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








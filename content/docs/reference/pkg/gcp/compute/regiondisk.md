
---
title: "RegionDisk"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a RegionDisk Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RegionDisk">RegionDisk</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RegionDiskArgs">RegionDiskArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">RegionDisk</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>disk_encryption_key=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>physical_block_size_bytes=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>replica_zones=None<span class="p">, </span>size=None<span class="p">, </span>snapshot=None<span class="p">, </span>source_snapshot_encryption_key=None<span class="p">, </span>type=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewRegionDisk<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionDiskArgs">RegionDiskArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionDisk">RegionDisk</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionDisk.html">RegionDisk</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionDiskArgs.html">RegionDiskArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a RegionDisk resource with the given unique name, arguments, and options.

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
                
                <code><a href="#regiondiskdiskencryptionkey">Region<wbr>Disk<wbr>Disk<wbr>Encryption<wbr>Key<wbr>Args?</a></code>
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the disk resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Replica<wbr>Zones</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
URLs of the zones where the disk should be replicated to.
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
sourceImage or sourceSnapshot parameter, or specify it alone to create an empty persistent disk. If you specify this
field along with sourceImage or sourceSnapshot, the value of sizeGb must not be less than the size of the sourceImage or
the size of the snapshot.
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
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. For
example, the following are valid values: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#regiondisksourcesnapshotencryptionkey">Region<wbr>Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key<wbr>Args?</a></code>
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
                
                <code><a href="#regiondiskdiskencryptionkey">*Region<wbr>Disk<wbr>Disk<wbr>Encryption<wbr>Key</a></code>
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the disk resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Replica<wbr>Zones</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
URLs of the zones where the disk should be replicated to.
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
sourceImage or sourceSnapshot parameter, or specify it alone to create an empty persistent disk. If you specify this
field along with sourceImage or sourceSnapshot, the value of sizeGb must not be less than the size of the sourceImage or
the size of the snapshot.
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
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. For
example, the following are valid values: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#regiondisksourcesnapshotencryptionkey">*Region<wbr>Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key</a></code>
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
                
                <code><a href="#regiondiskdiskencryptionkey">Region<wbr>Disk<wbr>Disk<wbr>Encryption<wbr>Key?</a></code>
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the disk resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">replica<wbr>Zones</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
URLs of the zones where the disk should be replicated to.
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
sourceImage or sourceSnapshot parameter, or specify it alone to create an empty persistent disk. If you specify this
field along with sourceImage or sourceSnapshot, the value of sizeGb must not be less than the size of the sourceImage or
the size of the snapshot.
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
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. For
example, the following are valid values: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#regiondisksourcesnapshotencryptionkey">Region<wbr>Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key?</a></code>
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
                
                <code><a href="#regiondiskdiskencryptionkey">Dict[Region<wbr>Disk<wbr>Disk<wbr>Encryption<wbr>Key]</a></code>
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the disk resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">replica_<wbr>zones</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
URLs of the zones where the disk should be replicated to.
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
sourceImage or sourceSnapshot parameter, or specify it alone to create an empty persistent disk. If you specify this
field along with sourceImage or sourceSnapshot, the value of sizeGb must not be less than the size of the sourceImage or
the size of the snapshot.
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
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. For
example, the following are valid values: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>snapshot_<wbr>encryption_<wbr>key</td>
            <td class="align-top">
                
                <code><a href="#regiondisksourcesnapshotencryptionkey">Dict[Region<wbr>Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key]</a></code>
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
    
    </tbody>
</table>


{{% /lang %}}







## RegionDisk Output Properties

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
                
                <code><a href="#regiondiskdiskencryptionkey">Region<wbr>Disk<wbr>Disk<wbr>Encryption<wbr>Key?</a></code>
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the region where the disk resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Replica<wbr>Zones</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} URLs of the zones where the disk should be replicated to.
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
sourceImage or sourceSnapshot parameter, or specify it alone to create an empty persistent disk. If you specify this
field along with sourceImage or sourceSnapshot, the value of sizeGb must not be less than the size of the sourceImage or
the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Snapshot</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. For
example, the following are valid values: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#regiondisksourcesnapshotencryptionkey">Region<wbr>Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key?</a></code>
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
                
                <code><a href="#regiondiskdiskencryptionkey">*Region<wbr>Disk<wbr>Disk<wbr>Encryption<wbr>Key</a></code>
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the region where the disk resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Replica<wbr>Zones</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} URLs of the zones where the disk should be replicated to.
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
sourceImage or sourceSnapshot parameter, or specify it alone to create an empty persistent disk. If you specify this
field along with sourceImage or sourceSnapshot, the value of sizeGb must not be less than the size of the sourceImage or
the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Snapshot</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. For
example, the following are valid values: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#regiondisksourcesnapshotencryptionkey">*Region<wbr>Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key</a></code>
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
                
                <code><a href="#regiondiskdiskencryptionkey">Region<wbr>Disk<wbr>Disk<wbr>Encryption<wbr>Key?</a></code>
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the region where the disk resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">replica<wbr>Zones</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} URLs of the zones where the disk should be replicated to.
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
sourceImage or sourceSnapshot parameter, or specify it alone to create an empty persistent disk. If you specify this
field along with sourceImage or sourceSnapshot, the value of sizeGb must not be less than the size of the sourceImage or
the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">snapshot</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. For
example, the following are valid values: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#regiondisksourcesnapshotencryptionkey">Region<wbr>Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key?</a></code>
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
                
                <code><a href="#regiondiskdiskencryptionkey">Dict[Region<wbr>Disk<wbr>Disk<wbr>Encryption<wbr>Key]</a></code>
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the region where the disk resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">replica_<wbr>zones</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} URLs of the zones where the disk should be replicated to.
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
sourceImage or sourceSnapshot parameter, or specify it alone to create an empty persistent disk. If you specify this
field along with sourceImage or sourceSnapshot, the value of sizeGb must not be less than the size of the sourceImage or
the size of the snapshot.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">snapshot</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. For
example, the following are valid values: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>snapshot_<wbr>encryption_<wbr>key</td>
            <td class="align-top">
                
                <code><a href="#regiondisksourcesnapshotencryptionkey">Dict[Region<wbr>Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key]</a></code>
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
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing RegionDisk Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RegionDiskState">RegionDiskState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RegionDisk">RegionDisk</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>creation_timestamp=None<span class="p">, </span>description=None<span class="p">, </span>disk_encryption_key=None<span class="p">, </span>label_fingerprint=None<span class="p">, </span>labels=None<span class="p">, </span>last_attach_timestamp=None<span class="p">, </span>last_detach_timestamp=None<span class="p">, </span>name=None<span class="p">, </span>physical_block_size_bytes=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>replica_zones=None<span class="p">, </span>self_link=None<span class="p">, </span>size=None<span class="p">, </span>snapshot=None<span class="p">, </span>source_snapshot_encryption_key=None<span class="p">, </span>source_snapshot_id=None<span class="p">, </span>type=None<span class="p">, </span>users=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetRegionDisk<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionDiskState">RegionDiskState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionDisk">RegionDisk</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionDisk.html">RegionDisk</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionDiskState.html">RegionDiskState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing RegionDisk resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
                
                <code><a href="#regiondiskdiskencryptionkey">Region<wbr>Disk<wbr>Disk<wbr>Encryption<wbr>Key<wbr>Args?</a></code>
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the disk resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Replica<wbr>Zones</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URLs of the zones where the disk should be replicated to.
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
sourceImage or sourceSnapshot parameter, or specify it alone to create an empty persistent disk. If you specify this
field along with sourceImage or sourceSnapshot, the value of sizeGb must not be less than the size of the sourceImage or
the size of the snapshot.
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
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. For
example, the following are valid values: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#regiondisksourcesnapshotencryptionkey">Region<wbr>Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key<wbr>Args?</a></code>
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
                
                <code><a href="#regiondiskdiskencryptionkey">*Region<wbr>Disk<wbr>Disk<wbr>Encryption<wbr>Key</a></code>
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the disk resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Replica<wbr>Zones</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URLs of the zones where the disk should be replicated to.
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
sourceImage or sourceSnapshot parameter, or specify it alone to create an empty persistent disk. If you specify this
field along with sourceImage or sourceSnapshot, the value of sizeGb must not be less than the size of the sourceImage or
the size of the snapshot.
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
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. For
example, the following are valid values: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#regiondisksourcesnapshotencryptionkey">*Region<wbr>Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key</a></code>
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
                
                <code><a href="#regiondiskdiskencryptionkey">Region<wbr>Disk<wbr>Disk<wbr>Encryption<wbr>Key?</a></code>
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the disk resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">replica<wbr>Zones</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URLs of the zones where the disk should be replicated to.
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
sourceImage or sourceSnapshot parameter, or specify it alone to create an empty persistent disk. If you specify this
field along with sourceImage or sourceSnapshot, the value of sizeGb must not be less than the size of the sourceImage or
the size of the snapshot.
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
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. For
example, the following are valid values: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Snapshot<wbr>Encryption<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#regiondisksourcesnapshotencryptionkey">Region<wbr>Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key?</a></code>
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
                
                <code><a href="#regiondiskdiskencryptionkey">Dict[Region<wbr>Disk<wbr>Disk<wbr>Encryption<wbr>Key]</a></code>
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the disk resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">replica_<wbr>zones</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URLs of the zones where the disk should be replicated to.
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
sourceImage or sourceSnapshot parameter, or specify it alone to create an empty persistent disk. If you specify this
field along with sourceImage or sourceSnapshot, the value of sizeGb must not be less than the size of the sourceImage or
the size of the snapshot.
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
The source snapshot used to create this disk. You can provide this as a partial or full URL to the resource. For
example, the following are valid values: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot&#39; *
&#39;projects/project/global/snapshots/snapshot&#39; * &#39;global/snapshots/snapshot&#39; * &#39;snapshot&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>snapshot_<wbr>encryption_<wbr>key</td>
            <td class="align-top">
                
                <code><a href="#regiondisksourcesnapshotencryptionkey">Dict[Region<wbr>Disk<wbr>Source<wbr>Snapshot<wbr>Encryption<wbr>Key]</a></code>
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
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### RegionDiskDiskEncryptionKey
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegionDiskDiskEncryptionKey">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegionDiskDiskEncryptionKey">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionDiskDiskEncryptionKeyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionDiskDiskEncryptionKeyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionDiskDiskEncryptionKeyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionDiskDiskEncryptionKey.html">output</a> API doc for this type.
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
            <td class="align-top">Kms<wbr>Key<wbr>Name</td>
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
            <td class="align-top">Kms<wbr>Key<wbr>Name</td>
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
            <td class="align-top">kms<wbr>Key<wbr>Name</td>
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
            <td class="align-top">kms_<wbr>key_<wbr>name</td>
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





#### RegionDiskSourceSnapshotEncryptionKey
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegionDiskSourceSnapshotEncryptionKey">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegionDiskSourceSnapshotEncryptionKey">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionDiskSourceSnapshotEncryptionKeyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionDiskSourceSnapshotEncryptionKeyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionDiskSourceSnapshotEncryptionKeyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionDiskSourceSnapshotEncryptionKey.html">output</a> API doc for this type.
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
            <td class="align-top">Kms<wbr>Key<wbr>Name</td>
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
            <td class="align-top">Kms<wbr>Key<wbr>Name</td>
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
            <td class="align-top">kms<wbr>Key<wbr>Name</td>
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
            <td class="align-top">kms_<wbr>key_<wbr>name</td>
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








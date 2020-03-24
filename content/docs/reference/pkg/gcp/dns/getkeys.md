
---
title: "GetKeys"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Get the DNSKEY and DS records of DNSSEC-signed managed zones. For more information see the
[official documentation](https://cloud.google.com/dns/docs/dnskeys/)
and [API](https://cloud.google.com/dns/docs/reference/v1/dnsKeys).

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/d/datasource_dns_keys.html.markdown.





## Using GetKeys

{{< langchoose csharp nojavascript >}}


<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getKeys<span class="p">(</span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/dns/#GetKeysArgs">GetKeysArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#InvokeOptions">pulumi.InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/dns/#GetKeysResult">GetKeysResult</a></span>></span></code></pre></div>


<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_keys(</span>managed_zone=None<span class="p">, </span>project=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>


<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupKeys<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#LookupKeysArgs">LookupKeysArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">pulumi.InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#LookupKeysResult">LookupKeysResult</a></span>, error)</span></code></pre></div>


<div class="highlight">
<pre class="chroma">
<code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetKeys </span><span class="p">{</span>
    <span class="k">public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.GetKeysResult.html">GetKeysResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.GetKeysArgs.html">GetKeysArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span>
<span class="p">}</span></code></pre>
</div>



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
            <td class="align-top">Managed<wbr>Zone</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or id of the Cloud DNS managed zone.
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
The ID of the project in which the resource belongs. If `project` is not provided, the provider project is used.
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
            <td class="align-top">Managed<wbr>Zone</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or id of the Cloud DNS managed zone.
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
The ID of the project in which the resource belongs. If `project` is not provided, the provider project is used.
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
            <td class="align-top">managed<wbr>Zone</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or id of the Cloud DNS managed zone.
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
The ID of the project in which the resource belongs. If `project` is not provided, the provider project is used.
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
            <td class="align-top">managed_<wbr>zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or id of the Cloud DNS managed zone.
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
The ID of the project in which the resource belongs. If `project` is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## GetKeys Result

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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} id is the provider-assigned unique ID for this managed resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Signing<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#getkeyskeysigningkey">List&lt;Get<wbr>Keys<wbr>Key<wbr>Signing<wbr>Key&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of Key-signing key (KSK) records. Structure is documented below. Additionally, the DS record is provided:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Managed<wbr>Zone</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone<wbr>Signing<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#getkeyszonesigningkey">List&lt;Get<wbr>Keys<wbr>Zone<wbr>Signing<wbr>Key&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of Zone-signing key (ZSK) records. Structure is documented below.
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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} id is the provider-assigned unique ID for this managed resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Signing<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#getkeyskeysigningkey">[]Get<wbr>Keys<wbr>Key<wbr>Signing<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of Key-signing key (KSK) records. Structure is documented below. Additionally, the DS record is provided:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Managed<wbr>Zone</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone<wbr>Signing<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#getkeyszonesigningkey">[]Get<wbr>Keys<wbr>Zone<wbr>Signing<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of Zone-signing key (ZSK) records. Structure is documented below.
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} id is the provider-assigned unique ID for this managed resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key<wbr>Signing<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#getkeyskeysigningkey">Get<wbr>Keys<wbr>Key<wbr>Signing<wbr>Key[]</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of Key-signing key (KSK) records. Structure is documented below. Additionally, the DS record is provided:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">managed<wbr>Zone</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone<wbr>Signing<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#getkeyszonesigningkey">Get<wbr>Keys<wbr>Zone<wbr>Signing<wbr>Key[]</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of Zone-signing key (ZSK) records. Structure is documented below.
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} id is the provider-assigned unique ID for this managed resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key_<wbr>signing_<wbr>keys</td>
            <td class="align-top">
                
                <code><a href="#getkeyskeysigningkey">List[Get<wbr>Keys<wbr>Key<wbr>Signing<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of Key-signing key (KSK) records. Structure is documented below. Additionally, the DS record is provided:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">managed_<wbr>zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone_<wbr>signing_<wbr>keys</td>
            <td class="align-top">
                
                <code><a href="#getkeyszonesigningkey">List[Get<wbr>Keys<wbr>Zone<wbr>Signing<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of Zone-signing key (ZSK) records. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Supporting Types

#### GetKeysKeySigningKey
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetKeysKeySigningKey">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#GetKeysKeySigningKey">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.GetKeysKeySigningKey.html">output</a> API doc for this type.
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
            <td class="align-top">Algorithm</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
String mnemonic specifying the DNSSEC algorithm of this key. Immutable after creation time. Possible values are `ecdsap256sha256`, `ecdsap384sha384`, `rsasha1`, `rsasha256`, and `rsasha512`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The time that this resource was created in the control plane. This is in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A mutable string of at most 1024 characters associated with this resource for the user&#39;s convenience.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Digests</td>
            <td class="align-top">
                
                <code><a href="#getkeyskeysigningkeydigest">List&lt;Get<wbr>Keys<wbr>Key<wbr>Signing<wbr>Key<wbr>Digest<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of cryptographic hashes of the DNSKEY resource record associated with this DnsKey. These digests are needed to construct a DS record that points at this DNS key. Each contains:
- `digest` - The base-16 encoded bytes of this digest. Suitable for use in a DS resource record.
- `type` - Specifies the algorithm used to calculate this digest. Possible values are `sha1`, `sha256` and `sha384`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ds<wbr>Record</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The DS record based on the KSK record. This is used when [delegating](https://cloud.google.com/dns/docs/dnssec-advanced#subdelegation) DNSSEC-signed subdomains.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Unique identifier for the resource; defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Active</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Active keys will be used to sign subsequent changes to the ManagedZone. Inactive keys will still be present as DNSKEY Resource Records for the use of resolvers validating existing signatures.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Length</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Length of the key in bits. Specified at creation time then immutable.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Tag</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The key tag is a non-cryptographic hash of the a DNSKEY resource record associated with this DnsKey. The key tag can be used to identify a DNSKEY more quickly (but it is not a unique identifier). In particular, the key tag is used in a parent zone&#39;s DS record to point at the DNSKEY in this child ManagedZone. The key tag is a number in the range [0, 65535] and the algorithm to calculate it is specified in RFC4034 Appendix B.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Key</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Base64 encoded public half of this key.
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
            <td class="align-top">Algorithm</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
String mnemonic specifying the DNSSEC algorithm of this key. Immutable after creation time. Possible values are `ecdsap256sha256`, `ecdsap384sha384`, `rsasha1`, `rsasha256`, and `rsasha512`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The time that this resource was created in the control plane. This is in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A mutable string of at most 1024 characters associated with this resource for the user&#39;s convenience.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Digests</td>
            <td class="align-top">
                
                <code><a href="#getkeyskeysigningkeydigest">[]Get<wbr>Keys<wbr>Key<wbr>Signing<wbr>Key<wbr>Digest</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of cryptographic hashes of the DNSKEY resource record associated with this DnsKey. These digests are needed to construct a DS record that points at this DNS key. Each contains:
- `digest` - The base-16 encoded bytes of this digest. Suitable for use in a DS resource record.
- `type` - Specifies the algorithm used to calculate this digest. Possible values are `sha1`, `sha256` and `sha384`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ds<wbr>Record</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The DS record based on the KSK record. This is used when [delegating](https://cloud.google.com/dns/docs/dnssec-advanced#subdelegation) DNSSEC-signed subdomains.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Unique identifier for the resource; defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Active</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Active keys will be used to sign subsequent changes to the ManagedZone. Inactive keys will still be present as DNSKEY Resource Records for the use of resolvers validating existing signatures.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Length</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Length of the key in bits. Specified at creation time then immutable.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Tag</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The key tag is a non-cryptographic hash of the a DNSKEY resource record associated with this DnsKey. The key tag can be used to identify a DNSKEY more quickly (but it is not a unique identifier). In particular, the key tag is used in a parent zone&#39;s DS record to point at the DNSKEY in this child ManagedZone. The key tag is a number in the range [0, 65535] and the algorithm to calculate it is specified in RFC4034 Appendix B.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Key</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Base64 encoded public half of this key.
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
            <td class="align-top">algorithm</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
String mnemonic specifying the DNSSEC algorithm of this key. Immutable after creation time. Possible values are `ecdsap256sha256`, `ecdsap384sha384`, `rsasha1`, `rsasha256`, and `rsasha512`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The time that this resource was created in the control plane. This is in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A mutable string of at most 1024 characters associated with this resource for the user&#39;s convenience.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">digests</td>
            <td class="align-top">
                
                <code><a href="#getkeyskeysigningkeydigest">Get<wbr>Keys<wbr>Key<wbr>Signing<wbr>Key<wbr>Digest[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of cryptographic hashes of the DNSKEY resource record associated with this DnsKey. These digests are needed to construct a DS record that points at this DNS key. Each contains:
- `digest` - The base-16 encoded bytes of this digest. Suitable for use in a DS resource record.
- `type` - Specifies the algorithm used to calculate this digest. Possible values are `sha1`, `sha256` and `sha384`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ds<wbr>Record</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The DS record based on the KSK record. This is used when [delegating](https://cloud.google.com/dns/docs/dnssec-advanced#subdelegation) DNSSEC-signed subdomains.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Unique identifier for the resource; defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is<wbr>Active</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Active keys will be used to sign subsequent changes to the ManagedZone. Inactive keys will still be present as DNSKEY Resource Records for the use of resolvers validating existing signatures.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key<wbr>Length</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Length of the key in bits. Specified at creation time then immutable.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key<wbr>Tag</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The key tag is a non-cryptographic hash of the a DNSKEY resource record associated with this DnsKey. The key tag can be used to identify a DNSKEY more quickly (but it is not a unique identifier). In particular, the key tag is used in a parent zone&#39;s DS record to point at the DNSKEY in this child ManagedZone. The key tag is a number in the range [0, 65535] and the algorithm to calculate it is specified in RFC4034 Appendix B.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public<wbr>Key</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Base64 encoded public half of this key.
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
            <td class="align-top">algorithm</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
String mnemonic specifying the DNSSEC algorithm of this key. Immutable after creation time. Possible values are `ecdsap256sha256`, `ecdsap384sha384`, `rsasha1`, `rsasha256`, and `rsasha512`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation_<wbr>time</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The time that this resource was created in the control plane. This is in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A mutable string of at most 1024 characters associated with this resource for the user&#39;s convenience.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">digests</td>
            <td class="align-top">
                
                <code><a href="#getkeyskeysigningkeydigest">List[Get<wbr>Keys<wbr>Key<wbr>Signing<wbr>Key<wbr>Digest]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of cryptographic hashes of the DNSKEY resource record associated with this DnsKey. These digests are needed to construct a DS record that points at this DNS key. Each contains:
- `digest` - The base-16 encoded bytes of this digest. Suitable for use in a DS resource record.
- `type` - Specifies the algorithm used to calculate this digest. Possible values are `sha1`, `sha256` and `sha384`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ds<wbr>Record</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The DS record based on the KSK record. This is used when [delegating](https://cloud.google.com/dns/docs/dnssec-advanced#subdelegation) DNSSEC-signed subdomains.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Unique identifier for the resource; defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is<wbr>Active</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Active keys will be used to sign subsequent changes to the ManagedZone. Inactive keys will still be present as DNSKEY Resource Records for the use of resolvers validating existing signatures.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key<wbr>Length</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Length of the key in bits. Specified at creation time then immutable.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key<wbr>Tag</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The key tag is a non-cryptographic hash of the a DNSKEY resource record associated with this DnsKey. The key tag can be used to identify a DNSKEY more quickly (but it is not a unique identifier). In particular, the key tag is used in a parent zone&#39;s DS record to point at the DNSKEY in this child ManagedZone. The key tag is a number in the range [0, 65535] and the algorithm to calculate it is specified in RFC4034 Appendix B.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public_<wbr>key</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Base64 encoded public half of this key.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetKeysKeySigningKeyDigest
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetKeysKeySigningKeyDigest">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#GetKeysKeySigningKeyDigest">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.GetKeysKeySigningKeyDigest.html">output</a> API doc for this type.
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
            <td class="align-top">Digest</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Digest</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">digest</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">digest</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetKeysZoneSigningKey
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetKeysZoneSigningKey">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#GetKeysZoneSigningKey">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.GetKeysZoneSigningKey.html">output</a> API doc for this type.
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
            <td class="align-top">Algorithm</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
String mnemonic specifying the DNSSEC algorithm of this key. Immutable after creation time. Possible values are `ecdsap256sha256`, `ecdsap384sha384`, `rsasha1`, `rsasha256`, and `rsasha512`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The time that this resource was created in the control plane. This is in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A mutable string of at most 1024 characters associated with this resource for the user&#39;s convenience.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Digests</td>
            <td class="align-top">
                
                <code><a href="#getkeyszonesigningkeydigest">List&lt;Get<wbr>Keys<wbr>Zone<wbr>Signing<wbr>Key<wbr>Digest<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of cryptographic hashes of the DNSKEY resource record associated with this DnsKey. These digests are needed to construct a DS record that points at this DNS key. Each contains:
- `digest` - The base-16 encoded bytes of this digest. Suitable for use in a DS resource record.
- `type` - Specifies the algorithm used to calculate this digest. Possible values are `sha1`, `sha256` and `sha384`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Unique identifier for the resource; defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Active</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Active keys will be used to sign subsequent changes to the ManagedZone. Inactive keys will still be present as DNSKEY Resource Records for the use of resolvers validating existing signatures.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Length</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Length of the key in bits. Specified at creation time then immutable.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Tag</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The key tag is a non-cryptographic hash of the a DNSKEY resource record associated with this DnsKey. The key tag can be used to identify a DNSKEY more quickly (but it is not a unique identifier). In particular, the key tag is used in a parent zone&#39;s DS record to point at the DNSKEY in this child ManagedZone. The key tag is a number in the range [0, 65535] and the algorithm to calculate it is specified in RFC4034 Appendix B.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Key</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Base64 encoded public half of this key.
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
            <td class="align-top">Algorithm</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
String mnemonic specifying the DNSSEC algorithm of this key. Immutable after creation time. Possible values are `ecdsap256sha256`, `ecdsap384sha384`, `rsasha1`, `rsasha256`, and `rsasha512`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The time that this resource was created in the control plane. This is in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A mutable string of at most 1024 characters associated with this resource for the user&#39;s convenience.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Digests</td>
            <td class="align-top">
                
                <code><a href="#getkeyszonesigningkeydigest">[]Get<wbr>Keys<wbr>Zone<wbr>Signing<wbr>Key<wbr>Digest</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of cryptographic hashes of the DNSKEY resource record associated with this DnsKey. These digests are needed to construct a DS record that points at this DNS key. Each contains:
- `digest` - The base-16 encoded bytes of this digest. Suitable for use in a DS resource record.
- `type` - Specifies the algorithm used to calculate this digest. Possible values are `sha1`, `sha256` and `sha384`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Unique identifier for the resource; defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Active</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Active keys will be used to sign subsequent changes to the ManagedZone. Inactive keys will still be present as DNSKEY Resource Records for the use of resolvers validating existing signatures.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Length</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Length of the key in bits. Specified at creation time then immutable.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Tag</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The key tag is a non-cryptographic hash of the a DNSKEY resource record associated with this DnsKey. The key tag can be used to identify a DNSKEY more quickly (but it is not a unique identifier). In particular, the key tag is used in a parent zone&#39;s DS record to point at the DNSKEY in this child ManagedZone. The key tag is a number in the range [0, 65535] and the algorithm to calculate it is specified in RFC4034 Appendix B.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Key</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Base64 encoded public half of this key.
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
            <td class="align-top">algorithm</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
String mnemonic specifying the DNSSEC algorithm of this key. Immutable after creation time. Possible values are `ecdsap256sha256`, `ecdsap384sha384`, `rsasha1`, `rsasha256`, and `rsasha512`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The time that this resource was created in the control plane. This is in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A mutable string of at most 1024 characters associated with this resource for the user&#39;s convenience.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">digests</td>
            <td class="align-top">
                
                <code><a href="#getkeyszonesigningkeydigest">Get<wbr>Keys<wbr>Zone<wbr>Signing<wbr>Key<wbr>Digest[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of cryptographic hashes of the DNSKEY resource record associated with this DnsKey. These digests are needed to construct a DS record that points at this DNS key. Each contains:
- `digest` - The base-16 encoded bytes of this digest. Suitable for use in a DS resource record.
- `type` - Specifies the algorithm used to calculate this digest. Possible values are `sha1`, `sha256` and `sha384`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Unique identifier for the resource; defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is<wbr>Active</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Active keys will be used to sign subsequent changes to the ManagedZone. Inactive keys will still be present as DNSKEY Resource Records for the use of resolvers validating existing signatures.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key<wbr>Length</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Length of the key in bits. Specified at creation time then immutable.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key<wbr>Tag</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The key tag is a non-cryptographic hash of the a DNSKEY resource record associated with this DnsKey. The key tag can be used to identify a DNSKEY more quickly (but it is not a unique identifier). In particular, the key tag is used in a parent zone&#39;s DS record to point at the DNSKEY in this child ManagedZone. The key tag is a number in the range [0, 65535] and the algorithm to calculate it is specified in RFC4034 Appendix B.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public<wbr>Key</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Base64 encoded public half of this key.
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
            <td class="align-top">algorithm</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
String mnemonic specifying the DNSSEC algorithm of this key. Immutable after creation time. Possible values are `ecdsap256sha256`, `ecdsap384sha384`, `rsasha1`, `rsasha256`, and `rsasha512`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation_<wbr>time</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The time that this resource was created in the control plane. This is in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A mutable string of at most 1024 characters associated with this resource for the user&#39;s convenience.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">digests</td>
            <td class="align-top">
                
                <code><a href="#getkeyszonesigningkeydigest">List[Get<wbr>Keys<wbr>Zone<wbr>Signing<wbr>Key<wbr>Digest]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of cryptographic hashes of the DNSKEY resource record associated with this DnsKey. These digests are needed to construct a DS record that points at this DNS key. Each contains:
- `digest` - The base-16 encoded bytes of this digest. Suitable for use in a DS resource record.
- `type` - Specifies the algorithm used to calculate this digest. Possible values are `sha1`, `sha256` and `sha384`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Unique identifier for the resource; defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is<wbr>Active</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Active keys will be used to sign subsequent changes to the ManagedZone. Inactive keys will still be present as DNSKEY Resource Records for the use of resolvers validating existing signatures.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key<wbr>Length</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Length of the key in bits. Specified at creation time then immutable.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key<wbr>Tag</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The key tag is a non-cryptographic hash of the a DNSKEY resource record associated with this DnsKey. The key tag can be used to identify a DNSKEY more quickly (but it is not a unique identifier). In particular, the key tag is used in a parent zone&#39;s DS record to point at the DNSKEY in this child ManagedZone. The key tag is a number in the range [0, 65535] and the algorithm to calculate it is specified in RFC4034 Appendix B.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public_<wbr>key</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Base64 encoded public half of this key.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetKeysZoneSigningKeyDigest
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetKeysZoneSigningKeyDigest">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#GetKeysZoneSigningKeyDigest">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.GetKeysZoneSigningKeyDigest.html">output</a> API doc for this type.
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
            <td class="align-top">Digest</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Digest</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">digest</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">digest</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








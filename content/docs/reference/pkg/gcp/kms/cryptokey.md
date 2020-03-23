
---
title: "CryptoKey"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a CryptoKey Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/kms/#CryptoKey">CryptoKey</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/kms/#CryptoKeyArgs">CryptoKeyArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">CryptoKey</span><span class="p">(resource_name, opts=None, </span>key_ring=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>purpose=None<span class="p">, </span>rotation_period=None<span class="p">, </span>version_template=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewCryptoKey<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#CryptoKeyArgs">CryptoKeyArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#CryptoKey">CryptoKey</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.CryptoKey.html">CryptoKey</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.CryptoKeyArgs.html">CryptoKeyArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a CryptoKey resource with the given unique name, arguments, and options.

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
            <td class="align-top">Key<wbr>Ring</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The KeyRing that this key belongs to. Format: &#39;&#39;projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}&#39;&#39;.
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
Labels with user-defined metadata to apply to this resource.
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
The resource name for the CryptoKey.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Purpose</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The immutable purpose of this CryptoKey. See the [purpose
reference](https://cloud.google.com/kms/docs/reference/rest/v1/projects.locations.keyRings.cryptoKeys#CryptoKeyPurpose)
for possible inputs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rotation<wbr>Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Every time this period passes, generate a new CryptoKeyVersion and set it as the primary. The first rotation will take
place after the specified period. The rotation period has the format of a decimal number with up to 9 fractional digits,
followed by the letter &#39;s&#39; (seconds). It must be greater than a day (ie, 86400).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyversiontemplate">Crypto<wbr>Key<wbr>Version<wbr>Template<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A template describing settings for new crypto key versions.
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
            <td class="align-top">Key<wbr>Ring</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The KeyRing that this key belongs to. Format: &#39;&#39;projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}&#39;&#39;.
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
Labels with user-defined metadata to apply to this resource.
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
The resource name for the CryptoKey.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Purpose</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The immutable purpose of this CryptoKey. See the [purpose
reference](https://cloud.google.com/kms/docs/reference/rest/v1/projects.locations.keyRings.cryptoKeys#CryptoKeyPurpose)
for possible inputs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rotation<wbr>Period</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Every time this period passes, generate a new CryptoKeyVersion and set it as the primary. The first rotation will take
place after the specified period. The rotation period has the format of a decimal number with up to 9 fractional digits,
followed by the letter &#39;s&#39; (seconds). It must be greater than a day (ie, 86400).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyversiontemplate">*Crypto<wbr>Key<wbr>Version<wbr>Template</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A template describing settings for new crypto key versions.
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
            <td class="align-top">key<wbr>Ring</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The KeyRing that this key belongs to. Format: &#39;&#39;projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}&#39;&#39;.
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
Labels with user-defined metadata to apply to this resource.
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
The resource name for the CryptoKey.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">purpose</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The immutable purpose of this CryptoKey. See the [purpose
reference](https://cloud.google.com/kms/docs/reference/rest/v1/projects.locations.keyRings.cryptoKeys#CryptoKeyPurpose)
for possible inputs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rotation<wbr>Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Every time this period passes, generate a new CryptoKeyVersion and set it as the primary. The first rotation will take
place after the specified period. The rotation period has the format of a decimal number with up to 9 fractional digits,
followed by the letter &#39;s&#39; (seconds). It must be greater than a day (ie, 86400).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyversiontemplate">Crypto<wbr>Key<wbr>Version<wbr>Template?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A template describing settings for new crypto key versions.
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
            <td class="align-top">key_<wbr>ring</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The KeyRing that this key belongs to. Format: &#39;&#39;projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}&#39;&#39;.
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
Labels with user-defined metadata to apply to this resource.
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
The resource name for the CryptoKey.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">purpose</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The immutable purpose of this CryptoKey. See the [purpose
reference](https://cloud.google.com/kms/docs/reference/rest/v1/projects.locations.keyRings.cryptoKeys#CryptoKeyPurpose)
for possible inputs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rotation_<wbr>period</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Every time this period passes, generate a new CryptoKeyVersion and set it as the primary. The first rotation will take
place after the specified period. The rotation period has the format of a decimal number with up to 9 fractional digits,
followed by the letter &#39;s&#39; (seconds). It must be greater than a day (ie, 86400).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version_<wbr>template</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyversiontemplate">Dict[Crypto<wbr>Key<wbr>Version<wbr>Template]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A template describing settings for new crypto key versions.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## CryptoKey Output Properties

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
            <td class="align-top">Key<wbr>Ring</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The KeyRing that this key belongs to. Format: &#39;&#39;projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}&#39;&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} Labels with user-defined metadata to apply to this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The resource name for the CryptoKey.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Purpose</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The immutable purpose of this CryptoKey. See the [purpose
reference](https://cloud.google.com/kms/docs/reference/rest/v1/projects.locations.keyRings.cryptoKeys#CryptoKeyPurpose)
for possible inputs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rotation<wbr>Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Every time this period passes, generate a new CryptoKeyVersion and set it as the primary. The first rotation will take
place after the specified period. The rotation period has the format of a decimal number with up to 9 fractional digits,
followed by the letter &#39;s&#39; (seconds). It must be greater than a day (ie, 86400).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyversiontemplate">Crypto<wbr>Key<wbr>Version<wbr>Template</a></code>
            </td>
            <td class="align-top">{{% md %}} A template describing settings for new crypto key versions.
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
            <td class="align-top">Key<wbr>Ring</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The KeyRing that this key belongs to. Format: &#39;&#39;projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}&#39;&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} Labels with user-defined metadata to apply to this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The resource name for the CryptoKey.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Purpose</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The immutable purpose of this CryptoKey. See the [purpose
reference](https://cloud.google.com/kms/docs/reference/rest/v1/projects.locations.keyRings.cryptoKeys#CryptoKeyPurpose)
for possible inputs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rotation<wbr>Period</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Every time this period passes, generate a new CryptoKeyVersion and set it as the primary. The first rotation will take
place after the specified period. The rotation period has the format of a decimal number with up to 9 fractional digits,
followed by the letter &#39;s&#39; (seconds). It must be greater than a day (ie, 86400).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyversiontemplate">Crypto<wbr>Key<wbr>Version<wbr>Template</a></code>
            </td>
            <td class="align-top">{{% md %}} A template describing settings for new crypto key versions.
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
            <td class="align-top">key<wbr>Ring</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The KeyRing that this key belongs to. Format: &#39;&#39;projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}&#39;&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} Labels with user-defined metadata to apply to this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The resource name for the CryptoKey.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">purpose</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The immutable purpose of this CryptoKey. See the [purpose
reference](https://cloud.google.com/kms/docs/reference/rest/v1/projects.locations.keyRings.cryptoKeys#CryptoKeyPurpose)
for possible inputs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rotation<wbr>Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Every time this period passes, generate a new CryptoKeyVersion and set it as the primary. The first rotation will take
place after the specified period. The rotation period has the format of a decimal number with up to 9 fractional digits,
followed by the letter &#39;s&#39; (seconds). It must be greater than a day (ie, 86400).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyversiontemplate">Crypto<wbr>Key<wbr>Version<wbr>Template</a></code>
            </td>
            <td class="align-top">{{% md %}} A template describing settings for new crypto key versions.
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
            <td class="align-top">key_<wbr>ring</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The KeyRing that this key belongs to. Format: &#39;&#39;projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}&#39;&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} Labels with user-defined metadata to apply to this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The resource name for the CryptoKey.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">purpose</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The immutable purpose of this CryptoKey. See the [purpose
reference](https://cloud.google.com/kms/docs/reference/rest/v1/projects.locations.keyRings.cryptoKeys#CryptoKeyPurpose)
for possible inputs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rotation_<wbr>period</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Every time this period passes, generate a new CryptoKeyVersion and set it as the primary. The first rotation will take
place after the specified period. The rotation period has the format of a decimal number with up to 9 fractional digits,
followed by the letter &#39;s&#39; (seconds). It must be greater than a day (ie, 86400).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self_<wbr>link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version_<wbr>template</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyversiontemplate">Dict[Crypto<wbr>Key<wbr>Version<wbr>Template]</a></code>
            </td>
            <td class="align-top">{{% md %}} A template describing settings for new crypto key versions.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing CryptoKey Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/kms/#CryptoKeyState">CryptoKeyState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/kms/#CryptoKey">CryptoKey</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>key_ring=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>purpose=None<span class="p">, </span>rotation_period=None<span class="p">, </span>self_link=None<span class="p">, </span>version_template=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetCryptoKey<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#CryptoKeyState">CryptoKeyState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#CryptoKey">CryptoKey</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.CryptoKey.html">CryptoKey</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.CryptoKeyState.html">CryptoKeyState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing CryptoKey resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Key<wbr>Ring</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The KeyRing that this key belongs to. Format: &#39;&#39;projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}&#39;&#39;.
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
Labels with user-defined metadata to apply to this resource.
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
The resource name for the CryptoKey.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Purpose</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The immutable purpose of this CryptoKey. See the [purpose
reference](https://cloud.google.com/kms/docs/reference/rest/v1/projects.locations.keyRings.cryptoKeys#CryptoKeyPurpose)
for possible inputs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rotation<wbr>Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Every time this period passes, generate a new CryptoKeyVersion and set it as the primary. The first rotation will take
place after the specified period. The rotation period has the format of a decimal number with up to 9 fractional digits,
followed by the letter &#39;s&#39; (seconds). It must be greater than a day (ie, 86400).
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyversiontemplate">Crypto<wbr>Key<wbr>Version<wbr>Template<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A template describing settings for new crypto key versions.
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
            <td class="align-top">Key<wbr>Ring</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The KeyRing that this key belongs to. Format: &#39;&#39;projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}&#39;&#39;.
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
Labels with user-defined metadata to apply to this resource.
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
The resource name for the CryptoKey.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Purpose</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The immutable purpose of this CryptoKey. See the [purpose
reference](https://cloud.google.com/kms/docs/reference/rest/v1/projects.locations.keyRings.cryptoKeys#CryptoKeyPurpose)
for possible inputs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rotation<wbr>Period</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Every time this period passes, generate a new CryptoKeyVersion and set it as the primary. The first rotation will take
place after the specified period. The rotation period has the format of a decimal number with up to 9 fractional digits,
followed by the letter &#39;s&#39; (seconds). It must be greater than a day (ie, 86400).
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyversiontemplate">*Crypto<wbr>Key<wbr>Version<wbr>Template</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A template describing settings for new crypto key versions.
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
            <td class="align-top">key<wbr>Ring</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The KeyRing that this key belongs to. Format: &#39;&#39;projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}&#39;&#39;.
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
Labels with user-defined metadata to apply to this resource.
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
The resource name for the CryptoKey.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">purpose</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The immutable purpose of this CryptoKey. See the [purpose
reference](https://cloud.google.com/kms/docs/reference/rest/v1/projects.locations.keyRings.cryptoKeys#CryptoKeyPurpose)
for possible inputs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rotation<wbr>Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Every time this period passes, generate a new CryptoKeyVersion and set it as the primary. The first rotation will take
place after the specified period. The rotation period has the format of a decimal number with up to 9 fractional digits,
followed by the letter &#39;s&#39; (seconds). It must be greater than a day (ie, 86400).
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyversiontemplate">Crypto<wbr>Key<wbr>Version<wbr>Template?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A template describing settings for new crypto key versions.
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
            <td class="align-top">key_<wbr>ring</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The KeyRing that this key belongs to. Format: &#39;&#39;projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}&#39;&#39;.
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
Labels with user-defined metadata to apply to this resource.
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
The resource name for the CryptoKey.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">purpose</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The immutable purpose of this CryptoKey. See the [purpose
reference](https://cloud.google.com/kms/docs/reference/rest/v1/projects.locations.keyRings.cryptoKeys#CryptoKeyPurpose)
for possible inputs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rotation_<wbr>period</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Every time this period passes, generate a new CryptoKeyVersion and set it as the primary. The first rotation will take
place after the specified period. The rotation period has the format of a decimal number with up to 9 fractional digits,
followed by the letter &#39;s&#39; (seconds). It must be greater than a day (ie, 86400).
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version_<wbr>template</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyversiontemplate">Dict[Crypto<wbr>Key<wbr>Version<wbr>Template]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A template describing settings for new crypto key versions.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### CryptoKeyVersionTemplate
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#CryptoKeyVersionTemplate">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#CryptoKeyVersionTemplate">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#CryptoKeyVersionTemplateArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#CryptoKeyVersionTemplateOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.CryptoKeyVersionTemplateArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.CryptoKeyVersionTemplate.html">output</a> API doc for this type.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Protection<wbr>Level</td>
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
            <td class="align-top">Algorithm</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Protection<wbr>Level</td>
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
            <td class="align-top">algorithm</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">protection<wbr>Level</td>
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
            <td class="align-top">algorithm</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">protection<wbr>Level</td>
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








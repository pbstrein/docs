
---
title: "CryptoKeyIAMMember"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Three different resources help you manage your IAM policy for KMS crypto key. Each of these resources serves a different use case:

* `gcp.kms.CryptoKeyIAMPolicy`: Authoritative. Sets the IAM policy for the crypto key and replaces any existing policy already attached.
* `gcp.kms.CryptoKeyIAMBinding`: Authoritative for a given role. Updates the IAM policy to grant a role to a list of members. Other roles within the IAM policy for the crypto key are preserved.
* `gcp.kms.CryptoKeyIAMMember`: Non-authoritative. Updates the IAM policy to grant a role to a new member. Other members for the role for the crypto key are preserved.

> **Note:** `gcp.kms.CryptoKeyIAMPolicy` **cannot** be used in conjunction with `gcp.kms.CryptoKeyIAMBinding` and `gcp.kms.CryptoKeyIAMMember` or they will fight over what your policy should be.

> **Note:** `gcp.kms.CryptoKeyIAMBinding` resources **can be** used in conjunction with `gcp.kms.CryptoKeyIAMMember` resources **only if** they do not grant privilege to the same role.

With IAM Conditions:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const admin = gcp.organizations.getIAMPolicy({
    bindings: [{
        condition: {
            description: "Expiring at midnight of 2019-12-31",
            expression: "request.time < timestamp(\"2020-01-01T00:00:00Z\")",
            title: "expires_after_2019_12_31",
        },
        members: ["user:jane@example.com"],
        role: "roles/cloudkms.cryptoKeyEncrypter",
    }],
});
```

With IAM Conditions:


With IAM Conditions:

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/google_kms_crypto_key_iam.html.markdown.



## Create a CryptoKeyIAMMember Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/kms/#CryptoKeyIAMMember">CryptoKeyIAMMember</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/kms/#CryptoKeyIAMMemberArgs">CryptoKeyIAMMemberArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">CryptoKeyIAMMember</span><span class="p">(resource_name, opts=None, </span>condition=None<span class="p">, </span>crypto_key_id=None<span class="p">, </span>member=None<span class="p">, </span>role=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewCryptoKeyIAMMember<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#CryptoKeyIAMMemberArgs">CryptoKeyIAMMemberArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#CryptoKeyIAMMember">CryptoKeyIAMMember</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.CryptoKeyIAMMember.html">CryptoKeyIAMMember</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.CryptoKeyIAMMemberArgs.html">CryptoKeyIAMMemberArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a CryptoKeyIAMMember resource with the given unique name, arguments, and options.

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
            <td class="align-top">Condition</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyiammembercondition">Crypto<wbr>Key<wbr>IAMMember<wbr>Condition<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An [IAM Condition](https://cloud.google.com/iam/docs/conditions-overview) for a given binding.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Crypto<wbr>Key<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The crypto key ID, in the form
`{project_id}/{location_name}/{key_ring_name}/{crypto_key_name}` or
`{location_name}/{key_ring_name}/{crypto_key_name}`. In the second form,
the provider&#39;s project setting will be used as a fallback.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Member</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The role that should be applied. Note that custom roles must be of the format
`[projects|organizations]/{parent-name}/roles/{role-name}`.
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
            <td class="align-top">Condition</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyiammembercondition">*Crypto<wbr>Key<wbr>IAMMember<wbr>Condition</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An [IAM Condition](https://cloud.google.com/iam/docs/conditions-overview) for a given binding.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Crypto<wbr>Key<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The crypto key ID, in the form
`{project_id}/{location_name}/{key_ring_name}/{crypto_key_name}` or
`{location_name}/{key_ring_name}/{crypto_key_name}`. In the second form,
the provider&#39;s project setting will be used as a fallback.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Member</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The role that should be applied. Note that custom roles must be of the format
`[projects|organizations]/{parent-name}/roles/{role-name}`.
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
            <td class="align-top">condition</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyiammembercondition">Crypto<wbr>Key<wbr>IAMMember<wbr>Condition?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An [IAM Condition](https://cloud.google.com/iam/docs/conditions-overview) for a given binding.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">crypto<wbr>Key<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The crypto key ID, in the form
`{project_id}/{location_name}/{key_ring_name}/{crypto_key_name}` or
`{location_name}/{key_ring_name}/{crypto_key_name}`. In the second form,
the provider&#39;s project setting will be used as a fallback.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">member</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The role that should be applied. Note that custom roles must be of the format
`[projects|organizations]/{parent-name}/roles/{role-name}`.
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
            <td class="align-top">condition</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyiammembercondition">Dict[Crypto<wbr>Key<wbr>IAMMember<wbr>Condition]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An [IAM Condition](https://cloud.google.com/iam/docs/conditions-overview) for a given binding.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">crypto_<wbr>key_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The crypto key ID, in the form
`{project_id}/{location_name}/{key_ring_name}/{crypto_key_name}` or
`{location_name}/{key_ring_name}/{crypto_key_name}`. In the second form,
the provider&#39;s project setting will be used as a fallback.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">member</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The role that should be applied. Note that custom roles must be of the format
`[projects|organizations]/{parent-name}/roles/{role-name}`.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## CryptoKeyIAMMember Output Properties

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
            <td class="align-top">Condition</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyiammembercondition">Crypto<wbr>Key<wbr>IAMMember<wbr>Condition?</a></code>
            </td>
            <td class="align-top">{{% md %}} An [IAM Condition](https://cloud.google.com/iam/docs/conditions-overview) for a given binding.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Crypto<wbr>Key<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The crypto key ID, in the form
`{project_id}/{location_name}/{key_ring_name}/{crypto_key_name}` or
`{location_name}/{key_ring_name}/{crypto_key_name}`. In the second form,
the provider&#39;s project setting will be used as a fallback.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Etag</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) The etag of the project&#39;s IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Member</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The role that should be applied. Note that custom roles must be of the format
`[projects|organizations]/{parent-name}/roles/{role-name}`.
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
            <td class="align-top">Condition</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyiammembercondition">*Crypto<wbr>Key<wbr>IAMMember<wbr>Condition</a></code>
            </td>
            <td class="align-top">{{% md %}} An [IAM Condition](https://cloud.google.com/iam/docs/conditions-overview) for a given binding.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Crypto<wbr>Key<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The crypto key ID, in the form
`{project_id}/{location_name}/{key_ring_name}/{crypto_key_name}` or
`{location_name}/{key_ring_name}/{crypto_key_name}`. In the second form,
the provider&#39;s project setting will be used as a fallback.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Etag</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) The etag of the project&#39;s IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Member</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The role that should be applied. Note that custom roles must be of the format
`[projects|organizations]/{parent-name}/roles/{role-name}`.
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
            <td class="align-top">condition</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyiammembercondition">Crypto<wbr>Key<wbr>IAMMember<wbr>Condition?</a></code>
            </td>
            <td class="align-top">{{% md %}} An [IAM Condition](https://cloud.google.com/iam/docs/conditions-overview) for a given binding.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">crypto<wbr>Key<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The crypto key ID, in the form
`{project_id}/{location_name}/{key_ring_name}/{crypto_key_name}` or
`{location_name}/{key_ring_name}/{crypto_key_name}`. In the second form,
the provider&#39;s project setting will be used as a fallback.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">etag</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) The etag of the project&#39;s IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">member</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The role that should be applied. Note that custom roles must be of the format
`[projects|organizations]/{parent-name}/roles/{role-name}`.
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
            <td class="align-top">condition</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyiammembercondition">Dict[Crypto<wbr>Key<wbr>IAMMember<wbr>Condition]</a></code>
            </td>
            <td class="align-top">{{% md %}} An [IAM Condition](https://cloud.google.com/iam/docs/conditions-overview) for a given binding.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">crypto_<wbr>key_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The crypto key ID, in the form
`{project_id}/{location_name}/{key_ring_name}/{crypto_key_name}` or
`{location_name}/{key_ring_name}/{crypto_key_name}`. In the second form,
the provider&#39;s project setting will be used as a fallback.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">etag</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) The etag of the project&#39;s IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">member</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The role that should be applied. Note that custom roles must be of the format
`[projects|organizations]/{parent-name}/roles/{role-name}`.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing CryptoKeyIAMMember Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/kms/#CryptoKeyIAMMemberState">CryptoKeyIAMMemberState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/kms/#CryptoKeyIAMMember">CryptoKeyIAMMember</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>condition=None<span class="p">, </span>crypto_key_id=None<span class="p">, </span>etag=None<span class="p">, </span>member=None<span class="p">, </span>role=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetCryptoKeyIAMMember<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#CryptoKeyIAMMemberState">CryptoKeyIAMMemberState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#CryptoKeyIAMMember">CryptoKeyIAMMember</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.CryptoKeyIAMMember.html">CryptoKeyIAMMember</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.CryptoKeyIAMMemberState.html">CryptoKeyIAMMemberState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing CryptoKeyIAMMember resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Condition</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyiammembercondition">Crypto<wbr>Key<wbr>IAMMember<wbr>Condition<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An [IAM Condition](https://cloud.google.com/iam/docs/conditions-overview) for a given binding.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Crypto<wbr>Key<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The crypto key ID, in the form
`{project_id}/{location_name}/{key_ring_name}/{crypto_key_name}` or
`{location_name}/{key_ring_name}/{crypto_key_name}`. In the second form,
the provider&#39;s project setting will be used as a fallback.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Etag</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) The etag of the project&#39;s IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Member</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role that should be applied. Note that custom roles must be of the format
`[projects|organizations]/{parent-name}/roles/{role-name}`.
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
            <td class="align-top">Condition</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyiammembercondition">*Crypto<wbr>Key<wbr>IAMMember<wbr>Condition</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An [IAM Condition](https://cloud.google.com/iam/docs/conditions-overview) for a given binding.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Crypto<wbr>Key<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The crypto key ID, in the form
`{project_id}/{location_name}/{key_ring_name}/{crypto_key_name}` or
`{location_name}/{key_ring_name}/{crypto_key_name}`. In the second form,
the provider&#39;s project setting will be used as a fallback.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Etag</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) The etag of the project&#39;s IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Member</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role that should be applied. Note that custom roles must be of the format
`[projects|organizations]/{parent-name}/roles/{role-name}`.
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
            <td class="align-top">condition</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyiammembercondition">Crypto<wbr>Key<wbr>IAMMember<wbr>Condition?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An [IAM Condition](https://cloud.google.com/iam/docs/conditions-overview) for a given binding.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">crypto<wbr>Key<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The crypto key ID, in the form
`{project_id}/{location_name}/{key_ring_name}/{crypto_key_name}` or
`{location_name}/{key_ring_name}/{crypto_key_name}`. In the second form,
the provider&#39;s project setting will be used as a fallback.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">etag</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) The etag of the project&#39;s IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">member</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role that should be applied. Note that custom roles must be of the format
`[projects|organizations]/{parent-name}/roles/{role-name}`.
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
            <td class="align-top">condition</td>
            <td class="align-top">
                
                <code><a href="#cryptokeyiammembercondition">Dict[Crypto<wbr>Key<wbr>IAMMember<wbr>Condition]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An [IAM Condition](https://cloud.google.com/iam/docs/conditions-overview) for a given binding.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">crypto_<wbr>key_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The crypto key ID, in the form
`{project_id}/{location_name}/{key_ring_name}/{crypto_key_name}` or
`{location_name}/{key_ring_name}/{crypto_key_name}`. In the second form,
the provider&#39;s project setting will be used as a fallback.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">etag</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) The etag of the project&#39;s IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">member</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role that should be applied. Note that custom roles must be of the format
`[projects|organizations]/{parent-name}/roles/{role-name}`.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### CryptoKeyIAMMemberCondition
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#CryptoKeyIAMMemberCondition">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#CryptoKeyIAMMemberCondition">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#CryptoKeyIAMMemberConditionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#CryptoKeyIAMMemberConditionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.CryptoKeyIAMMemberConditionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.CryptoKeyIAMMemberCondition.html">output</a> API doc for this type.
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
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expression</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Title</td>
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
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expression</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Title</td>
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
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expression</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">title</td>
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
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expression</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">title</td>
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









---
title: "Hl7Store"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

A Hl7V2Store is a datastore inside a Healthcare dataset that conforms to the FHIR (https://www.hl7.org/hl7V2/STU3/)
standard for Healthcare information exchange

To get more information about Hl7V2Store, see:

* [API documentation](https://cloud.google.com/healthcare/docs/reference/rest/v1beta1/projects.locations.datasets.hl7V2Stores)
* How-to Guides
    * [Creating a HL7v2 Store](https://cloud.google.com/healthcare/docs/how-tos/hl7v2)

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/healthcare_hl7_v2_store.html.markdown.



## Create a Hl7Store Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/healthcare/#Hl7Store">Hl7Store</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/healthcare/#Hl7StoreArgs">Hl7StoreArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Hl7Store</span><span class="p">(resource_name, opts=None, </span>dataset=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>notification_config=None<span class="p">, </span>parser_config=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewHl7Store<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/healthcare?tab=doc#Hl7StoreArgs">Hl7StoreArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/healthcare?tab=doc#Hl7Store">Hl7Store</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Healthcare.Hl7Store.html">Hl7Store</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Healthcare.Hl7StoreArgs.html">Hl7StoreArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Hl7Store resource with the given unique name, arguments, and options.

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
            <td class="align-top">Dataset</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Identifies the dataset addressed by this request. Must be in the format
&#39;projects/{project}/locations/{location}/datasets/{dataset}&#39;
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
User-supplied key-value pairs used to organize HL7v2 stores. Label keys must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}][\p{Ll}\p{Lo}\p{N}_-]{0,62} Label values are optional, must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}\p{N}_-]{0,63} No more than 64 labels can be associated with a given store. An object containing a list of
&#34;key&#34;: value pairs. Example: { &#34;name&#34;: &#34;wrench&#34;, &#34;mass&#34;: &#34;1.3kg&#34;, &#34;count&#34;: &#34;3&#34; }.
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
The resource name for the Hl7V2Store. ** Changing this property may recreate the Hl7v2 store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storenotificationconfig">Hl7Store<wbr>Notification<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parser<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storeparserconfig">Hl7Store<wbr>Parser<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
            <td class="align-top">Dataset</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Identifies the dataset addressed by this request. Must be in the format
&#39;projects/{project}/locations/{location}/datasets/{dataset}&#39;
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
User-supplied key-value pairs used to organize HL7v2 stores. Label keys must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}][\p{Ll}\p{Lo}\p{N}_-]{0,62} Label values are optional, must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}\p{N}_-]{0,63} No more than 64 labels can be associated with a given store. An object containing a list of
&#34;key&#34;: value pairs. Example: { &#34;name&#34;: &#34;wrench&#34;, &#34;mass&#34;: &#34;1.3kg&#34;, &#34;count&#34;: &#34;3&#34; }.
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
The resource name for the Hl7V2Store. ** Changing this property may recreate the Hl7v2 store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storenotificationconfig">*Hl7Store<wbr>Notification<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parser<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storeparserconfig">*Hl7Store<wbr>Parser<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
            <td class="align-top">dataset</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Identifies the dataset addressed by this request. Must be in the format
&#39;projects/{project}/locations/{location}/datasets/{dataset}&#39;
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
User-supplied key-value pairs used to organize HL7v2 stores. Label keys must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}][\p{Ll}\p{Lo}\p{N}_-]{0,62} Label values are optional, must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}\p{N}_-]{0,63} No more than 64 labels can be associated with a given store. An object containing a list of
&#34;key&#34;: value pairs. Example: { &#34;name&#34;: &#34;wrench&#34;, &#34;mass&#34;: &#34;1.3kg&#34;, &#34;count&#34;: &#34;3&#34; }.
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
The resource name for the Hl7V2Store. ** Changing this property may recreate the Hl7v2 store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storenotificationconfig">Hl7Store<wbr>Notification<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parser<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storeparserconfig">Hl7Store<wbr>Parser<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
            <td class="align-top">dataset</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Identifies the dataset addressed by this request. Must be in the format
&#39;projects/{project}/locations/{location}/datasets/{dataset}&#39;
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
User-supplied key-value pairs used to organize HL7v2 stores. Label keys must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}][\p{Ll}\p{Lo}\p{N}_-]{0,62} Label values are optional, must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}\p{N}_-]{0,63} No more than 64 labels can be associated with a given store. An object containing a list of
&#34;key&#34;: value pairs. Example: { &#34;name&#34;: &#34;wrench&#34;, &#34;mass&#34;: &#34;1.3kg&#34;, &#34;count&#34;: &#34;3&#34; }.
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
The resource name for the Hl7V2Store. ** Changing this property may recreate the Hl7v2 store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#hl7storenotificationconfig">Dict[Hl7Store<wbr>Notification<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parser_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#hl7storeparserconfig">Dict[Hl7Store<wbr>Parser<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Hl7Store Output Properties

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
            <td class="align-top">Dataset</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Identifies the dataset addressed by this request. Must be in the format
&#39;projects/{project}/locations/{location}/datasets/{dataset}&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} User-supplied key-value pairs used to organize HL7v2 stores. Label keys must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}][\p{Ll}\p{Lo}\p{N}_-]{0,62} Label values are optional, must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}\p{N}_-]{0,63} No more than 64 labels can be associated with a given store. An object containing a list of
&#34;key&#34;: value pairs. Example: { &#34;name&#34;: &#34;wrench&#34;, &#34;mass&#34;: &#34;1.3kg&#34;, &#34;count&#34;: &#34;3&#34; }.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The resource name for the Hl7V2Store. ** Changing this property may recreate the Hl7v2 store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storenotificationconfig">Hl7Store<wbr>Notification<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parser<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storeparserconfig">Hl7Store<wbr>Parser<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The fully qualified name of this dataset
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
            <td class="align-top">Dataset</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Identifies the dataset addressed by this request. Must be in the format
&#39;projects/{project}/locations/{location}/datasets/{dataset}&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} User-supplied key-value pairs used to organize HL7v2 stores. Label keys must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}][\p{Ll}\p{Lo}\p{N}_-]{0,62} Label values are optional, must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}\p{N}_-]{0,63} No more than 64 labels can be associated with a given store. An object containing a list of
&#34;key&#34;: value pairs. Example: { &#34;name&#34;: &#34;wrench&#34;, &#34;mass&#34;: &#34;1.3kg&#34;, &#34;count&#34;: &#34;3&#34; }.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The resource name for the Hl7V2Store. ** Changing this property may recreate the Hl7v2 store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storenotificationconfig">*Hl7Store<wbr>Notification<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parser<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storeparserconfig">*Hl7Store<wbr>Parser<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The fully qualified name of this dataset
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
            <td class="align-top">dataset</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Identifies the dataset addressed by this request. Must be in the format
&#39;projects/{project}/locations/{location}/datasets/{dataset}&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} User-supplied key-value pairs used to organize HL7v2 stores. Label keys must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}][\p{Ll}\p{Lo}\p{N}_-]{0,62} Label values are optional, must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}\p{N}_-]{0,63} No more than 64 labels can be associated with a given store. An object containing a list of
&#34;key&#34;: value pairs. Example: { &#34;name&#34;: &#34;wrench&#34;, &#34;mass&#34;: &#34;1.3kg&#34;, &#34;count&#34;: &#34;3&#34; }.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The resource name for the Hl7V2Store. ** Changing this property may recreate the Hl7v2 store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storenotificationconfig">Hl7Store<wbr>Notification<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parser<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storeparserconfig">Hl7Store<wbr>Parser<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The fully qualified name of this dataset
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
            <td class="align-top">dataset</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Identifies the dataset addressed by this request. Must be in the format
&#39;projects/{project}/locations/{location}/datasets/{dataset}&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} User-supplied key-value pairs used to organize HL7v2 stores. Label keys must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}][\p{Ll}\p{Lo}\p{N}_-]{0,62} Label values are optional, must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}\p{N}_-]{0,63} No more than 64 labels can be associated with a given store. An object containing a list of
&#34;key&#34;: value pairs. Example: { &#34;name&#34;: &#34;wrench&#34;, &#34;mass&#34;: &#34;1.3kg&#34;, &#34;count&#34;: &#34;3&#34; }.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The resource name for the Hl7V2Store. ** Changing this property may recreate the Hl7v2 store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#hl7storenotificationconfig">Dict[Hl7Store<wbr>Notification<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parser_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#hl7storeparserconfig">Dict[Hl7Store<wbr>Parser<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self_<wbr>link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The fully qualified name of this dataset
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Hl7Store Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/healthcare/#Hl7StoreState">Hl7StoreState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/healthcare/#Hl7Store">Hl7Store</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>dataset=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>notification_config=None<span class="p">, </span>parser_config=None<span class="p">, </span>self_link=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetHl7Store<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/healthcare?tab=doc#Hl7StoreState">Hl7StoreState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/healthcare?tab=doc#Hl7Store">Hl7Store</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Healthcare.Hl7Store.html">Hl7Store</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Healthcare.Hl7StoreState.html">Hl7StoreState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Hl7Store resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Dataset</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifies the dataset addressed by this request. Must be in the format
&#39;projects/{project}/locations/{location}/datasets/{dataset}&#39;
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
User-supplied key-value pairs used to organize HL7v2 stores. Label keys must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}][\p{Ll}\p{Lo}\p{N}_-]{0,62} Label values are optional, must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}\p{N}_-]{0,63} No more than 64 labels can be associated with a given store. An object containing a list of
&#34;key&#34;: value pairs. Example: { &#34;name&#34;: &#34;wrench&#34;, &#34;mass&#34;: &#34;1.3kg&#34;, &#34;count&#34;: &#34;3&#34; }.
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
The resource name for the Hl7V2Store. ** Changing this property may recreate the Hl7v2 store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storenotificationconfig">Hl7Store<wbr>Notification<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parser<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storeparserconfig">Hl7Store<wbr>Parser<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
The fully qualified name of this dataset
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
            <td class="align-top">Dataset</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifies the dataset addressed by this request. Must be in the format
&#39;projects/{project}/locations/{location}/datasets/{dataset}&#39;
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
User-supplied key-value pairs used to organize HL7v2 stores. Label keys must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}][\p{Ll}\p{Lo}\p{N}_-]{0,62} Label values are optional, must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}\p{N}_-]{0,63} No more than 64 labels can be associated with a given store. An object containing a list of
&#34;key&#34;: value pairs. Example: { &#34;name&#34;: &#34;wrench&#34;, &#34;mass&#34;: &#34;1.3kg&#34;, &#34;count&#34;: &#34;3&#34; }.
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
The resource name for the Hl7V2Store. ** Changing this property may recreate the Hl7v2 store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storenotificationconfig">*Hl7Store<wbr>Notification<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parser<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storeparserconfig">*Hl7Store<wbr>Parser<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
The fully qualified name of this dataset
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
            <td class="align-top">dataset</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifies the dataset addressed by this request. Must be in the format
&#39;projects/{project}/locations/{location}/datasets/{dataset}&#39;
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
User-supplied key-value pairs used to organize HL7v2 stores. Label keys must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}][\p{Ll}\p{Lo}\p{N}_-]{0,62} Label values are optional, must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}\p{N}_-]{0,63} No more than 64 labels can be associated with a given store. An object containing a list of
&#34;key&#34;: value pairs. Example: { &#34;name&#34;: &#34;wrench&#34;, &#34;mass&#34;: &#34;1.3kg&#34;, &#34;count&#34;: &#34;3&#34; }.
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
The resource name for the Hl7V2Store. ** Changing this property may recreate the Hl7v2 store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storenotificationconfig">Hl7Store<wbr>Notification<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parser<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#hl7storeparserconfig">Hl7Store<wbr>Parser<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
The fully qualified name of this dataset
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
            <td class="align-top">dataset</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifies the dataset addressed by this request. Must be in the format
&#39;projects/{project}/locations/{location}/datasets/{dataset}&#39;
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
User-supplied key-value pairs used to organize HL7v2 stores. Label keys must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}][\p{Ll}\p{Lo}\p{N}_-]{0,62} Label values are optional, must be between 1 and 63 characters long, have a
UTF-8 encoding of maximum 128 bytes, and must conform to the following PCRE regular expression:
[\p{Ll}\p{Lo}\p{N}_-]{0,63} No more than 64 labels can be associated with a given store. An object containing a list of
&#34;key&#34;: value pairs. Example: { &#34;name&#34;: &#34;wrench&#34;, &#34;mass&#34;: &#34;1.3kg&#34;, &#34;count&#34;: &#34;3&#34; }.
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
The resource name for the Hl7V2Store. ** Changing this property may recreate the Hl7v2 store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#hl7storenotificationconfig">Dict[Hl7Store<wbr>Notification<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parser_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#hl7storeparserconfig">Dict[Hl7Store<wbr>Parser<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
The fully qualified name of this dataset
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### Hl7StoreNotificationConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#Hl7StoreNotificationConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#Hl7StoreNotificationConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/healthcare?tab=doc#Hl7StoreNotificationConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/healthcare?tab=doc#Hl7StoreNotificationConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Healthcare.Hl7StoreNotificationConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Healthcare.Hl7StoreNotificationConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Pubsub<wbr>Topic</td>
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
            <td class="align-top">Pubsub<wbr>Topic</td>
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
            <td class="align-top">pubsub<wbr>Topic</td>
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
            <td class="align-top">pubsub<wbr>Topic</td>
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





#### Hl7StoreParserConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#Hl7StoreParserConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#Hl7StoreParserConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/healthcare?tab=doc#Hl7StoreParserConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/healthcare?tab=doc#Hl7StoreParserConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Healthcare.Hl7StoreParserConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Healthcare.Hl7StoreParserConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Allow<wbr>Null<wbr>Header</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Segment<wbr>Terminator</td>
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
            <td class="align-top">Allow<wbr>Null<wbr>Header</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Segment<wbr>Terminator</td>
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
            <td class="align-top">allow<wbr>Null<wbr>Header</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">segment<wbr>Terminator</td>
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
            <td class="align-top">allow<wbr>Null<wbr>Header</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">segment<wbr>Terminator</td>
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








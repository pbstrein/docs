
---
title: "FhirStore"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

A FhirStore is a datastore inside a Healthcare dataset that conforms to the FHIR (https://www.hl7.org/fhir/STU3/)
standard for Healthcare information exchange

To get more information about FhirStore, see:

* [API documentation](https://cloud.google.com/healthcare/docs/reference/rest/v1beta1/projects.locations.datasets.fhirStores)
* How-to Guides
    * [Creating a FHIR store](https://cloud.google.com/healthcare/docs/how-tos/fhir)

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/healthcare_fhir_store.html.markdown.



## Create a FhirStore Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/healthcare/#FhirStore">FhirStore</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/healthcare/#FhirStoreArgs">FhirStoreArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">FhirStore</span><span class="p">(resource_name, opts=None, </span>dataset=None<span class="p">, </span>disable_referential_integrity=None<span class="p">, </span>disable_resource_versioning=None<span class="p">, </span>enable_history_import=None<span class="p">, </span>enable_update_create=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>notification_config=None<span class="p">, </span>version=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewFhirStore<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/healthcare?tab=doc#FhirStoreArgs">FhirStoreArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/healthcare?tab=doc#FhirStore">FhirStore</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Healthcare.FhirStore.html">FhirStore</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Healthcare.FhirStoreArgs.html">FhirStoreArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a FhirStore resource with the given unique name, arguments, and options.

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
            <td class="align-top">Disable<wbr>Referential<wbr>Integrity</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable referential integrity in this FHIR store. This field is immutable after FHIR store creation. The
default value is false, meaning that the API will enforce referential integrity and fail the requests that will result
in inconsistent state in the FHIR store. When this field is set to true, the API will skip referential integrity check.
Consequently, operations that rely on references, such as Patient.get$everything, will not return all the results if
broken references exist. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disable<wbr>Resource<wbr>Versioning</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable resource versioning for this FHIR store. This field can not be changed after the creation of FHIR
store. If set to false, which is the default behavior, all write operations will cause historical versions to be
recorded automatically. The historical versions can be fetched through the history APIs, but cannot be updated. If set
to true, no historical versions will be kept. The server will send back errors for attempts to read the historical
versions. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>History<wbr>Import</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to allow the bulk import API to accept history bundles and directly insert historical resource versions into the
FHIR store. Importing resource histories creates resource interactions that appear to have occurred in the past, which
clients may not want to allow. If set to false, history bundles within an import will fail with an error. ** Changing
this property may recreate the FHIR store (removing all data) ** ** This property can be changed manually in the Google
Cloud Healthcare admin console without recreating the FHIR store **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Update<wbr>Create</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this FHIR store has the updateCreate capability. This determines if the client can use an Update operation to
create a new resource with a client-specified ID. If false, all IDs are server-assigned through the Create operation and
attempts to Update a non-existent resource will return errors. Please treat the audit logs with appropriate levels of
care if client-specified resource IDs contain sensitive data such as patient identifiers, those IDs will be part of the
FHIR resource path recorded in Cloud audit logs and Cloud Pub/Sub notifications.
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
User-supplied key-value pairs used to organize FHIR stores. Label keys must be between 1 and 63 characters long, have a
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
The resource name for the FhirStore. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#fhirstorenotificationconfig">Fhir<wbr>Store<wbr>Notification<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FHIR specification version. Supported values include DSTU2, STU3 and R4. Defaults to STU3.
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
            <td class="align-top">Disable<wbr>Referential<wbr>Integrity</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable referential integrity in this FHIR store. This field is immutable after FHIR store creation. The
default value is false, meaning that the API will enforce referential integrity and fail the requests that will result
in inconsistent state in the FHIR store. When this field is set to true, the API will skip referential integrity check.
Consequently, operations that rely on references, such as Patient.get$everything, will not return all the results if
broken references exist. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disable<wbr>Resource<wbr>Versioning</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable resource versioning for this FHIR store. This field can not be changed after the creation of FHIR
store. If set to false, which is the default behavior, all write operations will cause historical versions to be
recorded automatically. The historical versions can be fetched through the history APIs, but cannot be updated. If set
to true, no historical versions will be kept. The server will send back errors for attempts to read the historical
versions. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>History<wbr>Import</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to allow the bulk import API to accept history bundles and directly insert historical resource versions into the
FHIR store. Importing resource histories creates resource interactions that appear to have occurred in the past, which
clients may not want to allow. If set to false, history bundles within an import will fail with an error. ** Changing
this property may recreate the FHIR store (removing all data) ** ** This property can be changed manually in the Google
Cloud Healthcare admin console without recreating the FHIR store **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Update<wbr>Create</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this FHIR store has the updateCreate capability. This determines if the client can use an Update operation to
create a new resource with a client-specified ID. If false, all IDs are server-assigned through the Create operation and
attempts to Update a non-existent resource will return errors. Please treat the audit logs with appropriate levels of
care if client-specified resource IDs contain sensitive data such as patient identifiers, those IDs will be part of the
FHIR resource path recorded in Cloud audit logs and Cloud Pub/Sub notifications.
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
User-supplied key-value pairs used to organize FHIR stores. Label keys must be between 1 and 63 characters long, have a
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
The resource name for the FhirStore. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#fhirstorenotificationconfig">*Fhir<wbr>Store<wbr>Notification<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FHIR specification version. Supported values include DSTU2, STU3 and R4. Defaults to STU3.
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
            <td class="align-top">disable<wbr>Referential<wbr>Integrity</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable referential integrity in this FHIR store. This field is immutable after FHIR store creation. The
default value is false, meaning that the API will enforce referential integrity and fail the requests that will result
in inconsistent state in the FHIR store. When this field is set to true, the API will skip referential integrity check.
Consequently, operations that rely on references, such as Patient.get$everything, will not return all the results if
broken references exist. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disable<wbr>Resource<wbr>Versioning</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable resource versioning for this FHIR store. This field can not be changed after the creation of FHIR
store. If set to false, which is the default behavior, all write operations will cause historical versions to be
recorded automatically. The historical versions can be fetched through the history APIs, but cannot be updated. If set
to true, no historical versions will be kept. The server will send back errors for attempts to read the historical
versions. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>History<wbr>Import</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to allow the bulk import API to accept history bundles and directly insert historical resource versions into the
FHIR store. Importing resource histories creates resource interactions that appear to have occurred in the past, which
clients may not want to allow. If set to false, history bundles within an import will fail with an error. ** Changing
this property may recreate the FHIR store (removing all data) ** ** This property can be changed manually in the Google
Cloud Healthcare admin console without recreating the FHIR store **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Update<wbr>Create</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this FHIR store has the updateCreate capability. This determines if the client can use an Update operation to
create a new resource with a client-specified ID. If false, all IDs are server-assigned through the Create operation and
attempts to Update a non-existent resource will return errors. Please treat the audit logs with appropriate levels of
care if client-specified resource IDs contain sensitive data such as patient identifiers, those IDs will be part of the
FHIR resource path recorded in Cloud audit logs and Cloud Pub/Sub notifications.
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
User-supplied key-value pairs used to organize FHIR stores. Label keys must be between 1 and 63 characters long, have a
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
The resource name for the FhirStore. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#fhirstorenotificationconfig">Fhir<wbr>Store<wbr>Notification<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FHIR specification version. Supported values include DSTU2, STU3 and R4. Defaults to STU3.
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
            <td class="align-top">disable_<wbr>referential_<wbr>integrity</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable referential integrity in this FHIR store. This field is immutable after FHIR store creation. The
default value is false, meaning that the API will enforce referential integrity and fail the requests that will result
in inconsistent state in the FHIR store. When this field is set to true, the API will skip referential integrity check.
Consequently, operations that rely on references, such as Patient.get$everything, will not return all the results if
broken references exist. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disable_<wbr>resource_<wbr>versioning</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable resource versioning for this FHIR store. This field can not be changed after the creation of FHIR
store. If set to false, which is the default behavior, all write operations will cause historical versions to be
recorded automatically. The historical versions can be fetched through the history APIs, but cannot be updated. If set
to true, no historical versions will be kept. The server will send back errors for attempts to read the historical
versions. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>history_<wbr>import</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to allow the bulk import API to accept history bundles and directly insert historical resource versions into the
FHIR store. Importing resource histories creates resource interactions that appear to have occurred in the past, which
clients may not want to allow. If set to false, history bundles within an import will fail with an error. ** Changing
this property may recreate the FHIR store (removing all data) ** ** This property can be changed manually in the Google
Cloud Healthcare admin console without recreating the FHIR store **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>update_<wbr>create</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this FHIR store has the updateCreate capability. This determines if the client can use an Update operation to
create a new resource with a client-specified ID. If false, all IDs are server-assigned through the Create operation and
attempts to Update a non-existent resource will return errors. Please treat the audit logs with appropriate levels of
care if client-specified resource IDs contain sensitive data such as patient identifiers, those IDs will be part of the
FHIR resource path recorded in Cloud audit logs and Cloud Pub/Sub notifications.
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
User-supplied key-value pairs used to organize FHIR stores. Label keys must be between 1 and 63 characters long, have a
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
The resource name for the FhirStore. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#fhirstorenotificationconfig">Dict[Fhir<wbr>Store<wbr>Notification<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FHIR specification version. Supported values include DSTU2, STU3 and R4. Defaults to STU3.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## FhirStore Output Properties

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
            <td class="align-top">Disable<wbr>Referential<wbr>Integrity</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether to disable referential integrity in this FHIR store. This field is immutable after FHIR store creation. The
default value is false, meaning that the API will enforce referential integrity and fail the requests that will result
in inconsistent state in the FHIR store. When this field is set to true, the API will skip referential integrity check.
Consequently, operations that rely on references, such as Patient.get$everything, will not return all the results if
broken references exist. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disable<wbr>Resource<wbr>Versioning</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether to disable resource versioning for this FHIR store. This field can not be changed after the creation of FHIR
store. If set to false, which is the default behavior, all write operations will cause historical versions to be
recorded automatically. The historical versions can be fetched through the history APIs, but cannot be updated. If set
to true, no historical versions will be kept. The server will send back errors for attempts to read the historical
versions. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>History<wbr>Import</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether to allow the bulk import API to accept history bundles and directly insert historical resource versions into the
FHIR store. Importing resource histories creates resource interactions that appear to have occurred in the past, which
clients may not want to allow. If set to false, history bundles within an import will fail with an error. ** Changing
this property may recreate the FHIR store (removing all data) ** ** This property can be changed manually in the Google
Cloud Healthcare admin console without recreating the FHIR store **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Update<wbr>Create</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether this FHIR store has the updateCreate capability. This determines if the client can use an Update operation to
create a new resource with a client-specified ID. If false, all IDs are server-assigned through the Create operation and
attempts to Update a non-existent resource will return errors. Please treat the audit logs with appropriate levels of
care if client-specified resource IDs contain sensitive data such as patient identifiers, those IDs will be part of the
FHIR resource path recorded in Cloud audit logs and Cloud Pub/Sub notifications.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} User-supplied key-value pairs used to organize FHIR stores. Label keys must be between 1 and 63 characters long, have a
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
            <td class="align-top">{{% md %}} The resource name for the FhirStore. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#fhirstorenotificationconfig">Fhir<wbr>Store<wbr>Notification<wbr>Config?</a></code>
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
    
        <tr>
            <td class="align-top">Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The FHIR specification version. Supported values include DSTU2, STU3 and R4. Defaults to STU3.
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
            <td class="align-top">Disable<wbr>Referential<wbr>Integrity</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether to disable referential integrity in this FHIR store. This field is immutable after FHIR store creation. The
default value is false, meaning that the API will enforce referential integrity and fail the requests that will result
in inconsistent state in the FHIR store. When this field is set to true, the API will skip referential integrity check.
Consequently, operations that rely on references, such as Patient.get$everything, will not return all the results if
broken references exist. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disable<wbr>Resource<wbr>Versioning</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether to disable resource versioning for this FHIR store. This field can not be changed after the creation of FHIR
store. If set to false, which is the default behavior, all write operations will cause historical versions to be
recorded automatically. The historical versions can be fetched through the history APIs, but cannot be updated. If set
to true, no historical versions will be kept. The server will send back errors for attempts to read the historical
versions. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>History<wbr>Import</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether to allow the bulk import API to accept history bundles and directly insert historical resource versions into the
FHIR store. Importing resource histories creates resource interactions that appear to have occurred in the past, which
clients may not want to allow. If set to false, history bundles within an import will fail with an error. ** Changing
this property may recreate the FHIR store (removing all data) ** ** This property can be changed manually in the Google
Cloud Healthcare admin console without recreating the FHIR store **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Update<wbr>Create</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether this FHIR store has the updateCreate capability. This determines if the client can use an Update operation to
create a new resource with a client-specified ID. If false, all IDs are server-assigned through the Create operation and
attempts to Update a non-existent resource will return errors. Please treat the audit logs with appropriate levels of
care if client-specified resource IDs contain sensitive data such as patient identifiers, those IDs will be part of the
FHIR resource path recorded in Cloud audit logs and Cloud Pub/Sub notifications.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} User-supplied key-value pairs used to organize FHIR stores. Label keys must be between 1 and 63 characters long, have a
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
            <td class="align-top">{{% md %}} The resource name for the FhirStore. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#fhirstorenotificationconfig">*Fhir<wbr>Store<wbr>Notification<wbr>Config</a></code>
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
    
        <tr>
            <td class="align-top">Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The FHIR specification version. Supported values include DSTU2, STU3 and R4. Defaults to STU3.
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
            <td class="align-top">disable<wbr>Referential<wbr>Integrity</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether to disable referential integrity in this FHIR store. This field is immutable after FHIR store creation. The
default value is false, meaning that the API will enforce referential integrity and fail the requests that will result
in inconsistent state in the FHIR store. When this field is set to true, the API will skip referential integrity check.
Consequently, operations that rely on references, such as Patient.get$everything, will not return all the results if
broken references exist. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disable<wbr>Resource<wbr>Versioning</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether to disable resource versioning for this FHIR store. This field can not be changed after the creation of FHIR
store. If set to false, which is the default behavior, all write operations will cause historical versions to be
recorded automatically. The historical versions can be fetched through the history APIs, but cannot be updated. If set
to true, no historical versions will be kept. The server will send back errors for attempts to read the historical
versions. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>History<wbr>Import</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether to allow the bulk import API to accept history bundles and directly insert historical resource versions into the
FHIR store. Importing resource histories creates resource interactions that appear to have occurred in the past, which
clients may not want to allow. If set to false, history bundles within an import will fail with an error. ** Changing
this property may recreate the FHIR store (removing all data) ** ** This property can be changed manually in the Google
Cloud Healthcare admin console without recreating the FHIR store **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Update<wbr>Create</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether this FHIR store has the updateCreate capability. This determines if the client can use an Update operation to
create a new resource with a client-specified ID. If false, all IDs are server-assigned through the Create operation and
attempts to Update a non-existent resource will return errors. Please treat the audit logs with appropriate levels of
care if client-specified resource IDs contain sensitive data such as patient identifiers, those IDs will be part of the
FHIR resource path recorded in Cloud audit logs and Cloud Pub/Sub notifications.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} User-supplied key-value pairs used to organize FHIR stores. Label keys must be between 1 and 63 characters long, have a
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
            <td class="align-top">{{% md %}} The resource name for the FhirStore. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#fhirstorenotificationconfig">Fhir<wbr>Store<wbr>Notification<wbr>Config?</a></code>
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
    
        <tr>
            <td class="align-top">version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The FHIR specification version. Supported values include DSTU2, STU3 and R4. Defaults to STU3.
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
            <td class="align-top">disable_<wbr>referential_<wbr>integrity</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether to disable referential integrity in this FHIR store. This field is immutable after FHIR store creation. The
default value is false, meaning that the API will enforce referential integrity and fail the requests that will result
in inconsistent state in the FHIR store. When this field is set to true, the API will skip referential integrity check.
Consequently, operations that rely on references, such as Patient.get$everything, will not return all the results if
broken references exist. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disable_<wbr>resource_<wbr>versioning</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether to disable resource versioning for this FHIR store. This field can not be changed after the creation of FHIR
store. If set to false, which is the default behavior, all write operations will cause historical versions to be
recorded automatically. The historical versions can be fetched through the history APIs, but cannot be updated. If set
to true, no historical versions will be kept. The server will send back errors for attempts to read the historical
versions. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>history_<wbr>import</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether to allow the bulk import API to accept history bundles and directly insert historical resource versions into the
FHIR store. Importing resource histories creates resource interactions that appear to have occurred in the past, which
clients may not want to allow. If set to false, history bundles within an import will fail with an error. ** Changing
this property may recreate the FHIR store (removing all data) ** ** This property can be changed manually in the Google
Cloud Healthcare admin console without recreating the FHIR store **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>update_<wbr>create</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether this FHIR store has the updateCreate capability. This determines if the client can use an Update operation to
create a new resource with a client-specified ID. If false, all IDs are server-assigned through the Create operation and
attempts to Update a non-existent resource will return errors. Please treat the audit logs with appropriate levels of
care if client-specified resource IDs contain sensitive data such as patient identifiers, those IDs will be part of the
FHIR resource path recorded in Cloud audit logs and Cloud Pub/Sub notifications.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} User-supplied key-value pairs used to organize FHIR stores. Label keys must be between 1 and 63 characters long, have a
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
            <td class="align-top">{{% md %}} The resource name for the FhirStore. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#fhirstorenotificationconfig">Dict[Fhir<wbr>Store<wbr>Notification<wbr>Config]</a></code>
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
    
        <tr>
            <td class="align-top">version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The FHIR specification version. Supported values include DSTU2, STU3 and R4. Defaults to STU3.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing FhirStore Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/healthcare/#FhirStoreState">FhirStoreState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/healthcare/#FhirStore">FhirStore</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>dataset=None<span class="p">, </span>disable_referential_integrity=None<span class="p">, </span>disable_resource_versioning=None<span class="p">, </span>enable_history_import=None<span class="p">, </span>enable_update_create=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>notification_config=None<span class="p">, </span>self_link=None<span class="p">, </span>version=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetFhirStore<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/healthcare?tab=doc#FhirStoreState">FhirStoreState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/healthcare?tab=doc#FhirStore">FhirStore</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Healthcare.FhirStore.html">FhirStore</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Healthcare.FhirStoreState.html">FhirStoreState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing FhirStore resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Disable<wbr>Referential<wbr>Integrity</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable referential integrity in this FHIR store. This field is immutable after FHIR store creation. The
default value is false, meaning that the API will enforce referential integrity and fail the requests that will result
in inconsistent state in the FHIR store. When this field is set to true, the API will skip referential integrity check.
Consequently, operations that rely on references, such as Patient.get$everything, will not return all the results if
broken references exist. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disable<wbr>Resource<wbr>Versioning</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable resource versioning for this FHIR store. This field can not be changed after the creation of FHIR
store. If set to false, which is the default behavior, all write operations will cause historical versions to be
recorded automatically. The historical versions can be fetched through the history APIs, but cannot be updated. If set
to true, no historical versions will be kept. The server will send back errors for attempts to read the historical
versions. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>History<wbr>Import</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to allow the bulk import API to accept history bundles and directly insert historical resource versions into the
FHIR store. Importing resource histories creates resource interactions that appear to have occurred in the past, which
clients may not want to allow. If set to false, history bundles within an import will fail with an error. ** Changing
this property may recreate the FHIR store (removing all data) ** ** This property can be changed manually in the Google
Cloud Healthcare admin console without recreating the FHIR store **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Update<wbr>Create</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this FHIR store has the updateCreate capability. This determines if the client can use an Update operation to
create a new resource with a client-specified ID. If false, all IDs are server-assigned through the Create operation and
attempts to Update a non-existent resource will return errors. Please treat the audit logs with appropriate levels of
care if client-specified resource IDs contain sensitive data such as patient identifiers, those IDs will be part of the
FHIR resource path recorded in Cloud audit logs and Cloud Pub/Sub notifications.
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
User-supplied key-value pairs used to organize FHIR stores. Label keys must be between 1 and 63 characters long, have a
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
The resource name for the FhirStore. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#fhirstorenotificationconfig">Fhir<wbr>Store<wbr>Notification<wbr>Config<wbr>Args?</a></code>
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
    
        <tr>
            <td class="align-top">Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FHIR specification version. Supported values include DSTU2, STU3 and R4. Defaults to STU3.
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
            <td class="align-top">Disable<wbr>Referential<wbr>Integrity</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable referential integrity in this FHIR store. This field is immutable after FHIR store creation. The
default value is false, meaning that the API will enforce referential integrity and fail the requests that will result
in inconsistent state in the FHIR store. When this field is set to true, the API will skip referential integrity check.
Consequently, operations that rely on references, such as Patient.get$everything, will not return all the results if
broken references exist. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disable<wbr>Resource<wbr>Versioning</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable resource versioning for this FHIR store. This field can not be changed after the creation of FHIR
store. If set to false, which is the default behavior, all write operations will cause historical versions to be
recorded automatically. The historical versions can be fetched through the history APIs, but cannot be updated. If set
to true, no historical versions will be kept. The server will send back errors for attempts to read the historical
versions. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>History<wbr>Import</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to allow the bulk import API to accept history bundles and directly insert historical resource versions into the
FHIR store. Importing resource histories creates resource interactions that appear to have occurred in the past, which
clients may not want to allow. If set to false, history bundles within an import will fail with an error. ** Changing
this property may recreate the FHIR store (removing all data) ** ** This property can be changed manually in the Google
Cloud Healthcare admin console without recreating the FHIR store **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Update<wbr>Create</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this FHIR store has the updateCreate capability. This determines if the client can use an Update operation to
create a new resource with a client-specified ID. If false, all IDs are server-assigned through the Create operation and
attempts to Update a non-existent resource will return errors. Please treat the audit logs with appropriate levels of
care if client-specified resource IDs contain sensitive data such as patient identifiers, those IDs will be part of the
FHIR resource path recorded in Cloud audit logs and Cloud Pub/Sub notifications.
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
User-supplied key-value pairs used to organize FHIR stores. Label keys must be between 1 and 63 characters long, have a
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
The resource name for the FhirStore. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#fhirstorenotificationconfig">*Fhir<wbr>Store<wbr>Notification<wbr>Config</a></code>
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
    
        <tr>
            <td class="align-top">Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FHIR specification version. Supported values include DSTU2, STU3 and R4. Defaults to STU3.
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
            <td class="align-top">disable<wbr>Referential<wbr>Integrity</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable referential integrity in this FHIR store. This field is immutable after FHIR store creation. The
default value is false, meaning that the API will enforce referential integrity and fail the requests that will result
in inconsistent state in the FHIR store. When this field is set to true, the API will skip referential integrity check.
Consequently, operations that rely on references, such as Patient.get$everything, will not return all the results if
broken references exist. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disable<wbr>Resource<wbr>Versioning</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable resource versioning for this FHIR store. This field can not be changed after the creation of FHIR
store. If set to false, which is the default behavior, all write operations will cause historical versions to be
recorded automatically. The historical versions can be fetched through the history APIs, but cannot be updated. If set
to true, no historical versions will be kept. The server will send back errors for attempts to read the historical
versions. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>History<wbr>Import</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to allow the bulk import API to accept history bundles and directly insert historical resource versions into the
FHIR store. Importing resource histories creates resource interactions that appear to have occurred in the past, which
clients may not want to allow. If set to false, history bundles within an import will fail with an error. ** Changing
this property may recreate the FHIR store (removing all data) ** ** This property can be changed manually in the Google
Cloud Healthcare admin console without recreating the FHIR store **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Update<wbr>Create</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this FHIR store has the updateCreate capability. This determines if the client can use an Update operation to
create a new resource with a client-specified ID. If false, all IDs are server-assigned through the Create operation and
attempts to Update a non-existent resource will return errors. Please treat the audit logs with appropriate levels of
care if client-specified resource IDs contain sensitive data such as patient identifiers, those IDs will be part of the
FHIR resource path recorded in Cloud audit logs and Cloud Pub/Sub notifications.
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
User-supplied key-value pairs used to organize FHIR stores. Label keys must be between 1 and 63 characters long, have a
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
The resource name for the FhirStore. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#fhirstorenotificationconfig">Fhir<wbr>Store<wbr>Notification<wbr>Config?</a></code>
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
    
        <tr>
            <td class="align-top">version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FHIR specification version. Supported values include DSTU2, STU3 and R4. Defaults to STU3.
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
            <td class="align-top">disable_<wbr>referential_<wbr>integrity</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable referential integrity in this FHIR store. This field is immutable after FHIR store creation. The
default value is false, meaning that the API will enforce referential integrity and fail the requests that will result
in inconsistent state in the FHIR store. When this field is set to true, the API will skip referential integrity check.
Consequently, operations that rely on references, such as Patient.get$everything, will not return all the results if
broken references exist. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disable_<wbr>resource_<wbr>versioning</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to disable resource versioning for this FHIR store. This field can not be changed after the creation of FHIR
store. If set to false, which is the default behavior, all write operations will cause historical versions to be
recorded automatically. The historical versions can be fetched through the history APIs, but cannot be updated. If set
to true, no historical versions will be kept. The server will send back errors for attempts to read the historical
versions. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>history_<wbr>import</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to allow the bulk import API to accept history bundles and directly insert historical resource versions into the
FHIR store. Importing resource histories creates resource interactions that appear to have occurred in the past, which
clients may not want to allow. If set to false, history bundles within an import will fail with an error. ** Changing
this property may recreate the FHIR store (removing all data) ** ** This property can be changed manually in the Google
Cloud Healthcare admin console without recreating the FHIR store **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>update_<wbr>create</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this FHIR store has the updateCreate capability. This determines if the client can use an Update operation to
create a new resource with a client-specified ID. If false, all IDs are server-assigned through the Create operation and
attempts to Update a non-existent resource will return errors. Please treat the audit logs with appropriate levels of
care if client-specified resource IDs contain sensitive data such as patient identifiers, those IDs will be part of the
FHIR resource path recorded in Cloud audit logs and Cloud Pub/Sub notifications.
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
User-supplied key-value pairs used to organize FHIR stores. Label keys must be between 1 and 63 characters long, have a
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
The resource name for the FhirStore. ** Changing this property may recreate the FHIR store (removing all data) **
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#fhirstorenotificationconfig">Dict[Fhir<wbr>Store<wbr>Notification<wbr>Config]</a></code>
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
    
        <tr>
            <td class="align-top">version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FHIR specification version. Supported values include DSTU2, STU3 and R4. Defaults to STU3.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### FhirStoreNotificationConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#FhirStoreNotificationConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#FhirStoreNotificationConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/healthcare?tab=doc#FhirStoreNotificationConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/healthcare?tab=doc#FhirStoreNotificationConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Healthcare.FhirStoreNotificationConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Healthcare.FhirStoreNotificationConfig.html">output</a> API doc for this type.
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









---
title: "Notification"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Creates a new notification configuration on a specified bucket, establishing a flow of event notifications from GCS to a Cloud Pub/Sub topic.
 For more information see 
[the official documentation](https://cloud.google.com/storage/docs/pubsub-notifications) 
and 
[API](https://cloud.google.com/storage/docs/json_api/v1/notifications).

In order to enable notifications, a special Google Cloud Storage service account unique to the project
must have the IAM permission "projects.topics.publish" for a Cloud Pub/Sub topic in the project. To get the service
account's email address, use the `gcp.storage.getProjectServiceAccount` datasource's `email_address` value, and see below
for an example of enabling notifications by granting the correct IAM permission. See
[the notifications documentation](https://cloud.google.com/storage/docs/gsutil/commands/notification) for more details.

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/storage_notification.html.markdown.



## Create a Notification Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#Notification">Notification</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#NotificationArgs">NotificationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Notification</span><span class="p">(resource_name, opts=None, </span>bucket=None<span class="p">, </span>custom_attributes=None<span class="p">, </span>event_types=None<span class="p">, </span>object_name_prefix=None<span class="p">, </span>payload_format=None<span class="p">, </span>topic=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewNotification<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#NotificationArgs">NotificationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#Notification">Notification</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.Notification.html">Notification</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.NotificationArgs.html">NotificationArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Notification resource with the given unique name, arguments, and options.

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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Attributes</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value attribute pairs to attach to each Cloud PubSub message published for this notification subscription
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Event<wbr>Types</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of event type filters for this notification config. If not specified, Cloud Storage will send notifications for all event types. The valid types are: `&#34;OBJECT_FINALIZE&#34;`, `&#34;OBJECT_METADATA_UPDATE&#34;`, `&#34;OBJECT_DELETE&#34;`, `&#34;OBJECT_ARCHIVE&#34;`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies a prefix path filter for this notification config. Cloud Storage will only send notifications for objects in this bucket whose names begin with the specified prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Payload<wbr>Format</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The desired content of the Payload. One of `&#34;JSON_API_V1&#34;` or `&#34;NONE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Topic</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Cloud PubSub topic to which this subscription publishes. Expects either the 
topic name, assumed to belong to the default GCP provider project, or the project-level name,
i.e. `projects/my-gcp-project/topics/my-topic` or `my-topic`. If the project is not set in the provider,
you will need to use the project-level name.
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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Attributes</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value attribute pairs to attach to each Cloud PubSub message published for this notification subscription
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Event<wbr>Types</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of event type filters for this notification config. If not specified, Cloud Storage will send notifications for all event types. The valid types are: `&#34;OBJECT_FINALIZE&#34;`, `&#34;OBJECT_METADATA_UPDATE&#34;`, `&#34;OBJECT_DELETE&#34;`, `&#34;OBJECT_ARCHIVE&#34;`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies a prefix path filter for this notification config. Cloud Storage will only send notifications for objects in this bucket whose names begin with the specified prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Payload<wbr>Format</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The desired content of the Payload. One of `&#34;JSON_API_V1&#34;` or `&#34;NONE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Topic</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Cloud PubSub topic to which this subscription publishes. Expects either the 
topic name, assumed to belong to the default GCP provider project, or the project-level name,
i.e. `projects/my-gcp-project/topics/my-topic` or `my-topic`. If the project is not set in the provider,
you will need to use the project-level name.
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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom<wbr>Attributes</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value attribute pairs to attach to each Cloud PubSub message published for this notification subscription
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">event<wbr>Types</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of event type filters for this notification config. If not specified, Cloud Storage will send notifications for all event types. The valid types are: `&#34;OBJECT_FINALIZE&#34;`, `&#34;OBJECT_METADATA_UPDATE&#34;`, `&#34;OBJECT_DELETE&#34;`, `&#34;OBJECT_ARCHIVE&#34;`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies a prefix path filter for this notification config. Cloud Storage will only send notifications for objects in this bucket whose names begin with the specified prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">payload<wbr>Format</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The desired content of the Payload. One of `&#34;JSON_API_V1&#34;` or `&#34;NONE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">topic</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Cloud PubSub topic to which this subscription publishes. Expects either the 
topic name, assumed to belong to the default GCP provider project, or the project-level name,
i.e. `projects/my-gcp-project/topics/my-topic` or `my-topic`. If the project is not set in the provider,
you will need to use the project-level name.
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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom_<wbr>attributes</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value attribute pairs to attach to each Cloud PubSub message published for this notification subscription
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">event_<wbr>types</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of event type filters for this notification config. If not specified, Cloud Storage will send notifications for all event types. The valid types are: `&#34;OBJECT_FINALIZE&#34;`, `&#34;OBJECT_METADATA_UPDATE&#34;`, `&#34;OBJECT_DELETE&#34;`, `&#34;OBJECT_ARCHIVE&#34;`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object_<wbr>name_<wbr>prefix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies a prefix path filter for this notification config. Cloud Storage will only send notifications for objects in this bucket whose names begin with the specified prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">payload_<wbr>format</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The desired content of the Payload. One of `&#34;JSON_API_V1&#34;` or `&#34;NONE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">topic</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Cloud PubSub topic to which this subscription publishes. Expects either the 
topic name, assumed to belong to the default GCP provider project, or the project-level name,
i.e. `projects/my-gcp-project/topics/my-topic` or `my-topic`. If the project is not set in the provider,
you will need to use the project-level name.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Notification Output Properties

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
            <td class="align-top">{{% md %}} The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Attributes</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value attribute pairs to attach to each Cloud PubSub message published for this notification subscription
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Event<wbr>Types</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} List of event type filters for this notification config. If not specified, Cloud Storage will send notifications for all event types. The valid types are: `&#34;OBJECT_FINALIZE&#34;`, `&#34;OBJECT_METADATA_UPDATE&#34;`, `&#34;OBJECT_DELETE&#34;`, `&#34;OBJECT_ARCHIVE&#34;`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the created notification.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies a prefix path filter for this notification config. Cloud Storage will only send notifications for objects in this bucket whose names begin with the specified prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Payload<wbr>Format</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The desired content of the Payload. One of `&#34;JSON_API_V1&#34;` or `&#34;NONE&#34;`.
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
            <td class="align-top">Topic</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Cloud PubSub topic to which this subscription publishes. Expects either the 
topic name, assumed to belong to the default GCP provider project, or the project-level name,
i.e. `projects/my-gcp-project/topics/my-topic` or `my-topic`. If the project is not set in the provider,
you will need to use the project-level name.
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
            <td class="align-top">{{% md %}} The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Attributes</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value attribute pairs to attach to each Cloud PubSub message published for this notification subscription
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Event<wbr>Types</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} List of event type filters for this notification config. If not specified, Cloud Storage will send notifications for all event types. The valid types are: `&#34;OBJECT_FINALIZE&#34;`, `&#34;OBJECT_METADATA_UPDATE&#34;`, `&#34;OBJECT_DELETE&#34;`, `&#34;OBJECT_ARCHIVE&#34;`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the created notification.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies a prefix path filter for this notification config. Cloud Storage will only send notifications for objects in this bucket whose names begin with the specified prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Payload<wbr>Format</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The desired content of the Payload. One of `&#34;JSON_API_V1&#34;` or `&#34;NONE&#34;`.
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
            <td class="align-top">Topic</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Cloud PubSub topic to which this subscription publishes. Expects either the 
topic name, assumed to belong to the default GCP provider project, or the project-level name,
i.e. `projects/my-gcp-project/topics/my-topic` or `my-topic`. If the project is not set in the provider,
you will need to use the project-level name.
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
            <td class="align-top">{{% md %}} The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom<wbr>Attributes</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value attribute pairs to attach to each Cloud PubSub message published for this notification subscription
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">event<wbr>Types</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} List of event type filters for this notification config. If not specified, Cloud Storage will send notifications for all event types. The valid types are: `&#34;OBJECT_FINALIZE&#34;`, `&#34;OBJECT_METADATA_UPDATE&#34;`, `&#34;OBJECT_DELETE&#34;`, `&#34;OBJECT_ARCHIVE&#34;`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the created notification.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies a prefix path filter for this notification config. Cloud Storage will only send notifications for objects in this bucket whose names begin with the specified prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">payload<wbr>Format</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The desired content of the Payload. One of `&#34;JSON_API_V1&#34;` or `&#34;NONE&#34;`.
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
            <td class="align-top">topic</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Cloud PubSub topic to which this subscription publishes. Expects either the 
topic name, assumed to belong to the default GCP provider project, or the project-level name,
i.e. `projects/my-gcp-project/topics/my-topic` or `my-topic`. If the project is not set in the provider,
you will need to use the project-level name.
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
            <td class="align-top">{{% md %}} The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom_<wbr>attributes</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value attribute pairs to attach to each Cloud PubSub message published for this notification subscription
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">event_<wbr>types</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} List of event type filters for this notification config. If not specified, Cloud Storage will send notifications for all event types. The valid types are: `&#34;OBJECT_FINALIZE&#34;`, `&#34;OBJECT_METADATA_UPDATE&#34;`, `&#34;OBJECT_DELETE&#34;`, `&#34;OBJECT_ARCHIVE&#34;`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the created notification.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object_<wbr>name_<wbr>prefix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Specifies a prefix path filter for this notification config. Cloud Storage will only send notifications for objects in this bucket whose names begin with the specified prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">payload_<wbr>format</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The desired content of the Payload. One of `&#34;JSON_API_V1&#34;` or `&#34;NONE&#34;`.
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
            <td class="align-top">topic</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Cloud PubSub topic to which this subscription publishes. Expects either the 
topic name, assumed to belong to the default GCP provider project, or the project-level name,
i.e. `projects/my-gcp-project/topics/my-topic` or `my-topic`. If the project is not set in the provider,
you will need to use the project-level name.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Notification Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#NotificationState">NotificationState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#Notification">Notification</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>bucket=None<span class="p">, </span>custom_attributes=None<span class="p">, </span>event_types=None<span class="p">, </span>notification_id=None<span class="p">, </span>object_name_prefix=None<span class="p">, </span>payload_format=None<span class="p">, </span>self_link=None<span class="p">, </span>topic=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetNotification<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#NotificationState">NotificationState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#Notification">Notification</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.Notification.html">Notification</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.NotificationState.html">NotificationState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Notification resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Attributes</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value attribute pairs to attach to each Cloud PubSub message published for this notification subscription
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Event<wbr>Types</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of event type filters for this notification config. If not specified, Cloud Storage will send notifications for all event types. The valid types are: `&#34;OBJECT_FINALIZE&#34;`, `&#34;OBJECT_METADATA_UPDATE&#34;`, `&#34;OBJECT_DELETE&#34;`, `&#34;OBJECT_ARCHIVE&#34;`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the created notification.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies a prefix path filter for this notification config. Cloud Storage will only send notifications for objects in this bucket whose names begin with the specified prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Payload<wbr>Format</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The desired content of the Payload. One of `&#34;JSON_API_V1&#34;` or `&#34;NONE&#34;`.
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
            <td class="align-top">Topic</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Cloud PubSub topic to which this subscription publishes. Expects either the 
topic name, assumed to belong to the default GCP provider project, or the project-level name,
i.e. `projects/my-gcp-project/topics/my-topic` or `my-topic`. If the project is not set in the provider,
you will need to use the project-level name.
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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Attributes</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value attribute pairs to attach to each Cloud PubSub message published for this notification subscription
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Event<wbr>Types</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of event type filters for this notification config. If not specified, Cloud Storage will send notifications for all event types. The valid types are: `&#34;OBJECT_FINALIZE&#34;`, `&#34;OBJECT_METADATA_UPDATE&#34;`, `&#34;OBJECT_DELETE&#34;`, `&#34;OBJECT_ARCHIVE&#34;`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the created notification.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies a prefix path filter for this notification config. Cloud Storage will only send notifications for objects in this bucket whose names begin with the specified prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Payload<wbr>Format</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The desired content of the Payload. One of `&#34;JSON_API_V1&#34;` or `&#34;NONE&#34;`.
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
            <td class="align-top">Topic</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Cloud PubSub topic to which this subscription publishes. Expects either the 
topic name, assumed to belong to the default GCP provider project, or the project-level name,
i.e. `projects/my-gcp-project/topics/my-topic` or `my-topic`. If the project is not set in the provider,
you will need to use the project-level name.
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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom<wbr>Attributes</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value attribute pairs to attach to each Cloud PubSub message published for this notification subscription
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">event<wbr>Types</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of event type filters for this notification config. If not specified, Cloud Storage will send notifications for all event types. The valid types are: `&#34;OBJECT_FINALIZE&#34;`, `&#34;OBJECT_METADATA_UPDATE&#34;`, `&#34;OBJECT_DELETE&#34;`, `&#34;OBJECT_ARCHIVE&#34;`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the created notification.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies a prefix path filter for this notification config. Cloud Storage will only send notifications for objects in this bucket whose names begin with the specified prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">payload<wbr>Format</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The desired content of the Payload. One of `&#34;JSON_API_V1&#34;` or `&#34;NONE&#34;`.
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
            <td class="align-top">topic</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Cloud PubSub topic to which this subscription publishes. Expects either the 
topic name, assumed to belong to the default GCP provider project, or the project-level name,
i.e. `projects/my-gcp-project/topics/my-topic` or `my-topic`. If the project is not set in the provider,
you will need to use the project-level name.
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
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom_<wbr>attributes</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value attribute pairs to attach to each Cloud PubSub message published for this notification subscription
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">event_<wbr>types</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of event type filters for this notification config. If not specified, Cloud Storage will send notifications for all event types. The valid types are: `&#34;OBJECT_FINALIZE&#34;`, `&#34;OBJECT_METADATA_UPDATE&#34;`, `&#34;OBJECT_DELETE&#34;`, `&#34;OBJECT_ARCHIVE&#34;`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the created notification.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object_<wbr>name_<wbr>prefix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies a prefix path filter for this notification config. Cloud Storage will only send notifications for objects in this bucket whose names begin with the specified prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">payload_<wbr>format</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The desired content of the Payload. One of `&#34;JSON_API_V1&#34;` or `&#34;NONE&#34;`.
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
            <td class="align-top">topic</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Cloud PubSub topic to which this subscription publishes. Expects either the 
topic name, assumed to belong to the default GCP provider project, or the project-level name,
i.e. `projects/my-gcp-project/topics/my-topic` or `my-topic`. If the project is not set in the provider,
you will need to use the project-level name.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










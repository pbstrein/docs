
---
title: "EventSubscription"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Manages an EventGrid Event Subscription

> This content is derived from https://github.com/terraform-providers/terraform-provider-azurerm/blob/master/website/docs/r/eventgrid_event_subscription.html.markdown.



## Create a EventSubscription Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/eventgrid/#EventSubscription">EventSubscription</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/eventgrid/#EventSubscriptionArgs">EventSubscriptionArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">EventSubscription</span><span class="p">(resource_name, opts=None, </span>event_delivery_schema=None<span class="p">, </span>eventhub_endpoint=None<span class="p">, </span>hybrid_connection_endpoint=None<span class="p">, </span>included_event_types=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>retry_policy=None<span class="p">, </span>scope=None<span class="p">, </span>storage_blob_dead_letter_destination=None<span class="p">, </span>storage_queue_endpoint=None<span class="p">, </span>subject_filter=None<span class="p">, </span>topic_name=None<span class="p">, </span>webhook_endpoint=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewEventSubscription<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionArgs">EventSubscriptionArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscription">EventSubscription</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscription.html">EventSubscription</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionArgs.html">EventSubscriptionArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a EventSubscription resource with the given unique name, arguments, and options.

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
            <td class="align-top">Event<wbr>Delivery<wbr>Schema</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the event delivery schema for the event subscription. Possible values include: `EventGridSchema`, `CloudEventV01Schema`, `CustomInputSchema`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Eventhub<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptioneventhubendpoint">Event<wbr>Subscription<wbr>Eventhub<wbr>Endpoint<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `eventhub_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Hybrid<wbr>Connection<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionhybridconnectionendpoint">Event<wbr>Subscription<wbr>Hybrid<wbr>Connection<wbr>Endpoint<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `hybrid_connection_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Included<wbr>Event<wbr>Types</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of applicable event types that need to be part of the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of labels to assign to the event subscription.
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
Specifies the name of the EventGrid Event Subscription resource. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retry<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionretrypolicy">Event<wbr>Subscription<wbr>Retry<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `retry_policy` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scope</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the scope at which the EventGrid Event Subscription should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstorageblobdeadletterdestination">Event<wbr>Subscription<wbr>Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_blob_dead_letter_destination` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Queue<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstoragequeueendpoint">Event<wbr>Subscription<wbr>Storage<wbr>Queue<wbr>Endpoint<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_queue_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subject<wbr>Filter</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionsubjectfilter">Event<wbr>Subscription<wbr>Subject<wbr>Filter<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `subject_filter` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Topic<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the name of the topic to associate with the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Webhook<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionwebhookendpoint">Event<wbr>Subscription<wbr>Webhook<wbr>Endpoint<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `webhook_endpoint` block as defined below.
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
            <td class="align-top">Event<wbr>Delivery<wbr>Schema</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the event delivery schema for the event subscription. Possible values include: `EventGridSchema`, `CloudEventV01Schema`, `CustomInputSchema`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Eventhub<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptioneventhubendpoint">*Event<wbr>Subscription<wbr>Eventhub<wbr>Endpoint</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `eventhub_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Hybrid<wbr>Connection<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionhybridconnectionendpoint">*Event<wbr>Subscription<wbr>Hybrid<wbr>Connection<wbr>Endpoint</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `hybrid_connection_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Included<wbr>Event<wbr>Types</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of applicable event types that need to be part of the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of labels to assign to the event subscription.
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
Specifies the name of the EventGrid Event Subscription resource. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retry<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionretrypolicy">*Event<wbr>Subscription<wbr>Retry<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `retry_policy` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scope</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the scope at which the EventGrid Event Subscription should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstorageblobdeadletterdestination">*Event<wbr>Subscription<wbr>Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_blob_dead_letter_destination` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Queue<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstoragequeueendpoint">*Event<wbr>Subscription<wbr>Storage<wbr>Queue<wbr>Endpoint</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_queue_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subject<wbr>Filter</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionsubjectfilter">*Event<wbr>Subscription<wbr>Subject<wbr>Filter</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `subject_filter` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Topic<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the name of the topic to associate with the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Webhook<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionwebhookendpoint">*Event<wbr>Subscription<wbr>Webhook<wbr>Endpoint</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `webhook_endpoint` block as defined below.
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
            <td class="align-top">event<wbr>Delivery<wbr>Schema</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the event delivery schema for the event subscription. Possible values include: `EventGridSchema`, `CloudEventV01Schema`, `CustomInputSchema`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">eventhub<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptioneventhubendpoint">Event<wbr>Subscription<wbr>Eventhub<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `eventhub_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">hybrid<wbr>Connection<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionhybridconnectionendpoint">Event<wbr>Subscription<wbr>Hybrid<wbr>Connection<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `hybrid_connection_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">included<wbr>Event<wbr>Types</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of applicable event types that need to be part of the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of labels to assign to the event subscription.
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
Specifies the name of the EventGrid Event Subscription resource. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retry<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionretrypolicy">Event<wbr>Subscription<wbr>Retry<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `retry_policy` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scope</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the scope at which the EventGrid Event Subscription should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstorageblobdeadletterdestination">Event<wbr>Subscription<wbr>Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_blob_dead_letter_destination` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Queue<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstoragequeueendpoint">Event<wbr>Subscription<wbr>Storage<wbr>Queue<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_queue_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subject<wbr>Filter</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionsubjectfilter">Event<wbr>Subscription<wbr>Subject<wbr>Filter?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `subject_filter` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">topic<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the name of the topic to associate with the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">webhook<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionwebhookendpoint">Event<wbr>Subscription<wbr>Webhook<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `webhook_endpoint` block as defined below.
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
            <td class="align-top">event_<wbr>delivery_<wbr>schema</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the event delivery schema for the event subscription. Possible values include: `EventGridSchema`, `CloudEventV01Schema`, `CustomInputSchema`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">eventhub_<wbr>endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptioneventhubendpoint">Dict[Event<wbr>Subscription<wbr>Eventhub<wbr>Endpoint]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `eventhub_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">hybrid_<wbr>connection_<wbr>endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionhybridconnectionendpoint">Dict[Event<wbr>Subscription<wbr>Hybrid<wbr>Connection<wbr>Endpoint]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `hybrid_connection_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">included_<wbr>event_<wbr>types</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of applicable event types that need to be part of the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of labels to assign to the event subscription.
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
Specifies the name of the EventGrid Event Subscription resource. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retry_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionretrypolicy">Dict[Event<wbr>Subscription<wbr>Retry<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `retry_policy` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scope</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the scope at which the EventGrid Event Subscription should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage_<wbr>blob_<wbr>dead_<wbr>letter_<wbr>destination</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstorageblobdeadletterdestination">Dict[Event<wbr>Subscription<wbr>Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_blob_dead_letter_destination` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage_<wbr>queue_<wbr>endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstoragequeueendpoint">Dict[Event<wbr>Subscription<wbr>Storage<wbr>Queue<wbr>Endpoint]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_queue_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subject_<wbr>filter</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionsubjectfilter">Dict[Event<wbr>Subscription<wbr>Subject<wbr>Filter]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `subject_filter` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">topic_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the name of the topic to associate with the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">webhook_<wbr>endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionwebhookendpoint">Dict[Event<wbr>Subscription<wbr>Webhook<wbr>Endpoint]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `webhook_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## EventSubscription Output Properties

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
            <td class="align-top">Event<wbr>Delivery<wbr>Schema</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the event delivery schema for the event subscription. Possible values include: `EventGridSchema`, `CloudEventV01Schema`, `CustomInputSchema`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Eventhub<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptioneventhubendpoint">Event<wbr>Subscription<wbr>Eventhub<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `eventhub_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Hybrid<wbr>Connection<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionhybridconnectionendpoint">Event<wbr>Subscription<wbr>Hybrid<wbr>Connection<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `hybrid_connection_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Included<wbr>Event<wbr>Types</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} A list of applicable event types that need to be part of the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} A list of labels to assign to the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the EventGrid Event Subscription resource. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retry<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionretrypolicy">Event<wbr>Subscription<wbr>Retry<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} A `retry_policy` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scope</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the scope at which the EventGrid Event Subscription should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstorageblobdeadletterdestination">Event<wbr>Subscription<wbr>Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `storage_blob_dead_letter_destination` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Queue<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstoragequeueendpoint">Event<wbr>Subscription<wbr>Storage<wbr>Queue<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `storage_queue_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subject<wbr>Filter</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionsubjectfilter">Event<wbr>Subscription<wbr>Subject<wbr>Filter?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `subject_filter` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Topic<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the topic to associate with the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Webhook<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionwebhookendpoint">Event<wbr>Subscription<wbr>Webhook<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `webhook_endpoint` block as defined below.
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
            <td class="align-top">Event<wbr>Delivery<wbr>Schema</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the event delivery schema for the event subscription. Possible values include: `EventGridSchema`, `CloudEventV01Schema`, `CustomInputSchema`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Eventhub<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptioneventhubendpoint">*Event<wbr>Subscription<wbr>Eventhub<wbr>Endpoint</a></code>
            </td>
            <td class="align-top">{{% md %}} A `eventhub_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Hybrid<wbr>Connection<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionhybridconnectionendpoint">*Event<wbr>Subscription<wbr>Hybrid<wbr>Connection<wbr>Endpoint</a></code>
            </td>
            <td class="align-top">{{% md %}} A `hybrid_connection_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Included<wbr>Event<wbr>Types</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} A list of applicable event types that need to be part of the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} A list of labels to assign to the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the EventGrid Event Subscription resource. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retry<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionretrypolicy">Event<wbr>Subscription<wbr>Retry<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} A `retry_policy` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scope</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the scope at which the EventGrid Event Subscription should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstorageblobdeadletterdestination">*Event<wbr>Subscription<wbr>Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination</a></code>
            </td>
            <td class="align-top">{{% md %}} A `storage_blob_dead_letter_destination` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Queue<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstoragequeueendpoint">*Event<wbr>Subscription<wbr>Storage<wbr>Queue<wbr>Endpoint</a></code>
            </td>
            <td class="align-top">{{% md %}} A `storage_queue_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subject<wbr>Filter</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionsubjectfilter">*Event<wbr>Subscription<wbr>Subject<wbr>Filter</a></code>
            </td>
            <td class="align-top">{{% md %}} A `subject_filter` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Topic<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the topic to associate with the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Webhook<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionwebhookendpoint">*Event<wbr>Subscription<wbr>Webhook<wbr>Endpoint</a></code>
            </td>
            <td class="align-top">{{% md %}} A `webhook_endpoint` block as defined below.
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
            <td class="align-top">event<wbr>Delivery<wbr>Schema</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the event delivery schema for the event subscription. Possible values include: `EventGridSchema`, `CloudEventV01Schema`, `CustomInputSchema`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">eventhub<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptioneventhubendpoint">Event<wbr>Subscription<wbr>Eventhub<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `eventhub_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">hybrid<wbr>Connection<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionhybridconnectionendpoint">Event<wbr>Subscription<wbr>Hybrid<wbr>Connection<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `hybrid_connection_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">included<wbr>Event<wbr>Types</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} A list of applicable event types that need to be part of the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} A list of labels to assign to the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the EventGrid Event Subscription resource. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retry<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionretrypolicy">Event<wbr>Subscription<wbr>Retry<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} A `retry_policy` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scope</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the scope at which the EventGrid Event Subscription should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstorageblobdeadletterdestination">Event<wbr>Subscription<wbr>Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `storage_blob_dead_letter_destination` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Queue<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstoragequeueendpoint">Event<wbr>Subscription<wbr>Storage<wbr>Queue<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `storage_queue_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subject<wbr>Filter</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionsubjectfilter">Event<wbr>Subscription<wbr>Subject<wbr>Filter?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `subject_filter` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">topic<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the topic to associate with the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">webhook<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionwebhookendpoint">Event<wbr>Subscription<wbr>Webhook<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `webhook_endpoint` block as defined below.
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
            <td class="align-top">event_<wbr>delivery_<wbr>schema</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the event delivery schema for the event subscription. Possible values include: `EventGridSchema`, `CloudEventV01Schema`, `CustomInputSchema`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">eventhub_<wbr>endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptioneventhubendpoint">Dict[Event<wbr>Subscription<wbr>Eventhub<wbr>Endpoint]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `eventhub_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">hybrid_<wbr>connection_<wbr>endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionhybridconnectionendpoint">Dict[Event<wbr>Subscription<wbr>Hybrid<wbr>Connection<wbr>Endpoint]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `hybrid_connection_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">included_<wbr>event_<wbr>types</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} A list of applicable event types that need to be part of the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} A list of labels to assign to the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the EventGrid Event Subscription resource. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retry_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionretrypolicy">Dict[Event<wbr>Subscription<wbr>Retry<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `retry_policy` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scope</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the scope at which the EventGrid Event Subscription should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage_<wbr>blob_<wbr>dead_<wbr>letter_<wbr>destination</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstorageblobdeadletterdestination">Dict[Event<wbr>Subscription<wbr>Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `storage_blob_dead_letter_destination` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage_<wbr>queue_<wbr>endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstoragequeueendpoint">Dict[Event<wbr>Subscription<wbr>Storage<wbr>Queue<wbr>Endpoint]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `storage_queue_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subject_<wbr>filter</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionsubjectfilter">Dict[Event<wbr>Subscription<wbr>Subject<wbr>Filter]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `subject_filter` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">topic_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the topic to associate with the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">webhook_<wbr>endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionwebhookendpoint">Dict[Event<wbr>Subscription<wbr>Webhook<wbr>Endpoint]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `webhook_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing EventSubscription Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/eventgrid/#EventSubscriptionState">EventSubscriptionState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/eventgrid/#EventSubscription">EventSubscription</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>event_delivery_schema=None<span class="p">, </span>eventhub_endpoint=None<span class="p">, </span>hybrid_connection_endpoint=None<span class="p">, </span>included_event_types=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>retry_policy=None<span class="p">, </span>scope=None<span class="p">, </span>storage_blob_dead_letter_destination=None<span class="p">, </span>storage_queue_endpoint=None<span class="p">, </span>subject_filter=None<span class="p">, </span>topic_name=None<span class="p">, </span>webhook_endpoint=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetEventSubscription<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionState">EventSubscriptionState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscription">EventSubscription</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscription.html">EventSubscription</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionState.html">EventSubscriptionState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing EventSubscription resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Event<wbr>Delivery<wbr>Schema</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the event delivery schema for the event subscription. Possible values include: `EventGridSchema`, `CloudEventV01Schema`, `CustomInputSchema`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Eventhub<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptioneventhubendpoint">Event<wbr>Subscription<wbr>Eventhub<wbr>Endpoint<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `eventhub_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Hybrid<wbr>Connection<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionhybridconnectionendpoint">Event<wbr>Subscription<wbr>Hybrid<wbr>Connection<wbr>Endpoint<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `hybrid_connection_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Included<wbr>Event<wbr>Types</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of applicable event types that need to be part of the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of labels to assign to the event subscription.
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
Specifies the name of the EventGrid Event Subscription resource. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retry<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionretrypolicy">Event<wbr>Subscription<wbr>Retry<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `retry_policy` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scope</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the scope at which the EventGrid Event Subscription should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstorageblobdeadletterdestination">Event<wbr>Subscription<wbr>Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_blob_dead_letter_destination` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Queue<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstoragequeueendpoint">Event<wbr>Subscription<wbr>Storage<wbr>Queue<wbr>Endpoint<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_queue_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subject<wbr>Filter</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionsubjectfilter">Event<wbr>Subscription<wbr>Subject<wbr>Filter<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `subject_filter` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Topic<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the name of the topic to associate with the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Webhook<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionwebhookendpoint">Event<wbr>Subscription<wbr>Webhook<wbr>Endpoint<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `webhook_endpoint` block as defined below.
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
            <td class="align-top">Event<wbr>Delivery<wbr>Schema</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the event delivery schema for the event subscription. Possible values include: `EventGridSchema`, `CloudEventV01Schema`, `CustomInputSchema`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Eventhub<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptioneventhubendpoint">*Event<wbr>Subscription<wbr>Eventhub<wbr>Endpoint</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `eventhub_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Hybrid<wbr>Connection<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionhybridconnectionendpoint">*Event<wbr>Subscription<wbr>Hybrid<wbr>Connection<wbr>Endpoint</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `hybrid_connection_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Included<wbr>Event<wbr>Types</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of applicable event types that need to be part of the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of labels to assign to the event subscription.
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
Specifies the name of the EventGrid Event Subscription resource. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retry<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionretrypolicy">*Event<wbr>Subscription<wbr>Retry<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `retry_policy` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scope</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the scope at which the EventGrid Event Subscription should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstorageblobdeadletterdestination">*Event<wbr>Subscription<wbr>Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_blob_dead_letter_destination` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Queue<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstoragequeueendpoint">*Event<wbr>Subscription<wbr>Storage<wbr>Queue<wbr>Endpoint</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_queue_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subject<wbr>Filter</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionsubjectfilter">*Event<wbr>Subscription<wbr>Subject<wbr>Filter</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `subject_filter` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Topic<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the name of the topic to associate with the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Webhook<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionwebhookendpoint">*Event<wbr>Subscription<wbr>Webhook<wbr>Endpoint</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `webhook_endpoint` block as defined below.
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
            <td class="align-top">event<wbr>Delivery<wbr>Schema</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the event delivery schema for the event subscription. Possible values include: `EventGridSchema`, `CloudEventV01Schema`, `CustomInputSchema`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">eventhub<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptioneventhubendpoint">Event<wbr>Subscription<wbr>Eventhub<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `eventhub_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">hybrid<wbr>Connection<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionhybridconnectionendpoint">Event<wbr>Subscription<wbr>Hybrid<wbr>Connection<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `hybrid_connection_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">included<wbr>Event<wbr>Types</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of applicable event types that need to be part of the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of labels to assign to the event subscription.
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
Specifies the name of the EventGrid Event Subscription resource. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retry<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionretrypolicy">Event<wbr>Subscription<wbr>Retry<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `retry_policy` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scope</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the scope at which the EventGrid Event Subscription should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstorageblobdeadletterdestination">Event<wbr>Subscription<wbr>Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_blob_dead_letter_destination` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Queue<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstoragequeueendpoint">Event<wbr>Subscription<wbr>Storage<wbr>Queue<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_queue_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subject<wbr>Filter</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionsubjectfilter">Event<wbr>Subscription<wbr>Subject<wbr>Filter?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `subject_filter` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">topic<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the name of the topic to associate with the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">webhook<wbr>Endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionwebhookendpoint">Event<wbr>Subscription<wbr>Webhook<wbr>Endpoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `webhook_endpoint` block as defined below.
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
            <td class="align-top">event_<wbr>delivery_<wbr>schema</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the event delivery schema for the event subscription. Possible values include: `EventGridSchema`, `CloudEventV01Schema`, `CustomInputSchema`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">eventhub_<wbr>endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptioneventhubendpoint">Dict[Event<wbr>Subscription<wbr>Eventhub<wbr>Endpoint]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `eventhub_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">hybrid_<wbr>connection_<wbr>endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionhybridconnectionendpoint">Dict[Event<wbr>Subscription<wbr>Hybrid<wbr>Connection<wbr>Endpoint]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `hybrid_connection_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">included_<wbr>event_<wbr>types</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of applicable event types that need to be part of the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of labels to assign to the event subscription.
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
Specifies the name of the EventGrid Event Subscription resource. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retry_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionretrypolicy">Dict[Event<wbr>Subscription<wbr>Retry<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `retry_policy` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scope</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the scope at which the EventGrid Event Subscription should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage_<wbr>blob_<wbr>dead_<wbr>letter_<wbr>destination</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstorageblobdeadletterdestination">Dict[Event<wbr>Subscription<wbr>Storage<wbr>Blob<wbr>Dead<wbr>Letter<wbr>Destination]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_blob_dead_letter_destination` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage_<wbr>queue_<wbr>endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionstoragequeueendpoint">Dict[Event<wbr>Subscription<wbr>Storage<wbr>Queue<wbr>Endpoint]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `storage_queue_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subject_<wbr>filter</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionsubjectfilter">Dict[Event<wbr>Subscription<wbr>Subject<wbr>Filter]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `subject_filter` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">topic_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the name of the topic to associate with the event subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">webhook_<wbr>endpoint</td>
            <td class="align-top">
                
                <code><a href="#eventsubscriptionwebhookendpoint">Dict[Event<wbr>Subscription<wbr>Webhook<wbr>Endpoint]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `webhook_endpoint` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### EventSubscriptionEventhubEndpoint
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#EventSubscriptionEventhubEndpoint">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#EventSubscriptionEventhubEndpoint">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionEventhubEndpointArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionEventhubEndpointOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionEventhubEndpointArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionEventhubEndpoint.html">output</a> API doc for this type.
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
            <td class="align-top">Eventhub<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the eventhub where the Event Subscription will receive events.
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
            <td class="align-top">Eventhub<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the eventhub where the Event Subscription will receive events.
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
            <td class="align-top">eventhub<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the eventhub where the Event Subscription will receive events.
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
            <td class="align-top">eventhub_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the eventhub where the Event Subscription will receive events.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### EventSubscriptionHybridConnectionEndpoint
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#EventSubscriptionHybridConnectionEndpoint">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#EventSubscriptionHybridConnectionEndpoint">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionHybridConnectionEndpointArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionHybridConnectionEndpointOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionHybridConnectionEndpointArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionHybridConnectionEndpoint.html">output</a> API doc for this type.
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
            <td class="align-top">Hybrid<wbr>Connection<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the hybrid connection where the Event Subscription will receive events.
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
            <td class="align-top">Hybrid<wbr>Connection<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the hybrid connection where the Event Subscription will receive events.
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
            <td class="align-top">hybrid<wbr>Connection<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the hybrid connection where the Event Subscription will receive events.
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
            <td class="align-top">hybrid<wbr>Connection<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the hybrid connection where the Event Subscription will receive events.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### EventSubscriptionRetryPolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#EventSubscriptionRetryPolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#EventSubscriptionRetryPolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionRetryPolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionRetryPolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionRetryPolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionRetryPolicy.html">output</a> API doc for this type.
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
            <td class="align-top">Event<wbr>Time<wbr>To<wbr>Live</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the time to live (in minutes) for events.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Delivery<wbr>Attempts</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the maximum number of delivery retry attempts for events.
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
            <td class="align-top">Event<wbr>Time<wbr>To<wbr>Live</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the time to live (in minutes) for events.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Delivery<wbr>Attempts</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the maximum number of delivery retry attempts for events.
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
            <td class="align-top">event<wbr>Time<wbr>To<wbr>Live</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the time to live (in minutes) for events.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Delivery<wbr>Attempts</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the maximum number of delivery retry attempts for events.
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
            <td class="align-top">event<wbr>Time<wbr>To<wbr>Live</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the time to live (in minutes) for events.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Delivery<wbr>Attempts</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the maximum number of delivery retry attempts for events.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### EventSubscriptionStorageBlobDeadLetterDestination
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#EventSubscriptionStorageBlobDeadLetterDestination">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#EventSubscriptionStorageBlobDeadLetterDestination">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionStorageBlobDeadLetterDestinationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionStorageBlobDeadLetterDestinationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionStorageBlobDeadLetterDestinationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionStorageBlobDeadLetterDestination.html">output</a> API doc for this type.
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
            <td class="align-top">Storage<wbr>Account<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the storage account id where the storage blob is located.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Blob<wbr>Container<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the name of the Storage blob container that is the destination of the deadletter events
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
            <td class="align-top">Storage<wbr>Account<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the storage account id where the storage blob is located.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Blob<wbr>Container<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the name of the Storage blob container that is the destination of the deadletter events
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
            <td class="align-top">storage<wbr>Account<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the storage account id where the storage blob is located.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Blob<wbr>Container<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the name of the Storage blob container that is the destination of the deadletter events
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
            <td class="align-top">storage_<wbr>account_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the storage account id where the storage blob is located.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Blob<wbr>Container<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the name of the Storage blob container that is the destination of the deadletter events
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### EventSubscriptionStorageQueueEndpoint
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#EventSubscriptionStorageQueueEndpoint">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#EventSubscriptionStorageQueueEndpoint">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionStorageQueueEndpointArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionStorageQueueEndpointOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionStorageQueueEndpointArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionStorageQueueEndpoint.html">output</a> API doc for this type.
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
            <td class="align-top">Queue<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the name of the storage queue where the Event Subscriptio will receive events.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Account<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the storage account id where the storage blob is located.
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
            <td class="align-top">Queue<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the name of the storage queue where the Event Subscriptio will receive events.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Account<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the storage account id where the storage blob is located.
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
            <td class="align-top">queue<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the name of the storage queue where the Event Subscriptio will receive events.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Account<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the storage account id where the storage blob is located.
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
            <td class="align-top">queue_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the name of the storage queue where the Event Subscriptio will receive events.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage_<wbr>account_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the id of the storage account id where the storage blob is located.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### EventSubscriptionSubjectFilter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#EventSubscriptionSubjectFilter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#EventSubscriptionSubjectFilter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionSubjectFilterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionSubjectFilterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionSubjectFilterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionSubjectFilter.html">output</a> API doc for this type.
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
            <td class="align-top">Case<wbr>Sensitive</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies if `subject_begins_with` and `subject_ends_with` case sensitive. This value defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subject<wbr>Begins<wbr>With</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A string to filter events for an event subscription based on a resource path prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subject<wbr>Ends<wbr>With</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A string to filter events for an event subscription based on a resource path suffix.
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
            <td class="align-top">Case<wbr>Sensitive</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies if `subject_begins_with` and `subject_ends_with` case sensitive. This value defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subject<wbr>Begins<wbr>With</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A string to filter events for an event subscription based on a resource path prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subject<wbr>Ends<wbr>With</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A string to filter events for an event subscription based on a resource path suffix.
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
            <td class="align-top">case<wbr>Sensitive</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies if `subject_begins_with` and `subject_ends_with` case sensitive. This value defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subject<wbr>Begins<wbr>With</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A string to filter events for an event subscription based on a resource path prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subject<wbr>Ends<wbr>With</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A string to filter events for an event subscription based on a resource path suffix.
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
            <td class="align-top">case<wbr>Sensitive</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies if `subject_begins_with` and `subject_ends_with` case sensitive. This value defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subject<wbr>Begins<wbr>With</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A string to filter events for an event subscription based on a resource path prefix.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subject<wbr>Ends<wbr>With</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A string to filter events for an event subscription based on a resource path suffix.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### EventSubscriptionWebhookEndpoint
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#EventSubscriptionWebhookEndpoint">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#EventSubscriptionWebhookEndpoint">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionWebhookEndpointArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/eventgrid?tab=doc#EventSubscriptionWebhookEndpointOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionWebhookEndpointArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Eventgrid.EventSubscriptionWebhookEndpoint.html">output</a> API doc for this type.
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
            <td class="align-top">Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the url of the webhook where the Event Subscription will receive events.
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
            <td class="align-top">Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the url of the webhook where the Event Subscription will receive events.
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
            <td class="align-top">url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the url of the webhook where the Event Subscription will receive events.
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
            <td class="align-top">url</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the url of the webhook where the Event Subscription will receive events.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








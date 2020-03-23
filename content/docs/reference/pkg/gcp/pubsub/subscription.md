
---
title: "Subscription"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a Subscription Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/pubsub/#Subscription">Subscription</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/pubsub/#SubscriptionArgs">SubscriptionArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Subscription</span><span class="p">(resource_name, opts=None, </span>ack_deadline_seconds=None<span class="p">, </span>expiration_policy=None<span class="p">, </span>labels=None<span class="p">, </span>message_retention_duration=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>push_config=None<span class="p">, </span>retain_acked_messages=None<span class="p">, </span>topic=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewSubscription<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/pubsub?tab=doc#SubscriptionArgs">SubscriptionArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/pubsub?tab=doc#Subscription">Subscription</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Pubsub.Subscription.html">Subscription</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Pubsub.SubscriptionArgs.html">SubscriptionArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Subscription resource with the given unique name, arguments, and options.

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
            <td class="align-top">Ack<wbr>Deadline<wbr>Seconds</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the
message. After message delivery but before the ack deadline expires and before the message is acknowledged, it is an
outstanding message and will not be delivered again during that time (on a best-effort basis). For pull subscriptions,
this value is used as the initial value for the ack deadline. To override this value for a given message, call
subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify
is 10 seconds. The maximum custom deadline you can specify is 600 seconds (10 minutes). If this parameter is 0, a
default value of 10 seconds is used. For push delivery, this value is also used to set the request timeout for the call
to the push endpoint. If the subscriber never acknowledges the message, the Pub/Sub system will eventually redeliver the
message.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expiration<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#subscriptionexpirationpolicy">Subscription<wbr>Expiration<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A policy that specifies the conditions for this subscription&#39;s expiration. A subscription is considered active as long
as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the
subscription. If expirationPolicy is not set, a default policy with ttl of 31 days will be used. If it is set but ttl is
&#34;&#34;, the resource never expires. The minimum allowed value for expirationPolicy.ttl is 1 day.
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
A set of key/value label pairs to assign to this Subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Message<wbr>Retention<wbr>Duration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How long to retain unacknowledged messages in the subscription&#39;s backlog, from the moment a message is published. If
retainAckedMessages is true, then this also configures the retention of acknowledged messages, and thus configures how
far back in time a subscriptions.seek can be done. Defaults to 7 days. Cannot be more than 7 days (&#39;&#34;604800s&#34;&#39;) or less
than 10 minutes (&#39;&#34;600s&#34;&#39;). A duration in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example:
&#39;&#34;600.5s&#34;&#39;.
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
Name of the subscription.
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
            <td class="align-top">Push<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfig">Subscription<wbr>Push<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If push delivery is used with this subscription, this field is used to configure it. An empty pushConfig signifies that
the subscriber will pull and ack messages using API methods.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retain<wbr>Acked<wbr>Messages</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether to retain acknowledged messages. If &#39;true&#39;, then messages are not expunged from the subscription&#39;s
backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.
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
A reference to a Topic resource.
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
            <td class="align-top">Ack<wbr>Deadline<wbr>Seconds</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the
message. After message delivery but before the ack deadline expires and before the message is acknowledged, it is an
outstanding message and will not be delivered again during that time (on a best-effort basis). For pull subscriptions,
this value is used as the initial value for the ack deadline. To override this value for a given message, call
subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify
is 10 seconds. The maximum custom deadline you can specify is 600 seconds (10 minutes). If this parameter is 0, a
default value of 10 seconds is used. For push delivery, this value is also used to set the request timeout for the call
to the push endpoint. If the subscriber never acknowledges the message, the Pub/Sub system will eventually redeliver the
message.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expiration<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#subscriptionexpirationpolicy">*Subscription<wbr>Expiration<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A policy that specifies the conditions for this subscription&#39;s expiration. A subscription is considered active as long
as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the
subscription. If expirationPolicy is not set, a default policy with ttl of 31 days will be used. If it is set but ttl is
&#34;&#34;, the resource never expires. The minimum allowed value for expirationPolicy.ttl is 1 day.
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
A set of key/value label pairs to assign to this Subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Message<wbr>Retention<wbr>Duration</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How long to retain unacknowledged messages in the subscription&#39;s backlog, from the moment a message is published. If
retainAckedMessages is true, then this also configures the retention of acknowledged messages, and thus configures how
far back in time a subscriptions.seek can be done. Defaults to 7 days. Cannot be more than 7 days (&#39;&#34;604800s&#34;&#39;) or less
than 10 minutes (&#39;&#34;600s&#34;&#39;). A duration in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example:
&#39;&#34;600.5s&#34;&#39;.
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
Name of the subscription.
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
            <td class="align-top">Push<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfig">*Subscription<wbr>Push<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If push delivery is used with this subscription, this field is used to configure it. An empty pushConfig signifies that
the subscriber will pull and ack messages using API methods.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retain<wbr>Acked<wbr>Messages</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether to retain acknowledged messages. If &#39;true&#39;, then messages are not expunged from the subscription&#39;s
backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.
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
A reference to a Topic resource.
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
            <td class="align-top">ack<wbr>Deadline<wbr>Seconds</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the
message. After message delivery but before the ack deadline expires and before the message is acknowledged, it is an
outstanding message and will not be delivered again during that time (on a best-effort basis). For pull subscriptions,
this value is used as the initial value for the ack deadline. To override this value for a given message, call
subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify
is 10 seconds. The maximum custom deadline you can specify is 600 seconds (10 minutes). If this parameter is 0, a
default value of 10 seconds is used. For push delivery, this value is also used to set the request timeout for the call
to the push endpoint. If the subscriber never acknowledges the message, the Pub/Sub system will eventually redeliver the
message.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expiration<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#subscriptionexpirationpolicy">Subscription<wbr>Expiration<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A policy that specifies the conditions for this subscription&#39;s expiration. A subscription is considered active as long
as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the
subscription. If expirationPolicy is not set, a default policy with ttl of 31 days will be used. If it is set but ttl is
&#34;&#34;, the resource never expires. The minimum allowed value for expirationPolicy.ttl is 1 day.
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
A set of key/value label pairs to assign to this Subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">message<wbr>Retention<wbr>Duration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How long to retain unacknowledged messages in the subscription&#39;s backlog, from the moment a message is published. If
retainAckedMessages is true, then this also configures the retention of acknowledged messages, and thus configures how
far back in time a subscriptions.seek can be done. Defaults to 7 days. Cannot be more than 7 days (&#39;&#34;604800s&#34;&#39;) or less
than 10 minutes (&#39;&#34;600s&#34;&#39;). A duration in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example:
&#39;&#34;600.5s&#34;&#39;.
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
Name of the subscription.
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
            <td class="align-top">push<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfig">Subscription<wbr>Push<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If push delivery is used with this subscription, this field is used to configure it. An empty pushConfig signifies that
the subscriber will pull and ack messages using API methods.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retain<wbr>Acked<wbr>Messages</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether to retain acknowledged messages. If &#39;true&#39;, then messages are not expunged from the subscription&#39;s
backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.
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
A reference to a Topic resource.
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
            <td class="align-top">ack_<wbr>deadline_<wbr>seconds</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the
message. After message delivery but before the ack deadline expires and before the message is acknowledged, it is an
outstanding message and will not be delivered again during that time (on a best-effort basis). For pull subscriptions,
this value is used as the initial value for the ack deadline. To override this value for a given message, call
subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify
is 10 seconds. The maximum custom deadline you can specify is 600 seconds (10 minutes). If this parameter is 0, a
default value of 10 seconds is used. For push delivery, this value is also used to set the request timeout for the call
to the push endpoint. If the subscriber never acknowledges the message, the Pub/Sub system will eventually redeliver the
message.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expiration_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#subscriptionexpirationpolicy">Dict[Subscription<wbr>Expiration<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A policy that specifies the conditions for this subscription&#39;s expiration. A subscription is considered active as long
as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the
subscription. If expirationPolicy is not set, a default policy with ttl of 31 days will be used. If it is set but ttl is
&#34;&#34;, the resource never expires. The minimum allowed value for expirationPolicy.ttl is 1 day.
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
A set of key/value label pairs to assign to this Subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">message_<wbr>retention_<wbr>duration</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How long to retain unacknowledged messages in the subscription&#39;s backlog, from the moment a message is published. If
retainAckedMessages is true, then this also configures the retention of acknowledged messages, and thus configures how
far back in time a subscriptions.seek can be done. Defaults to 7 days. Cannot be more than 7 days (&#39;&#34;604800s&#34;&#39;) or less
than 10 minutes (&#39;&#34;600s&#34;&#39;). A duration in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example:
&#39;&#34;600.5s&#34;&#39;.
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
Name of the subscription.
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
            <td class="align-top">push_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfig">Dict[Subscription<wbr>Push<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If push delivery is used with this subscription, this field is used to configure it. An empty pushConfig signifies that
the subscriber will pull and ack messages using API methods.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retain_<wbr>acked_<wbr>messages</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether to retain acknowledged messages. If &#39;true&#39;, then messages are not expunged from the subscription&#39;s
backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.
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
A reference to a Topic resource.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Subscription Output Properties

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
            <td class="align-top">Ack<wbr>Deadline<wbr>Seconds</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the
message. After message delivery but before the ack deadline expires and before the message is acknowledged, it is an
outstanding message and will not be delivered again during that time (on a best-effort basis). For pull subscriptions,
this value is used as the initial value for the ack deadline. To override this value for a given message, call
subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify
is 10 seconds. The maximum custom deadline you can specify is 600 seconds (10 minutes). If this parameter is 0, a
default value of 10 seconds is used. For push delivery, this value is also used to set the request timeout for the call
to the push endpoint. If the subscriber never acknowledges the message, the Pub/Sub system will eventually redeliver the
message.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expiration<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#subscriptionexpirationpolicy">Subscription<wbr>Expiration<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} A policy that specifies the conditions for this subscription&#39;s expiration. A subscription is considered active as long
as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the
subscription. If expirationPolicy is not set, a default policy with ttl of 31 days will be used. If it is set but ttl is
&#34;&#34;, the resource never expires. The minimum allowed value for expirationPolicy.ttl is 1 day.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to this Subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Message<wbr>Retention<wbr>Duration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} How long to retain unacknowledged messages in the subscription&#39;s backlog, from the moment a message is published. If
retainAckedMessages is true, then this also configures the retention of acknowledged messages, and thus configures how
far back in time a subscriptions.seek can be done. Defaults to 7 days. Cannot be more than 7 days (&#39;&#34;604800s&#34;&#39;) or less
than 10 minutes (&#39;&#34;600s&#34;&#39;). A duration in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example:
&#39;&#34;600.5s&#34;&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Path</td>
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
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Push<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfig">Subscription<wbr>Push<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} If push delivery is used with this subscription, this field is used to configure it. An empty pushConfig signifies that
the subscriber will pull and ack messages using API methods.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retain<wbr>Acked<wbr>Messages</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether to retain acknowledged messages. If &#39;true&#39;, then messages are not expunged from the subscription&#39;s
backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Topic</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A reference to a Topic resource.
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
            <td class="align-top">Ack<wbr>Deadline<wbr>Seconds</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the
message. After message delivery but before the ack deadline expires and before the message is acknowledged, it is an
outstanding message and will not be delivered again during that time (on a best-effort basis). For pull subscriptions,
this value is used as the initial value for the ack deadline. To override this value for a given message, call
subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify
is 10 seconds. The maximum custom deadline you can specify is 600 seconds (10 minutes). If this parameter is 0, a
default value of 10 seconds is used. For push delivery, this value is also used to set the request timeout for the call
to the push endpoint. If the subscriber never acknowledges the message, the Pub/Sub system will eventually redeliver the
message.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expiration<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#subscriptionexpirationpolicy">Subscription<wbr>Expiration<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} A policy that specifies the conditions for this subscription&#39;s expiration. A subscription is considered active as long
as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the
subscription. If expirationPolicy is not set, a default policy with ttl of 31 days will be used. If it is set but ttl is
&#34;&#34;, the resource never expires. The minimum allowed value for expirationPolicy.ttl is 1 day.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to this Subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Message<wbr>Retention<wbr>Duration</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} How long to retain unacknowledged messages in the subscription&#39;s backlog, from the moment a message is published. If
retainAckedMessages is true, then this also configures the retention of acknowledged messages, and thus configures how
far back in time a subscriptions.seek can be done. Defaults to 7 days. Cannot be more than 7 days (&#39;&#34;604800s&#34;&#39;) or less
than 10 minutes (&#39;&#34;600s&#34;&#39;). A duration in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example:
&#39;&#34;600.5s&#34;&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Path</td>
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
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Push<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfig">*Subscription<wbr>Push<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} If push delivery is used with this subscription, this field is used to configure it. An empty pushConfig signifies that
the subscriber will pull and ack messages using API methods.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retain<wbr>Acked<wbr>Messages</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether to retain acknowledged messages. If &#39;true&#39;, then messages are not expunged from the subscription&#39;s
backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Topic</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A reference to a Topic resource.
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
            <td class="align-top">ack<wbr>Deadline<wbr>Seconds</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the
message. After message delivery but before the ack deadline expires and before the message is acknowledged, it is an
outstanding message and will not be delivered again during that time (on a best-effort basis). For pull subscriptions,
this value is used as the initial value for the ack deadline. To override this value for a given message, call
subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify
is 10 seconds. The maximum custom deadline you can specify is 600 seconds (10 minutes). If this parameter is 0, a
default value of 10 seconds is used. For push delivery, this value is also used to set the request timeout for the call
to the push endpoint. If the subscriber never acknowledges the message, the Pub/Sub system will eventually redeliver the
message.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expiration<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#subscriptionexpirationpolicy">Subscription<wbr>Expiration<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} A policy that specifies the conditions for this subscription&#39;s expiration. A subscription is considered active as long
as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the
subscription. If expirationPolicy is not set, a default policy with ttl of 31 days will be used. If it is set but ttl is
&#34;&#34;, the resource never expires. The minimum allowed value for expirationPolicy.ttl is 1 day.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to this Subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">message<wbr>Retention<wbr>Duration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} How long to retain unacknowledged messages in the subscription&#39;s backlog, from the moment a message is published. If
retainAckedMessages is true, then this also configures the retention of acknowledged messages, and thus configures how
far back in time a subscriptions.seek can be done. Defaults to 7 days. Cannot be more than 7 days (&#39;&#34;604800s&#34;&#39;) or less
than 10 minutes (&#39;&#34;600s&#34;&#39;). A duration in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example:
&#39;&#34;600.5s&#34;&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">path</td>
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
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">push<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfig">Subscription<wbr>Push<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} If push delivery is used with this subscription, this field is used to configure it. An empty pushConfig signifies that
the subscriber will pull and ack messages using API methods.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retain<wbr>Acked<wbr>Messages</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether to retain acknowledged messages. If &#39;true&#39;, then messages are not expunged from the subscription&#39;s
backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">topic</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A reference to a Topic resource.
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
            <td class="align-top">ack_<wbr>deadline_<wbr>seconds</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the
message. After message delivery but before the ack deadline expires and before the message is acknowledged, it is an
outstanding message and will not be delivered again during that time (on a best-effort basis). For pull subscriptions,
this value is used as the initial value for the ack deadline. To override this value for a given message, call
subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify
is 10 seconds. The maximum custom deadline you can specify is 600 seconds (10 minutes). If this parameter is 0, a
default value of 10 seconds is used. For push delivery, this value is also used to set the request timeout for the call
to the push endpoint. If the subscriber never acknowledges the message, the Pub/Sub system will eventually redeliver the
message.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expiration_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#subscriptionexpirationpolicy">Dict[Subscription<wbr>Expiration<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} A policy that specifies the conditions for this subscription&#39;s expiration. A subscription is considered active as long
as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the
subscription. If expirationPolicy is not set, a default policy with ttl of 31 days will be used. If it is set but ttl is
&#34;&#34;, the resource never expires. The minimum allowed value for expirationPolicy.ttl is 1 day.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to this Subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">message_<wbr>retention_<wbr>duration</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} How long to retain unacknowledged messages in the subscription&#39;s backlog, from the moment a message is published. If
retainAckedMessages is true, then this also configures the retention of acknowledged messages, and thus configures how
far back in time a subscriptions.seek can be done. Defaults to 7 days. Cannot be more than 7 days (&#39;&#34;604800s&#34;&#39;) or less
than 10 minutes (&#39;&#34;600s&#34;&#39;). A duration in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example:
&#39;&#34;600.5s&#34;&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Name of the subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">path</td>
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
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">push_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfig">Dict[Subscription<wbr>Push<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} If push delivery is used with this subscription, this field is used to configure it. An empty pushConfig signifies that
the subscriber will pull and ack messages using API methods.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retain_<wbr>acked_<wbr>messages</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether to retain acknowledged messages. If &#39;true&#39;, then messages are not expunged from the subscription&#39;s
backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">topic</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A reference to a Topic resource.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Subscription Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/pubsub/#SubscriptionState">SubscriptionState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/pubsub/#Subscription">Subscription</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>ack_deadline_seconds=None<span class="p">, </span>expiration_policy=None<span class="p">, </span>labels=None<span class="p">, </span>message_retention_duration=None<span class="p">, </span>name=None<span class="p">, </span>path=None<span class="p">, </span>project=None<span class="p">, </span>push_config=None<span class="p">, </span>retain_acked_messages=None<span class="p">, </span>topic=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetSubscription<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/pubsub?tab=doc#SubscriptionState">SubscriptionState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/pubsub?tab=doc#Subscription">Subscription</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Pubsub.Subscription.html">Subscription</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Pubsub.SubscriptionState.html">SubscriptionState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Subscription resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Ack<wbr>Deadline<wbr>Seconds</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the
message. After message delivery but before the ack deadline expires and before the message is acknowledged, it is an
outstanding message and will not be delivered again during that time (on a best-effort basis). For pull subscriptions,
this value is used as the initial value for the ack deadline. To override this value for a given message, call
subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify
is 10 seconds. The maximum custom deadline you can specify is 600 seconds (10 minutes). If this parameter is 0, a
default value of 10 seconds is used. For push delivery, this value is also used to set the request timeout for the call
to the push endpoint. If the subscriber never acknowledges the message, the Pub/Sub system will eventually redeliver the
message.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expiration<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#subscriptionexpirationpolicy">Subscription<wbr>Expiration<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A policy that specifies the conditions for this subscription&#39;s expiration. A subscription is considered active as long
as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the
subscription. If expirationPolicy is not set, a default policy with ttl of 31 days will be used. If it is set but ttl is
&#34;&#34;, the resource never expires. The minimum allowed value for expirationPolicy.ttl is 1 day.
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
A set of key/value label pairs to assign to this Subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Message<wbr>Retention<wbr>Duration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How long to retain unacknowledged messages in the subscription&#39;s backlog, from the moment a message is published. If
retainAckedMessages is true, then this also configures the retention of acknowledged messages, and thus configures how
far back in time a subscriptions.seek can be done. Defaults to 7 days. Cannot be more than 7 days (&#39;&#34;604800s&#34;&#39;) or less
than 10 minutes (&#39;&#34;600s&#34;&#39;). A duration in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example:
&#39;&#34;600.5s&#34;&#39;.
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
Name of the subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Push<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfig">Subscription<wbr>Push<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If push delivery is used with this subscription, this field is used to configure it. An empty pushConfig signifies that
the subscriber will pull and ack messages using API methods.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retain<wbr>Acked<wbr>Messages</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether to retain acknowledged messages. If &#39;true&#39;, then messages are not expunged from the subscription&#39;s
backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.
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
A reference to a Topic resource.
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
            <td class="align-top">Ack<wbr>Deadline<wbr>Seconds</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the
message. After message delivery but before the ack deadline expires and before the message is acknowledged, it is an
outstanding message and will not be delivered again during that time (on a best-effort basis). For pull subscriptions,
this value is used as the initial value for the ack deadline. To override this value for a given message, call
subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify
is 10 seconds. The maximum custom deadline you can specify is 600 seconds (10 minutes). If this parameter is 0, a
default value of 10 seconds is used. For push delivery, this value is also used to set the request timeout for the call
to the push endpoint. If the subscriber never acknowledges the message, the Pub/Sub system will eventually redeliver the
message.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expiration<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#subscriptionexpirationpolicy">*Subscription<wbr>Expiration<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A policy that specifies the conditions for this subscription&#39;s expiration. A subscription is considered active as long
as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the
subscription. If expirationPolicy is not set, a default policy with ttl of 31 days will be used. If it is set but ttl is
&#34;&#34;, the resource never expires. The minimum allowed value for expirationPolicy.ttl is 1 day.
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
A set of key/value label pairs to assign to this Subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Message<wbr>Retention<wbr>Duration</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How long to retain unacknowledged messages in the subscription&#39;s backlog, from the moment a message is published. If
retainAckedMessages is true, then this also configures the retention of acknowledged messages, and thus configures how
far back in time a subscriptions.seek can be done. Defaults to 7 days. Cannot be more than 7 days (&#39;&#34;604800s&#34;&#39;) or less
than 10 minutes (&#39;&#34;600s&#34;&#39;). A duration in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example:
&#39;&#34;600.5s&#34;&#39;.
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
Name of the subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Path</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Push<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfig">*Subscription<wbr>Push<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If push delivery is used with this subscription, this field is used to configure it. An empty pushConfig signifies that
the subscriber will pull and ack messages using API methods.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retain<wbr>Acked<wbr>Messages</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether to retain acknowledged messages. If &#39;true&#39;, then messages are not expunged from the subscription&#39;s
backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.
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
A reference to a Topic resource.
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
            <td class="align-top">ack<wbr>Deadline<wbr>Seconds</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the
message. After message delivery but before the ack deadline expires and before the message is acknowledged, it is an
outstanding message and will not be delivered again during that time (on a best-effort basis). For pull subscriptions,
this value is used as the initial value for the ack deadline. To override this value for a given message, call
subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify
is 10 seconds. The maximum custom deadline you can specify is 600 seconds (10 minutes). If this parameter is 0, a
default value of 10 seconds is used. For push delivery, this value is also used to set the request timeout for the call
to the push endpoint. If the subscriber never acknowledges the message, the Pub/Sub system will eventually redeliver the
message.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expiration<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#subscriptionexpirationpolicy">Subscription<wbr>Expiration<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A policy that specifies the conditions for this subscription&#39;s expiration. A subscription is considered active as long
as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the
subscription. If expirationPolicy is not set, a default policy with ttl of 31 days will be used. If it is set but ttl is
&#34;&#34;, the resource never expires. The minimum allowed value for expirationPolicy.ttl is 1 day.
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
A set of key/value label pairs to assign to this Subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">message<wbr>Retention<wbr>Duration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How long to retain unacknowledged messages in the subscription&#39;s backlog, from the moment a message is published. If
retainAckedMessages is true, then this also configures the retention of acknowledged messages, and thus configures how
far back in time a subscriptions.seek can be done. Defaults to 7 days. Cannot be more than 7 days (&#39;&#34;604800s&#34;&#39;) or less
than 10 minutes (&#39;&#34;600s&#34;&#39;). A duration in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example:
&#39;&#34;600.5s&#34;&#39;.
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
Name of the subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">push<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfig">Subscription<wbr>Push<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If push delivery is used with this subscription, this field is used to configure it. An empty pushConfig signifies that
the subscriber will pull and ack messages using API methods.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retain<wbr>Acked<wbr>Messages</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether to retain acknowledged messages. If &#39;true&#39;, then messages are not expunged from the subscription&#39;s
backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.
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
A reference to a Topic resource.
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
            <td class="align-top">ack_<wbr>deadline_<wbr>seconds</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the
message. After message delivery but before the ack deadline expires and before the message is acknowledged, it is an
outstanding message and will not be delivered again during that time (on a best-effort basis). For pull subscriptions,
this value is used as the initial value for the ack deadline. To override this value for a given message, call
subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify
is 10 seconds. The maximum custom deadline you can specify is 600 seconds (10 minutes). If this parameter is 0, a
default value of 10 seconds is used. For push delivery, this value is also used to set the request timeout for the call
to the push endpoint. If the subscriber never acknowledges the message, the Pub/Sub system will eventually redeliver the
message.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expiration_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#subscriptionexpirationpolicy">Dict[Subscription<wbr>Expiration<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A policy that specifies the conditions for this subscription&#39;s expiration. A subscription is considered active as long
as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the
subscription. If expirationPolicy is not set, a default policy with ttl of 31 days will be used. If it is set but ttl is
&#34;&#34;, the resource never expires. The minimum allowed value for expirationPolicy.ttl is 1 day.
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
A set of key/value label pairs to assign to this Subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">message_<wbr>retention_<wbr>duration</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How long to retain unacknowledged messages in the subscription&#39;s backlog, from the moment a message is published. If
retainAckedMessages is true, then this also configures the retention of acknowledged messages, and thus configures how
far back in time a subscriptions.seek can be done. Defaults to 7 days. Cannot be more than 7 days (&#39;&#34;604800s&#34;&#39;) or less
than 10 minutes (&#39;&#34;600s&#34;&#39;). A duration in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example:
&#39;&#34;600.5s&#34;&#39;.
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
Name of the subscription.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">path</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">push_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfig">Dict[Subscription<wbr>Push<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If push delivery is used with this subscription, this field is used to configure it. An empty pushConfig signifies that
the subscriber will pull and ack messages using API methods.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retain_<wbr>acked_<wbr>messages</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether to retain acknowledged messages. If &#39;true&#39;, then messages are not expunged from the subscription&#39;s
backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.
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
A reference to a Topic resource.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### SubscriptionExpirationPolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#SubscriptionExpirationPolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#SubscriptionExpirationPolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/pubsub?tab=doc#SubscriptionExpirationPolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/pubsub?tab=doc#SubscriptionExpirationPolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Pubsub.SubscriptionExpirationPolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Pubsub.SubscriptionExpirationPolicy.html">output</a> API doc for this type.
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
            <td class="align-top">Ttl</td>
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
            <td class="align-top">Ttl</td>
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
            <td class="align-top">ttl</td>
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
            <td class="align-top">ttl</td>
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





#### SubscriptionPushConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#SubscriptionPushConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#SubscriptionPushConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/pubsub?tab=doc#SubscriptionPushConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/pubsub?tab=doc#SubscriptionPushConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Pubsub.SubscriptionPushConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Pubsub.SubscriptionPushConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Attributes</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oidc<wbr>Token</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfigoidctoken">Subscription<wbr>Push<wbr>Config<wbr>Oidc<wbr>Token<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Push<wbr>Endpoint</td>
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
            <td class="align-top">Attributes</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oidc<wbr>Token</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfigoidctoken">*Subscription<wbr>Push<wbr>Config<wbr>Oidc<wbr>Token</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Push<wbr>Endpoint</td>
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
            <td class="align-top">attributes</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oidc<wbr>Token</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfigoidctoken">Subscription<wbr>Push<wbr>Config<wbr>Oidc<wbr>Token?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">push<wbr>Endpoint</td>
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
            <td class="align-top">attributes</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oidc<wbr>Token</td>
            <td class="align-top">
                
                <code><a href="#subscriptionpushconfigoidctoken">Dict[Subscription<wbr>Push<wbr>Config<wbr>Oidc<wbr>Token]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">push<wbr>Endpoint</td>
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





#### SubscriptionPushConfigOidcToken
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#SubscriptionPushConfigOidcToken">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#SubscriptionPushConfigOidcToken">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/pubsub?tab=doc#SubscriptionPushConfigOidcTokenArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/pubsub?tab=doc#SubscriptionPushConfigOidcTokenOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Pubsub.SubscriptionPushConfigOidcTokenArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Pubsub.SubscriptionPushConfigOidcToken.html">output</a> API doc for this type.
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
            <td class="align-top">Audience</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Account<wbr>Email</td>
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
            <td class="align-top">Audience</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Account<wbr>Email</td>
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
            <td class="align-top">audience</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Account<wbr>Email</td>
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
            <td class="align-top">audience</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service_<wbr>account_<wbr>email</td>
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








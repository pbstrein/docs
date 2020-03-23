
---
title: "Registry"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

 Creates a device registry in Google's Cloud IoT Core platform. For more information see
[the official documentation](https://cloud.google.com/iot/docs/) and
[API](https://cloud.google.com/iot/docs/reference/cloudiot/rest/v1/projects.locations.registries).

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/cloudiot_registry.html.markdown.



## Create a Registry Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/kms/#Registry">Registry</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/kms/#RegistryArgs">RegistryArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Registry</span><span class="p">(resource_name, opts=None, </span>credentials=None<span class="p">, </span>event_notification_configs=None<span class="p">, </span>http_config=None<span class="p">, </span>log_level=None<span class="p">, </span>mqtt_config=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>state_notification_config=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewRegistry<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#RegistryArgs">RegistryArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#Registry">Registry</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.Registry.html">Registry</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.RegistryArgs.html">RegistryArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Registry resource with the given unique name, arguments, and options.

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
            <td class="align-top">Credentials</td>
            <td class="align-top">
                
                <code><a href="#registrycredential">List&lt;Registry<wbr>Credential<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of public key certificates to authenticate devices. Structure is documented below. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Event<wbr>Notification<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#registryeventnotificationconfigitem">List&lt;Registry<wbr>Event<wbr>Notification<wbr>Config<wbr>Item<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of configurations for event notification, such as
PubSub topics to publish device events to. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registryhttpconfig">Registry<wbr>Http<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate HTTP. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Level</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mqtt<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrymqttconfig">Registry<wbr>Mqtt<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate MQTT. Structure is documented below.
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
A unique name for the resource, required by device registry.
Changing this forces a new resource to be created.
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">State<wbr>Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrystatenotificationconfig">Registry<wbr>State<wbr>Notification<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A PubSub topic to publish device state updates. Structure is documented below.
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
            <td class="align-top">Credentials</td>
            <td class="align-top">
                
                <code><a href="#registrycredential">[]Registry<wbr>Credential</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of public key certificates to authenticate devices. Structure is documented below. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Event<wbr>Notification<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#registryeventnotificationconfigitem">[]Registry<wbr>Event<wbr>Notification<wbr>Config<wbr>Item</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of configurations for event notification, such as
PubSub topics to publish device events to. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registryhttpconfig">*Registry<wbr>Http<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate HTTP. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Level</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mqtt<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrymqttconfig">*Registry<wbr>Mqtt<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate MQTT. Structure is documented below.
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
A unique name for the resource, required by device registry.
Changing this forces a new resource to be created.
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">State<wbr>Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrystatenotificationconfig">*Registry<wbr>State<wbr>Notification<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A PubSub topic to publish device state updates. Structure is documented below.
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
            <td class="align-top">credentials</td>
            <td class="align-top">
                
                <code><a href="#registrycredential">Registry<wbr>Credential[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of public key certificates to authenticate devices. Structure is documented below. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">event<wbr>Notification<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#registryeventnotificationconfigitem">Registry<wbr>Event<wbr>Notification<wbr>Config<wbr>Item[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of configurations for event notification, such as
PubSub topics to publish device events to. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registryhttpconfig">Registry<wbr>Http<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate HTTP. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Level</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mqtt<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrymqttconfig">Registry<wbr>Mqtt<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate MQTT. Structure is documented below.
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
A unique name for the resource, required by device registry.
Changing this forces a new resource to be created.
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">state<wbr>Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrystatenotificationconfig">Registry<wbr>State<wbr>Notification<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A PubSub topic to publish device state updates. Structure is documented below.
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
            <td class="align-top">credentials</td>
            <td class="align-top">
                
                <code><a href="#registrycredential">List[Registry<wbr>Credential]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of public key certificates to authenticate devices. Structure is documented below. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">event_<wbr>notification_<wbr>configs</td>
            <td class="align-top">
                
                <code><a href="#registryeventnotificationconfigitem">List[Registry<wbr>Event<wbr>Notification<wbr>Config<wbr>Item]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of configurations for event notification, such as
PubSub topics to publish device events to. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#registryhttpconfig">Dict[Registry<wbr>Http<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate HTTP. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log_<wbr>level</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mqtt_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#registrymqttconfig">Dict[Registry<wbr>Mqtt<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate MQTT. Structure is documented below.
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
A unique name for the resource, required by device registry.
Changing this forces a new resource to be created.
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">state_<wbr>notification_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#registrystatenotificationconfig">Dict[Registry<wbr>State<wbr>Notification<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A PubSub topic to publish device state updates. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Registry Output Properties

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
            <td class="align-top">Credentials</td>
            <td class="align-top">
                
                <code><a href="#registrycredential">List&lt;Registry<wbr>Credential&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} List of public key certificates to authenticate devices. Structure is documented below. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Event<wbr>Notification<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#registryeventnotificationconfigitem">List&lt;Registry<wbr>Event<wbr>Notification<wbr>Config<wbr>Item&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} List of configurations for event notification, such as
PubSub topics to publish device events to. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registryhttpconfig">Registry<wbr>Http<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Activate or deactivate HTTP. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Level</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mqtt<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrymqttconfig">Registry<wbr>Mqtt<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Activate or deactivate MQTT. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A unique name for the resource, required by device registry.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The project in which the resource belongs. If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Region in which the created address should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">State<wbr>Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrystatenotificationconfig">Registry<wbr>State<wbr>Notification<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} A PubSub topic to publish device state updates. Structure is documented below.
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
            <td class="align-top">Credentials</td>
            <td class="align-top">
                
                <code><a href="#registrycredential">[]Registry<wbr>Credential</a></code>
            </td>
            <td class="align-top">{{% md %}} List of public key certificates to authenticate devices. Structure is documented below. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Event<wbr>Notification<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#registryeventnotificationconfigitem">[]Registry<wbr>Event<wbr>Notification<wbr>Config<wbr>Item</a></code>
            </td>
            <td class="align-top">{{% md %}} List of configurations for event notification, such as
PubSub topics to publish device events to. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registryhttpconfig">Registry<wbr>Http<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Activate or deactivate HTTP. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Level</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mqtt<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrymqttconfig">Registry<wbr>Mqtt<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Activate or deactivate MQTT. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A unique name for the resource, required by device registry.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The project in which the resource belongs. If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Region in which the created address should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">State<wbr>Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrystatenotificationconfig">*Registry<wbr>State<wbr>Notification<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} A PubSub topic to publish device state updates. Structure is documented below.
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
            <td class="align-top">credentials</td>
            <td class="align-top">
                
                <code><a href="#registrycredential">Registry<wbr>Credential[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} List of public key certificates to authenticate devices. Structure is documented below. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">event<wbr>Notification<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#registryeventnotificationconfigitem">Registry<wbr>Event<wbr>Notification<wbr>Config<wbr>Item[]</a></code>
            </td>
            <td class="align-top">{{% md %}} List of configurations for event notification, such as
PubSub topics to publish device events to. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registryhttpconfig">Registry<wbr>Http<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Activate or deactivate HTTP. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Level</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mqtt<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrymqttconfig">Registry<wbr>Mqtt<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Activate or deactivate MQTT. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A unique name for the resource, required by device registry.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The project in which the resource belongs. If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Region in which the created address should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">state<wbr>Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrystatenotificationconfig">Registry<wbr>State<wbr>Notification<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} A PubSub topic to publish device state updates. Structure is documented below.
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
            <td class="align-top">credentials</td>
            <td class="align-top">
                
                <code><a href="#registrycredential">List[Registry<wbr>Credential]</a></code>
            </td>
            <td class="align-top">{{% md %}} List of public key certificates to authenticate devices. Structure is documented below. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">event_<wbr>notification_<wbr>configs</td>
            <td class="align-top">
                
                <code><a href="#registryeventnotificationconfigitem">List[Registry<wbr>Event<wbr>Notification<wbr>Config<wbr>Item]</a></code>
            </td>
            <td class="align-top">{{% md %}} List of configurations for event notification, such as
PubSub topics to publish device events to. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#registryhttpconfig">Dict[Registry<wbr>Http<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} Activate or deactivate HTTP. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log_<wbr>level</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mqtt_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#registrymqttconfig">Dict[Registry<wbr>Mqtt<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} Activate or deactivate MQTT. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A unique name for the resource, required by device registry.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The project in which the resource belongs. If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Region in which the created address should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">state_<wbr>notification_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#registrystatenotificationconfig">Dict[Registry<wbr>State<wbr>Notification<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} A PubSub topic to publish device state updates. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Registry Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/kms/#RegistryState">RegistryState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/kms/#Registry">Registry</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>credentials=None<span class="p">, </span>event_notification_configs=None<span class="p">, </span>http_config=None<span class="p">, </span>log_level=None<span class="p">, </span>mqtt_config=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>state_notification_config=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetRegistry<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#RegistryState">RegistryState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#Registry">Registry</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.Registry.html">Registry</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.RegistryState.html">RegistryState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Registry resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Credentials</td>
            <td class="align-top">
                
                <code><a href="#registrycredential">List&lt;Registry<wbr>Credential<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of public key certificates to authenticate devices. Structure is documented below. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Event<wbr>Notification<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#registryeventnotificationconfigitem">List&lt;Registry<wbr>Event<wbr>Notification<wbr>Config<wbr>Item<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of configurations for event notification, such as
PubSub topics to publish device events to. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registryhttpconfig">Registry<wbr>Http<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate HTTP. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Level</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mqtt<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrymqttconfig">Registry<wbr>Mqtt<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate MQTT. Structure is documented below.
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
A unique name for the resource, required by device registry.
Changing this forces a new resource to be created.
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">State<wbr>Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrystatenotificationconfig">Registry<wbr>State<wbr>Notification<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A PubSub topic to publish device state updates. Structure is documented below.
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
            <td class="align-top">Credentials</td>
            <td class="align-top">
                
                <code><a href="#registrycredential">[]Registry<wbr>Credential</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of public key certificates to authenticate devices. Structure is documented below. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Event<wbr>Notification<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#registryeventnotificationconfigitem">[]Registry<wbr>Event<wbr>Notification<wbr>Config<wbr>Item</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of configurations for event notification, such as
PubSub topics to publish device events to. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registryhttpconfig">*Registry<wbr>Http<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate HTTP. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Level</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mqtt<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrymqttconfig">*Registry<wbr>Mqtt<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate MQTT. Structure is documented below.
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
A unique name for the resource, required by device registry.
Changing this forces a new resource to be created.
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">State<wbr>Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrystatenotificationconfig">*Registry<wbr>State<wbr>Notification<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A PubSub topic to publish device state updates. Structure is documented below.
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
            <td class="align-top">credentials</td>
            <td class="align-top">
                
                <code><a href="#registrycredential">Registry<wbr>Credential[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of public key certificates to authenticate devices. Structure is documented below. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">event<wbr>Notification<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#registryeventnotificationconfigitem">Registry<wbr>Event<wbr>Notification<wbr>Config<wbr>Item[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of configurations for event notification, such as
PubSub topics to publish device events to. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registryhttpconfig">Registry<wbr>Http<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate HTTP. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Level</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mqtt<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrymqttconfig">Registry<wbr>Mqtt<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate MQTT. Structure is documented below.
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
A unique name for the resource, required by device registry.
Changing this forces a new resource to be created.
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">state<wbr>Notification<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#registrystatenotificationconfig">Registry<wbr>State<wbr>Notification<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A PubSub topic to publish device state updates. Structure is documented below.
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
            <td class="align-top">credentials</td>
            <td class="align-top">
                
                <code><a href="#registrycredential">List[Registry<wbr>Credential]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of public key certificates to authenticate devices. Structure is documented below. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">event_<wbr>notification_<wbr>configs</td>
            <td class="align-top">
                
                <code><a href="#registryeventnotificationconfigitem">List[Registry<wbr>Event<wbr>Notification<wbr>Config<wbr>Item]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of configurations for event notification, such as
PubSub topics to publish device events to. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#registryhttpconfig">Dict[Registry<wbr>Http<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate HTTP. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log_<wbr>level</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mqtt_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#registrymqttconfig">Dict[Registry<wbr>Mqtt<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Activate or deactivate MQTT. Structure is documented below.
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
A unique name for the resource, required by device registry.
Changing this forces a new resource to be created.
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">state_<wbr>notification_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#registrystatenotificationconfig">Dict[Registry<wbr>State<wbr>Notification<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A PubSub topic to publish device state updates. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### RegistryCredential
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegistryCredential">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegistryCredential">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#RegistryCredentialArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#RegistryCredentialOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.RegistryCredentialArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.RegistryCredential.html">output</a> API doc for this type.
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
            <td class="align-top">Public<wbr>Key<wbr>Certificate</td>
            <td class="align-top">
                
                <code><a href="#registrycredentialpublickeycertificate">Registry<wbr>Credential<wbr>Public<wbr>Key<wbr>Certificate<wbr>Args</a></code>
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
            <td class="align-top">Public<wbr>Key<wbr>Certificate</td>
            <td class="align-top">
                
                <code><a href="#registrycredentialpublickeycertificate">Registry<wbr>Credential<wbr>Public<wbr>Key<wbr>Certificate</a></code>
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
            <td class="align-top">public<wbr>Key<wbr>Certificate</td>
            <td class="align-top">
                
                <code><a href="#registrycredentialpublickeycertificate">Registry<wbr>Credential<wbr>Public<wbr>Key<wbr>Certificate</a></code>
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
            <td class="align-top">public<wbr>Key<wbr>Certificate</td>
            <td class="align-top">
                
                <code><a href="#registrycredentialpublickeycertificate">Dict[Registry<wbr>Credential<wbr>Public<wbr>Key<wbr>Certificate]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### RegistryCredentialPublicKeyCertificate
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegistryCredentialPublicKeyCertificate">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegistryCredentialPublicKeyCertificate">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#RegistryCredentialPublicKeyCertificateArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#RegistryCredentialPublicKeyCertificateOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.RegistryCredentialPublicKeyCertificateArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.RegistryCredentialPublicKeyCertificate.html">output</a> API doc for this type.
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
            <td class="align-top">Certificate</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Format</td>
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
            <td class="align-top">Certificate</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Format</td>
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
            <td class="align-top">certificate</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">format</td>
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
            <td class="align-top">certificate</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">format</td>
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





#### RegistryEventNotificationConfigItem
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegistryEventNotificationConfigItem">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegistryEventNotificationConfigItem">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#RegistryEventNotificationConfigItemArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#RegistryEventNotificationConfigItemOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.RegistryEventNotificationConfigItemArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.RegistryEventNotificationConfigItem.html">output</a> API doc for this type.
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
            <td class="align-top">Pubsub<wbr>Topic<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subfolder<wbr>Matches</td>
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
            <td class="align-top">Pubsub<wbr>Topic<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subfolder<wbr>Matches</td>
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
            <td class="align-top">pubsub<wbr>Topic<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subfolder<wbr>Matches</td>
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
            <td class="align-top">pubsub_<wbr>topic_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subfolder<wbr>Matches</td>
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





#### RegistryHttpConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegistryHttpConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegistryHttpConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#RegistryHttpConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#RegistryHttpConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.RegistryHttpConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.RegistryHttpConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Http<wbr>Enabled<wbr>State</td>
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
            <td class="align-top">Http<wbr>Enabled<wbr>State</td>
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
            <td class="align-top">http<wbr>Enabled<wbr>State</td>
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
            <td class="align-top">http_<wbr>enabled_<wbr>state</td>
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





#### RegistryMqttConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegistryMqttConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegistryMqttConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#RegistryMqttConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#RegistryMqttConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.RegistryMqttConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.RegistryMqttConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Mqtt<wbr>Enabled<wbr>State</td>
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
            <td class="align-top">Mqtt<wbr>Enabled<wbr>State</td>
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
            <td class="align-top">mqtt<wbr>Enabled<wbr>State</td>
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
            <td class="align-top">mqtt_<wbr>enabled_<wbr>state</td>
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





#### RegistryStateNotificationConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegistryStateNotificationConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegistryStateNotificationConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#RegistryStateNotificationConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/kms?tab=doc#RegistryStateNotificationConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.RegistryStateNotificationConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Kms.RegistryStateNotificationConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Pubsub<wbr>Topic<wbr>Name</td>
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
            <td class="align-top">Pubsub<wbr>Topic<wbr>Name</td>
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
            <td class="align-top">pubsub<wbr>Topic<wbr>Name</td>
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
            <td class="align-top">pubsub_<wbr>topic_<wbr>name</td>
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








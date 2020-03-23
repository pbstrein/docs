
---
title: "NotificationChannel"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a NotificationChannel Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/monitoring/#NotificationChannel">NotificationChannel</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/monitoring/#NotificationChannelArgs">NotificationChannelArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">NotificationChannel</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>display_name=None<span class="p">, </span>enabled=None<span class="p">, </span>labels=None<span class="p">, </span>project=None<span class="p">, </span>type=None<span class="p">, </span>user_labels=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewNotificationChannel<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#NotificationChannelArgs">NotificationChannelArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#NotificationChannel">NotificationChannel</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.NotificationChannel.html">NotificationChannel</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.NotificationChannelArgs.html">NotificationChannelArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a NotificationChannel resource with the given unique name, arguments, and options.

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
An optional human-readable description of this notification channel. This description may provide additional details,
beyond the display name, for the channel. This may not exceed 1024 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An optional human-readable name for this notification channel. It is recommended that you specify a non-empty and unique
name in order to make it easier to identify the channels in your project, though this is not enforced. The display name
is limited to 512 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether notifications are forwarded to the described channel. This makes it possible to disable delivery of
notifications to a particular channel without removing the channel from all alerting policies that reference the
channel. This is a more convenient approach when the change is temporary and you want to receive notifications from the
same set of alerting policies on the channel at some point in the future.
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
Configuration fields that define the channel and its behavior. The permissible and required labels are specified in the
NotificationChannelDescriptor corresponding to the type field. **Note**: Some NotificationChannelDescriptor labels are
sensitive and the API will return an partially-obfuscated value. For example, for &#39;&#34;type&#34;: &#34;slack&#34;&#39; channels, an
&#39;auth_token&#39; label with value &#34;SECRET&#34; will be obfuscated as &#34;**CRET&#34;. In order to avoid a diff, Terraform will use the
state value if it appears that the obfuscated value matches the state value in length/unobfuscated characters. However,
Terraform will not detect a diff if the obfuscated portion of the value was changed outside of Terraform.
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
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The type of the notification channel. This field matches the value of the NotificationChannelDescriptor.type field. See
https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.notificationChannelDescriptors/list to get the list of
valid values such as &#34;email&#34;, &#34;slack&#34;, etc...
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-supplied key/value data that does not need to conform to the corresponding NotificationChannelDescriptor&#39;s schema,
unlike the labels field. This field is intended to be used for organizing and identifying the NotificationChannel
objects.The field can contain up to 64 entries. Each key and value is limited to 63 Unicode characters or 128 bytes,
whichever is smaller. Labels and values can contain only lowercase letters, numerals, underscores, and dashes. Keys must
begin with a letter.
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
An optional human-readable description of this notification channel. This description may provide additional details,
beyond the display name, for the channel. This may not exceed 1024 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An optional human-readable name for this notification channel. It is recommended that you specify a non-empty and unique
name in order to make it easier to identify the channels in your project, though this is not enforced. The display name
is limited to 512 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether notifications are forwarded to the described channel. This makes it possible to disable delivery of
notifications to a particular channel without removing the channel from all alerting policies that reference the
channel. This is a more convenient approach when the change is temporary and you want to receive notifications from the
same set of alerting policies on the channel at some point in the future.
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
Configuration fields that define the channel and its behavior. The permissible and required labels are specified in the
NotificationChannelDescriptor corresponding to the type field. **Note**: Some NotificationChannelDescriptor labels are
sensitive and the API will return an partially-obfuscated value. For example, for &#39;&#34;type&#34;: &#34;slack&#34;&#39; channels, an
&#39;auth_token&#39; label with value &#34;SECRET&#34; will be obfuscated as &#34;**CRET&#34;. In order to avoid a diff, Terraform will use the
state value if it appears that the obfuscated value matches the state value in length/unobfuscated characters. However,
Terraform will not detect a diff if the obfuscated portion of the value was changed outside of Terraform.
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
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The type of the notification channel. This field matches the value of the NotificationChannelDescriptor.type field. See
https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.notificationChannelDescriptors/list to get the list of
valid values such as &#34;email&#34;, &#34;slack&#34;, etc...
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-supplied key/value data that does not need to conform to the corresponding NotificationChannelDescriptor&#39;s schema,
unlike the labels field. This field is intended to be used for organizing and identifying the NotificationChannel
objects.The field can contain up to 64 entries. Each key and value is limited to 63 Unicode characters or 128 bytes,
whichever is smaller. Labels and values can contain only lowercase letters, numerals, underscores, and dashes. Keys must
begin with a letter.
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
An optional human-readable description of this notification channel. This description may provide additional details,
beyond the display name, for the channel. This may not exceed 1024 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An optional human-readable name for this notification channel. It is recommended that you specify a non-empty and unique
name in order to make it easier to identify the channels in your project, though this is not enforced. The display name
is limited to 512 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether notifications are forwarded to the described channel. This makes it possible to disable delivery of
notifications to a particular channel without removing the channel from all alerting policies that reference the
channel. This is a more convenient approach when the change is temporary and you want to receive notifications from the
same set of alerting policies on the channel at some point in the future.
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
Configuration fields that define the channel and its behavior. The permissible and required labels are specified in the
NotificationChannelDescriptor corresponding to the type field. **Note**: Some NotificationChannelDescriptor labels are
sensitive and the API will return an partially-obfuscated value. For example, for &#39;&#34;type&#34;: &#34;slack&#34;&#39; channels, an
&#39;auth_token&#39; label with value &#34;SECRET&#34; will be obfuscated as &#34;**CRET&#34;. In order to avoid a diff, Terraform will use the
state value if it appears that the obfuscated value matches the state value in length/unobfuscated characters. However,
Terraform will not detect a diff if the obfuscated portion of the value was changed outside of Terraform.
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
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The type of the notification channel. This field matches the value of the NotificationChannelDescriptor.type field. See
https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.notificationChannelDescriptors/list to get the list of
valid values such as &#34;email&#34;, &#34;slack&#34;, etc...
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-supplied key/value data that does not need to conform to the corresponding NotificationChannelDescriptor&#39;s schema,
unlike the labels field. This field is intended to be used for organizing and identifying the NotificationChannel
objects.The field can contain up to 64 entries. Each key and value is limited to 63 Unicode characters or 128 bytes,
whichever is smaller. Labels and values can contain only lowercase letters, numerals, underscores, and dashes. Keys must
begin with a letter.
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
An optional human-readable description of this notification channel. This description may provide additional details,
beyond the display name, for the channel. This may not exceed 1024 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An optional human-readable name for this notification channel. It is recommended that you specify a non-empty and unique
name in order to make it easier to identify the channels in your project, though this is not enforced. The display name
is limited to 512 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether notifications are forwarded to the described channel. This makes it possible to disable delivery of
notifications to a particular channel without removing the channel from all alerting policies that reference the
channel. This is a more convenient approach when the change is temporary and you want to receive notifications from the
same set of alerting policies on the channel at some point in the future.
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
Configuration fields that define the channel and its behavior. The permissible and required labels are specified in the
NotificationChannelDescriptor corresponding to the type field. **Note**: Some NotificationChannelDescriptor labels are
sensitive and the API will return an partially-obfuscated value. For example, for &#39;&#34;type&#34;: &#34;slack&#34;&#39; channels, an
&#39;auth_token&#39; label with value &#34;SECRET&#34; will be obfuscated as &#34;**CRET&#34;. In order to avoid a diff, Terraform will use the
state value if it appears that the obfuscated value matches the state value in length/unobfuscated characters. However,
Terraform will not detect a diff if the obfuscated portion of the value was changed outside of Terraform.
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
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The type of the notification channel. This field matches the value of the NotificationChannelDescriptor.type field. See
https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.notificationChannelDescriptors/list to get the list of
valid values such as &#34;email&#34;, &#34;slack&#34;, etc...
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user_<wbr>labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-supplied key/value data that does not need to conform to the corresponding NotificationChannelDescriptor&#39;s schema,
unlike the labels field. This field is intended to be used for organizing and identifying the NotificationChannel
objects.The field can contain up to 64 entries. Each key and value is limited to 63 Unicode characters or 128 bytes,
whichever is smaller. Labels and values can contain only lowercase letters, numerals, underscores, and dashes. Keys must
begin with a letter.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## NotificationChannel Output Properties

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
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An optional human-readable description of this notification channel. This description may provide additional details,
beyond the display name, for the channel. This may not exceed 1024 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} An optional human-readable name for this notification channel. It is recommended that you specify a non-empty and unique
name in order to make it easier to identify the channels in your project, though this is not enforced. The display name
is limited to 512 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether notifications are forwarded to the described channel. This makes it possible to disable delivery of
notifications to a particular channel without removing the channel from all alerting policies that reference the
channel. This is a more convenient approach when the change is temporary and you want to receive notifications from the
same set of alerting policies on the channel at some point in the future.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} Configuration fields that define the channel and its behavior. The permissible and required labels are specified in the
NotificationChannelDescriptor corresponding to the type field. **Note**: Some NotificationChannelDescriptor labels are
sensitive and the API will return an partially-obfuscated value. For example, for &#39;&#34;type&#34;: &#34;slack&#34;&#39; channels, an
&#39;auth_token&#39; label with value &#34;SECRET&#34; will be obfuscated as &#34;**CRET&#34;. In order to avoid a diff, Terraform will use the
state value if it appears that the obfuscated value matches the state value in length/unobfuscated characters. However,
Terraform will not detect a diff if the obfuscated portion of the value was changed outside of Terraform.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The full REST resource name for this channel. The syntax is: projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID] The
[CHANNEL_ID] is automatically assigned by the server on creation.
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
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The type of the notification channel. This field matches the value of the NotificationChannelDescriptor.type field. See
https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.notificationChannelDescriptors/list to get the list of
valid values such as &#34;email&#34;, &#34;slack&#34;, etc...
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} User-supplied key/value data that does not need to conform to the corresponding NotificationChannelDescriptor&#39;s schema,
unlike the labels field. This field is intended to be used for organizing and identifying the NotificationChannel
objects.The field can contain up to 64 entries. Each key and value is limited to 63 Unicode characters or 128 bytes,
whichever is smaller. Labels and values can contain only lowercase letters, numerals, underscores, and dashes. Keys must
begin with a letter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Verification<wbr>Status</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether this channel has been verified or not. On a ListNotificationChannels or GetNotificationChannel
operation, this field is expected to be populated.If the value is UNVERIFIED, then it indicates that the channel is
non-functioning (it both requires verification and lacks verification); otherwise, it is assumed that the channel
works.If the channel is neither VERIFIED nor UNVERIFIED, it implies that the channel is of a type that does not require
verification or that this specific channel has been exempted from verification because it was created prior to
verification being required for channels of this type.This field cannot be modified using a standard
UpdateNotificationChannel operation. To change the value of this field, you must call VerifyNotificationChannel.
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
            <td class="align-top">{{% md %}} An optional human-readable description of this notification channel. This description may provide additional details,
beyond the display name, for the channel. This may not exceed 1024 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} An optional human-readable name for this notification channel. It is recommended that you specify a non-empty and unique
name in order to make it easier to identify the channels in your project, though this is not enforced. The display name
is limited to 512 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether notifications are forwarded to the described channel. This makes it possible to disable delivery of
notifications to a particular channel without removing the channel from all alerting policies that reference the
channel. This is a more convenient approach when the change is temporary and you want to receive notifications from the
same set of alerting policies on the channel at some point in the future.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} Configuration fields that define the channel and its behavior. The permissible and required labels are specified in the
NotificationChannelDescriptor corresponding to the type field. **Note**: Some NotificationChannelDescriptor labels are
sensitive and the API will return an partially-obfuscated value. For example, for &#39;&#34;type&#34;: &#34;slack&#34;&#39; channels, an
&#39;auth_token&#39; label with value &#34;SECRET&#34; will be obfuscated as &#34;**CRET&#34;. In order to avoid a diff, Terraform will use the
state value if it appears that the obfuscated value matches the state value in length/unobfuscated characters. However,
Terraform will not detect a diff if the obfuscated portion of the value was changed outside of Terraform.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The full REST resource name for this channel. The syntax is: projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID] The
[CHANNEL_ID] is automatically assigned by the server on creation.
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
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The type of the notification channel. This field matches the value of the NotificationChannelDescriptor.type field. See
https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.notificationChannelDescriptors/list to get the list of
valid values such as &#34;email&#34;, &#34;slack&#34;, etc...
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} User-supplied key/value data that does not need to conform to the corresponding NotificationChannelDescriptor&#39;s schema,
unlike the labels field. This field is intended to be used for organizing and identifying the NotificationChannel
objects.The field can contain up to 64 entries. Each key and value is limited to 63 Unicode characters or 128 bytes,
whichever is smaller. Labels and values can contain only lowercase letters, numerals, underscores, and dashes. Keys must
begin with a letter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Verification<wbr>Status</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether this channel has been verified or not. On a ListNotificationChannels or GetNotificationChannel
operation, this field is expected to be populated.If the value is UNVERIFIED, then it indicates that the channel is
non-functioning (it both requires verification and lacks verification); otherwise, it is assumed that the channel
works.If the channel is neither VERIFIED nor UNVERIFIED, it implies that the channel is of a type that does not require
verification or that this specific channel has been exempted from verification because it was created prior to
verification being required for channels of this type.This field cannot be modified using a standard
UpdateNotificationChannel operation. To change the value of this field, you must call VerifyNotificationChannel.
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
            <td class="align-top">{{% md %}} An optional human-readable description of this notification channel. This description may provide additional details,
beyond the display name, for the channel. This may not exceed 1024 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} An optional human-readable name for this notification channel. It is recommended that you specify a non-empty and unique
name in order to make it easier to identify the channels in your project, though this is not enforced. The display name
is limited to 512 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether notifications are forwarded to the described channel. This makes it possible to disable delivery of
notifications to a particular channel without removing the channel from all alerting policies that reference the
channel. This is a more convenient approach when the change is temporary and you want to receive notifications from the
same set of alerting policies on the channel at some point in the future.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} Configuration fields that define the channel and its behavior. The permissible and required labels are specified in the
NotificationChannelDescriptor corresponding to the type field. **Note**: Some NotificationChannelDescriptor labels are
sensitive and the API will return an partially-obfuscated value. For example, for &#39;&#34;type&#34;: &#34;slack&#34;&#39; channels, an
&#39;auth_token&#39; label with value &#34;SECRET&#34; will be obfuscated as &#34;**CRET&#34;. In order to avoid a diff, Terraform will use the
state value if it appears that the obfuscated value matches the state value in length/unobfuscated characters. However,
Terraform will not detect a diff if the obfuscated portion of the value was changed outside of Terraform.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The full REST resource name for this channel. The syntax is: projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID] The
[CHANNEL_ID] is automatically assigned by the server on creation.
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
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The type of the notification channel. This field matches the value of the NotificationChannelDescriptor.type field. See
https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.notificationChannelDescriptors/list to get the list of
valid values such as &#34;email&#34;, &#34;slack&#34;, etc...
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} User-supplied key/value data that does not need to conform to the corresponding NotificationChannelDescriptor&#39;s schema,
unlike the labels field. This field is intended to be used for organizing and identifying the NotificationChannel
objects.The field can contain up to 64 entries. Each key and value is limited to 63 Unicode characters or 128 bytes,
whichever is smaller. Labels and values can contain only lowercase letters, numerals, underscores, and dashes. Keys must
begin with a letter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">verification<wbr>Status</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether this channel has been verified or not. On a ListNotificationChannels or GetNotificationChannel
operation, this field is expected to be populated.If the value is UNVERIFIED, then it indicates that the channel is
non-functioning (it both requires verification and lacks verification); otherwise, it is assumed that the channel
works.If the channel is neither VERIFIED nor UNVERIFIED, it implies that the channel is of a type that does not require
verification or that this specific channel has been exempted from verification because it was created prior to
verification being required for channels of this type.This field cannot be modified using a standard
UpdateNotificationChannel operation. To change the value of this field, you must call VerifyNotificationChannel.
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
            <td class="align-top">{{% md %}} An optional human-readable description of this notification channel. This description may provide additional details,
beyond the display name, for the channel. This may not exceed 1024 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} An optional human-readable name for this notification channel. It is recommended that you specify a non-empty and unique
name in order to make it easier to identify the channels in your project, though this is not enforced. The display name
is limited to 512 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether notifications are forwarded to the described channel. This makes it possible to disable delivery of
notifications to a particular channel without removing the channel from all alerting policies that reference the
channel. This is a more convenient approach when the change is temporary and you want to receive notifications from the
same set of alerting policies on the channel at some point in the future.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} Configuration fields that define the channel and its behavior. The permissible and required labels are specified in the
NotificationChannelDescriptor corresponding to the type field. **Note**: Some NotificationChannelDescriptor labels are
sensitive and the API will return an partially-obfuscated value. For example, for &#39;&#34;type&#34;: &#34;slack&#34;&#39; channels, an
&#39;auth_token&#39; label with value &#34;SECRET&#34; will be obfuscated as &#34;**CRET&#34;. In order to avoid a diff, Terraform will use the
state value if it appears that the obfuscated value matches the state value in length/unobfuscated characters. However,
Terraform will not detect a diff if the obfuscated portion of the value was changed outside of Terraform.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The full REST resource name for this channel. The syntax is: projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID] The
[CHANNEL_ID] is automatically assigned by the server on creation.
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
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The type of the notification channel. This field matches the value of the NotificationChannelDescriptor.type field. See
https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.notificationChannelDescriptors/list to get the list of
valid values such as &#34;email&#34;, &#34;slack&#34;, etc...
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user_<wbr>labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} User-supplied key/value data that does not need to conform to the corresponding NotificationChannelDescriptor&#39;s schema,
unlike the labels field. This field is intended to be used for organizing and identifying the NotificationChannel
objects.The field can contain up to 64 entries. Each key and value is limited to 63 Unicode characters or 128 bytes,
whichever is smaller. Labels and values can contain only lowercase letters, numerals, underscores, and dashes. Keys must
begin with a letter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">verification_<wbr>status</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether this channel has been verified or not. On a ListNotificationChannels or GetNotificationChannel
operation, this field is expected to be populated.If the value is UNVERIFIED, then it indicates that the channel is
non-functioning (it both requires verification and lacks verification); otherwise, it is assumed that the channel
works.If the channel is neither VERIFIED nor UNVERIFIED, it implies that the channel is of a type that does not require
verification or that this specific channel has been exempted from verification because it was created prior to
verification being required for channels of this type.This field cannot be modified using a standard
UpdateNotificationChannel operation. To change the value of this field, you must call VerifyNotificationChannel.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing NotificationChannel Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/monitoring/#NotificationChannelState">NotificationChannelState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/monitoring/#NotificationChannel">NotificationChannel</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>description=None<span class="p">, </span>display_name=None<span class="p">, </span>enabled=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>type=None<span class="p">, </span>user_labels=None<span class="p">, </span>verification_status=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetNotificationChannel<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#NotificationChannelState">NotificationChannelState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#NotificationChannel">NotificationChannel</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.NotificationChannel.html">NotificationChannel</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.NotificationChannelState.html">NotificationChannelState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing NotificationChannel resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional human-readable description of this notification channel. This description may provide additional details,
beyond the display name, for the channel. This may not exceed 1024 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional human-readable name for this notification channel. It is recommended that you specify a non-empty and unique
name in order to make it easier to identify the channels in your project, though this is not enforced. The display name
is limited to 512 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether notifications are forwarded to the described channel. This makes it possible to disable delivery of
notifications to a particular channel without removing the channel from all alerting policies that reference the
channel. This is a more convenient approach when the change is temporary and you want to receive notifications from the
same set of alerting policies on the channel at some point in the future.
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
Configuration fields that define the channel and its behavior. The permissible and required labels are specified in the
NotificationChannelDescriptor corresponding to the type field. **Note**: Some NotificationChannelDescriptor labels are
sensitive and the API will return an partially-obfuscated value. For example, for &#39;&#34;type&#34;: &#34;slack&#34;&#39; channels, an
&#39;auth_token&#39; label with value &#34;SECRET&#34; will be obfuscated as &#34;**CRET&#34;. In order to avoid a diff, Terraform will use the
state value if it appears that the obfuscated value matches the state value in length/unobfuscated characters. However,
Terraform will not detect a diff if the obfuscated portion of the value was changed outside of Terraform.
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
The full REST resource name for this channel. The syntax is: projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID] The
[CHANNEL_ID] is automatically assigned by the server on creation.
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
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The type of the notification channel. This field matches the value of the NotificationChannelDescriptor.type field. See
https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.notificationChannelDescriptors/list to get the list of
valid values such as &#34;email&#34;, &#34;slack&#34;, etc...
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-supplied key/value data that does not need to conform to the corresponding NotificationChannelDescriptor&#39;s schema,
unlike the labels field. This field is intended to be used for organizing and identifying the NotificationChannel
objects.The field can contain up to 64 entries. Each key and value is limited to 63 Unicode characters or 128 bytes,
whichever is smaller. Labels and values can contain only lowercase letters, numerals, underscores, and dashes. Keys must
begin with a letter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Verification<wbr>Status</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether this channel has been verified or not. On a ListNotificationChannels or GetNotificationChannel
operation, this field is expected to be populated.If the value is UNVERIFIED, then it indicates that the channel is
non-functioning (it both requires verification and lacks verification); otherwise, it is assumed that the channel
works.If the channel is neither VERIFIED nor UNVERIFIED, it implies that the channel is of a type that does not require
verification or that this specific channel has been exempted from verification because it was created prior to
verification being required for channels of this type.This field cannot be modified using a standard
UpdateNotificationChannel operation. To change the value of this field, you must call VerifyNotificationChannel.
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
An optional human-readable description of this notification channel. This description may provide additional details,
beyond the display name, for the channel. This may not exceed 1024 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional human-readable name for this notification channel. It is recommended that you specify a non-empty and unique
name in order to make it easier to identify the channels in your project, though this is not enforced. The display name
is limited to 512 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether notifications are forwarded to the described channel. This makes it possible to disable delivery of
notifications to a particular channel without removing the channel from all alerting policies that reference the
channel. This is a more convenient approach when the change is temporary and you want to receive notifications from the
same set of alerting policies on the channel at some point in the future.
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
Configuration fields that define the channel and its behavior. The permissible and required labels are specified in the
NotificationChannelDescriptor corresponding to the type field. **Note**: Some NotificationChannelDescriptor labels are
sensitive and the API will return an partially-obfuscated value. For example, for &#39;&#34;type&#34;: &#34;slack&#34;&#39; channels, an
&#39;auth_token&#39; label with value &#34;SECRET&#34; will be obfuscated as &#34;**CRET&#34;. In order to avoid a diff, Terraform will use the
state value if it appears that the obfuscated value matches the state value in length/unobfuscated characters. However,
Terraform will not detect a diff if the obfuscated portion of the value was changed outside of Terraform.
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
The full REST resource name for this channel. The syntax is: projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID] The
[CHANNEL_ID] is automatically assigned by the server on creation.
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
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The type of the notification channel. This field matches the value of the NotificationChannelDescriptor.type field. See
https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.notificationChannelDescriptors/list to get the list of
valid values such as &#34;email&#34;, &#34;slack&#34;, etc...
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-supplied key/value data that does not need to conform to the corresponding NotificationChannelDescriptor&#39;s schema,
unlike the labels field. This field is intended to be used for organizing and identifying the NotificationChannel
objects.The field can contain up to 64 entries. Each key and value is limited to 63 Unicode characters or 128 bytes,
whichever is smaller. Labels and values can contain only lowercase letters, numerals, underscores, and dashes. Keys must
begin with a letter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Verification<wbr>Status</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether this channel has been verified or not. On a ListNotificationChannels or GetNotificationChannel
operation, this field is expected to be populated.If the value is UNVERIFIED, then it indicates that the channel is
non-functioning (it both requires verification and lacks verification); otherwise, it is assumed that the channel
works.If the channel is neither VERIFIED nor UNVERIFIED, it implies that the channel is of a type that does not require
verification or that this specific channel has been exempted from verification because it was created prior to
verification being required for channels of this type.This field cannot be modified using a standard
UpdateNotificationChannel operation. To change the value of this field, you must call VerifyNotificationChannel.
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
An optional human-readable description of this notification channel. This description may provide additional details,
beyond the display name, for the channel. This may not exceed 1024 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional human-readable name for this notification channel. It is recommended that you specify a non-empty and unique
name in order to make it easier to identify the channels in your project, though this is not enforced. The display name
is limited to 512 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether notifications are forwarded to the described channel. This makes it possible to disable delivery of
notifications to a particular channel without removing the channel from all alerting policies that reference the
channel. This is a more convenient approach when the change is temporary and you want to receive notifications from the
same set of alerting policies on the channel at some point in the future.
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
Configuration fields that define the channel and its behavior. The permissible and required labels are specified in the
NotificationChannelDescriptor corresponding to the type field. **Note**: Some NotificationChannelDescriptor labels are
sensitive and the API will return an partially-obfuscated value. For example, for &#39;&#34;type&#34;: &#34;slack&#34;&#39; channels, an
&#39;auth_token&#39; label with value &#34;SECRET&#34; will be obfuscated as &#34;**CRET&#34;. In order to avoid a diff, Terraform will use the
state value if it appears that the obfuscated value matches the state value in length/unobfuscated characters. However,
Terraform will not detect a diff if the obfuscated portion of the value was changed outside of Terraform.
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
The full REST resource name for this channel. The syntax is: projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID] The
[CHANNEL_ID] is automatically assigned by the server on creation.
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
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The type of the notification channel. This field matches the value of the NotificationChannelDescriptor.type field. See
https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.notificationChannelDescriptors/list to get the list of
valid values such as &#34;email&#34;, &#34;slack&#34;, etc...
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-supplied key/value data that does not need to conform to the corresponding NotificationChannelDescriptor&#39;s schema,
unlike the labels field. This field is intended to be used for organizing and identifying the NotificationChannel
objects.The field can contain up to 64 entries. Each key and value is limited to 63 Unicode characters or 128 bytes,
whichever is smaller. Labels and values can contain only lowercase letters, numerals, underscores, and dashes. Keys must
begin with a letter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">verification<wbr>Status</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether this channel has been verified or not. On a ListNotificationChannels or GetNotificationChannel
operation, this field is expected to be populated.If the value is UNVERIFIED, then it indicates that the channel is
non-functioning (it both requires verification and lacks verification); otherwise, it is assumed that the channel
works.If the channel is neither VERIFIED nor UNVERIFIED, it implies that the channel is of a type that does not require
verification or that this specific channel has been exempted from verification because it was created prior to
verification being required for channels of this type.This field cannot be modified using a standard
UpdateNotificationChannel operation. To change the value of this field, you must call VerifyNotificationChannel.
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
An optional human-readable description of this notification channel. This description may provide additional details,
beyond the display name, for the channel. This may not exceed 1024 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional human-readable name for this notification channel. It is recommended that you specify a non-empty and unique
name in order to make it easier to identify the channels in your project, though this is not enforced. The display name
is limited to 512 Unicode characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether notifications are forwarded to the described channel. This makes it possible to disable delivery of
notifications to a particular channel without removing the channel from all alerting policies that reference the
channel. This is a more convenient approach when the change is temporary and you want to receive notifications from the
same set of alerting policies on the channel at some point in the future.
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
Configuration fields that define the channel and its behavior. The permissible and required labels are specified in the
NotificationChannelDescriptor corresponding to the type field. **Note**: Some NotificationChannelDescriptor labels are
sensitive and the API will return an partially-obfuscated value. For example, for &#39;&#34;type&#34;: &#34;slack&#34;&#39; channels, an
&#39;auth_token&#39; label with value &#34;SECRET&#34; will be obfuscated as &#34;**CRET&#34;. In order to avoid a diff, Terraform will use the
state value if it appears that the obfuscated value matches the state value in length/unobfuscated characters. However,
Terraform will not detect a diff if the obfuscated portion of the value was changed outside of Terraform.
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
The full REST resource name for this channel. The syntax is: projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID] The
[CHANNEL_ID] is automatically assigned by the server on creation.
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
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The type of the notification channel. This field matches the value of the NotificationChannelDescriptor.type field. See
https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.notificationChannelDescriptors/list to get the list of
valid values such as &#34;email&#34;, &#34;slack&#34;, etc...
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user_<wbr>labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-supplied key/value data that does not need to conform to the corresponding NotificationChannelDescriptor&#39;s schema,
unlike the labels field. This field is intended to be used for organizing and identifying the NotificationChannel
objects.The field can contain up to 64 entries. Each key and value is limited to 63 Unicode characters or 128 bytes,
whichever is smaller. Labels and values can contain only lowercase letters, numerals, underscores, and dashes. Keys must
begin with a letter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">verification_<wbr>status</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether this channel has been verified or not. On a ListNotificationChannels or GetNotificationChannel
operation, this field is expected to be populated.If the value is UNVERIFIED, then it indicates that the channel is
non-functioning (it both requires verification and lacks verification); otherwise, it is assumed that the channel
works.If the channel is neither VERIFIED nor UNVERIFIED, it implies that the channel is of a type that does not require
verification or that this specific channel has been exempted from verification because it was created prior to
verification being required for channels of this type.This field cannot be modified using a standard
UpdateNotificationChannel operation. To change the value of this field, you must call VerifyNotificationChannel.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










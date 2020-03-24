
---
title: "AlertPolicy"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

A description of the conditions under which some aspect of your system is
considered to be "unhealthy" and the ways to notify people or services
about this state.


To get more information about AlertPolicy, see:

* [API documentation](https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.alertPolicies)
* How-to Guides
    * [Official Documentation](https://cloud.google.com/monitoring/alerts/)

## Example Usage - Monitoring Alert Policy Basic


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const alertPolicy = new gcp.monitoring.AlertPolicy("alert_policy", {
    combiner: "OR",
    conditions: [{
        conditionThreshold: {
            aggregations: [{
                alignmentPeriod: "60s",
                perSeriesAligner: "ALIGN_RATE",
            }],
            comparison: "COMPARISON_GT",
            duration: "60s",
            filter: "metric.type=\"compute.googleapis.com/instance/disk/write_bytes_count\" AND resource.type=\"gce_instance\"",
        },
        displayName: "test condition",
    }],
    displayName: "My Alert Policy",
    userLabels: {
        foo: "bar",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/monitoring_alert_policy.html.markdown.



## Create a AlertPolicy Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/monitoring/#AlertPolicy">AlertPolicy</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/monitoring/#AlertPolicyArgs">AlertPolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">AlertPolicy</span><span class="p">(resource_name, opts=None, </span>combiner=None<span class="p">, </span>conditions=None<span class="p">, </span>display_name=None<span class="p">, </span>documentation=None<span class="p">, </span>enabled=None<span class="p">, </span>notification_channels=None<span class="p">, </span>project=None<span class="p">, </span>user_labels=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewAlertPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyArgs">AlertPolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicy">AlertPolicy</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicy.html">AlertPolicy</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyArgs.html">AlertPolicyArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a AlertPolicy resource with the given unique name, arguments, and options.

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
            <td class="align-top">Combiner</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How to combine the results of multiple conditions to determine if an incident should be opened.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Conditions</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycondition">List&lt;Alert<wbr>Policy<wbr>Condition<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of conditions for the policy. The conditions are combined by AND or OR according to the combiner field. If the
combined conditions evaluate to true, then an incident is created. A policy can have from one to six conditions.
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
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Documentation</td>
            <td class="align-top">
                
                <code><a href="#alertpolicydocumentation">Alert<wbr>Policy<wbr>Documentation<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
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
Whether or not the policy is enabled. The default is true.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Channels</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifies the notification channels to which notifications should be sent when incidents are opened or closed or when
new violations occur on an already opened incident. Each element of this array corresponds to the name field in each of
the NotificationChannel objects that are returned from the notificationChannels.list method. The syntax of the entries
in this field is &#39;projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID]&#39;
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
This field is intended to be used for organizing and identifying the AlertPolicy objects.The field can contain up to 64
entries. Each key and value is limited to 63 Unicode characters or 128 bytes, whichever is smaller. Labels and values
can contain only lowercase letters, numerals, underscores, and dashes. Keys must begin with a letter.
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
            <td class="align-top">Combiner</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How to combine the results of multiple conditions to determine if an incident should be opened.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Conditions</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycondition">[]Alert<wbr>Policy<wbr>Condition</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of conditions for the policy. The conditions are combined by AND or OR according to the combiner field. If the
combined conditions evaluate to true, then an incident is created. A policy can have from one to six conditions.
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
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Documentation</td>
            <td class="align-top">
                
                <code><a href="#alertpolicydocumentation">*Alert<wbr>Policy<wbr>Documentation</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
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
Whether or not the policy is enabled. The default is true.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Channels</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifies the notification channels to which notifications should be sent when incidents are opened or closed or when
new violations occur on an already opened incident. Each element of this array corresponds to the name field in each of
the NotificationChannel objects that are returned from the notificationChannels.list method. The syntax of the entries
in this field is &#39;projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID]&#39;
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
This field is intended to be used for organizing and identifying the AlertPolicy objects.The field can contain up to 64
entries. Each key and value is limited to 63 Unicode characters or 128 bytes, whichever is smaller. Labels and values
can contain only lowercase letters, numerals, underscores, and dashes. Keys must begin with a letter.
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
            <td class="align-top">combiner</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How to combine the results of multiple conditions to determine if an incident should be opened.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">conditions</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycondition">Alert<wbr>Policy<wbr>Condition[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of conditions for the policy. The conditions are combined by AND or OR according to the combiner field. If the
combined conditions evaluate to true, then an incident is created. A policy can have from one to six conditions.
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
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">documentation</td>
            <td class="align-top">
                
                <code><a href="#alertpolicydocumentation">Alert<wbr>Policy<wbr>Documentation?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
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
Whether or not the policy is enabled. The default is true.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification<wbr>Channels</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifies the notification channels to which notifications should be sent when incidents are opened or closed or when
new violations occur on an already opened incident. Each element of this array corresponds to the name field in each of
the NotificationChannel objects that are returned from the notificationChannels.list method. The syntax of the entries
in this field is &#39;projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID]&#39;
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
This field is intended to be used for organizing and identifying the AlertPolicy objects.The field can contain up to 64
entries. Each key and value is limited to 63 Unicode characters or 128 bytes, whichever is smaller. Labels and values
can contain only lowercase letters, numerals, underscores, and dashes. Keys must begin with a letter.
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
            <td class="align-top">combiner</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How to combine the results of multiple conditions to determine if an incident should be opened.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">conditions</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycondition">List[Alert<wbr>Policy<wbr>Condition]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of conditions for the policy. The conditions are combined by AND or OR according to the combiner field. If the
combined conditions evaluate to true, then an incident is created. A policy can have from one to six conditions.
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
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">documentation</td>
            <td class="align-top">
                
                <code><a href="#alertpolicydocumentation">Dict[Alert<wbr>Policy<wbr>Documentation]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
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
Whether or not the policy is enabled. The default is true.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification_<wbr>channels</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifies the notification channels to which notifications should be sent when incidents are opened or closed or when
new violations occur on an already opened incident. Each element of this array corresponds to the name field in each of
the NotificationChannel objects that are returned from the notificationChannels.list method. The syntax of the entries
in this field is &#39;projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID]&#39;
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
This field is intended to be used for organizing and identifying the AlertPolicy objects.The field can contain up to 64
entries. Each key and value is limited to 63 Unicode characters or 128 bytes, whichever is smaller. Labels and values
can contain only lowercase letters, numerals, underscores, and dashes. Keys must begin with a letter.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## AlertPolicy Output Properties

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
            <td class="align-top">Combiner</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} How to combine the results of multiple conditions to determine if an incident should be opened.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Conditions</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycondition">List&lt;Alert<wbr>Policy<wbr>Condition&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of conditions for the policy. The conditions are combined by AND or OR according to the combiner field. If the
combined conditions evaluate to true, then an incident is created. A policy can have from one to six conditions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Record</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycreationrecord">Alert<wbr>Policy<wbr>Creation<wbr>Record</a></code>
            </td>
            <td class="align-top">{{% md %}} A read-only record of the creation of the alerting policy. If provided in a call to create or update, this field will be
ignored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Documentation</td>
            <td class="align-top">
                
                <code><a href="#alertpolicydocumentation">Alert<wbr>Policy<wbr>Documentation?</a></code>
            </td>
            <td class="align-top">{{% md %}} A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether or not the policy is enabled. The default is true.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique resource name for this policy. Its syntax is: projects/[PROJECT_ID]/alertPolicies/[ALERT_POLICY_ID]
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Channels</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} Identifies the notification channels to which notifications should be sent when incidents are opened or closed or when
new violations occur on an already opened incident. Each element of this array corresponds to the name field in each of
the NotificationChannel objects that are returned from the notificationChannels.list method. The syntax of the entries
in this field is &#39;projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID]&#39;
 {{% /md %}}

            
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
            <td class="align-top">User<wbr>Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} This field is intended to be used for organizing and identifying the AlertPolicy objects.The field can contain up to 64
entries. Each key and value is limited to 63 Unicode characters or 128 bytes, whichever is smaller. Labels and values
can contain only lowercase letters, numerals, underscores, and dashes. Keys must begin with a letter.
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
            <td class="align-top">Combiner</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} How to combine the results of multiple conditions to determine if an incident should be opened.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Conditions</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycondition">[]Alert<wbr>Policy<wbr>Condition</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of conditions for the policy. The conditions are combined by AND or OR according to the combiner field. If the
combined conditions evaluate to true, then an incident is created. A policy can have from one to six conditions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Record</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycreationrecord">Alert<wbr>Policy<wbr>Creation<wbr>Record</a></code>
            </td>
            <td class="align-top">{{% md %}} A read-only record of the creation of the alerting policy. If provided in a call to create or update, this field will be
ignored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Documentation</td>
            <td class="align-top">
                
                <code><a href="#alertpolicydocumentation">*Alert<wbr>Policy<wbr>Documentation</a></code>
            </td>
            <td class="align-top">{{% md %}} A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether or not the policy is enabled. The default is true.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique resource name for this policy. Its syntax is: projects/[PROJECT_ID]/alertPolicies/[ALERT_POLICY_ID]
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Channels</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} Identifies the notification channels to which notifications should be sent when incidents are opened or closed or when
new violations occur on an already opened incident. Each element of this array corresponds to the name field in each of
the NotificationChannel objects that are returned from the notificationChannels.list method. The syntax of the entries
in this field is &#39;projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID]&#39;
 {{% /md %}}

            
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
            <td class="align-top">User<wbr>Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} This field is intended to be used for organizing and identifying the AlertPolicy objects.The field can contain up to 64
entries. Each key and value is limited to 63 Unicode characters or 128 bytes, whichever is smaller. Labels and values
can contain only lowercase letters, numerals, underscores, and dashes. Keys must begin with a letter.
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
            <td class="align-top">combiner</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} How to combine the results of multiple conditions to determine if an incident should be opened.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">conditions</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycondition">Alert<wbr>Policy<wbr>Condition[]</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of conditions for the policy. The conditions are combined by AND or OR according to the combiner field. If the
combined conditions evaluate to true, then an incident is created. A policy can have from one to six conditions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation<wbr>Record</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycreationrecord">Alert<wbr>Policy<wbr>Creation<wbr>Record</a></code>
            </td>
            <td class="align-top">{{% md %}} A read-only record of the creation of the alerting policy. If provided in a call to create or update, this field will be
ignored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">documentation</td>
            <td class="align-top">
                
                <code><a href="#alertpolicydocumentation">Alert<wbr>Policy<wbr>Documentation?</a></code>
            </td>
            <td class="align-top">{{% md %}} A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether or not the policy is enabled. The default is true.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique resource name for this policy. Its syntax is: projects/[PROJECT_ID]/alertPolicies/[ALERT_POLICY_ID]
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification<wbr>Channels</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} Identifies the notification channels to which notifications should be sent when incidents are opened or closed or when
new violations occur on an already opened incident. Each element of this array corresponds to the name field in each of
the NotificationChannel objects that are returned from the notificationChannels.list method. The syntax of the entries
in this field is &#39;projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID]&#39;
 {{% /md %}}

            
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
            <td class="align-top">user<wbr>Labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} This field is intended to be used for organizing and identifying the AlertPolicy objects.The field can contain up to 64
entries. Each key and value is limited to 63 Unicode characters or 128 bytes, whichever is smaller. Labels and values
can contain only lowercase letters, numerals, underscores, and dashes. Keys must begin with a letter.
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
            <td class="align-top">combiner</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} How to combine the results of multiple conditions to determine if an incident should be opened.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">conditions</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycondition">List[Alert<wbr>Policy<wbr>Condition]</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of conditions for the policy. The conditions are combined by AND or OR according to the combiner field. If the
combined conditions evaluate to true, then an incident is created. A policy can have from one to six conditions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation_<wbr>record</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycreationrecord">Dict[Alert<wbr>Policy<wbr>Creation<wbr>Record]</a></code>
            </td>
            <td class="align-top">{{% md %}} A read-only record of the creation of the alerting policy. If provided in a call to create or update, this field will be
ignored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">documentation</td>
            <td class="align-top">
                
                <code><a href="#alertpolicydocumentation">Dict[Alert<wbr>Policy<wbr>Documentation]</a></code>
            </td>
            <td class="align-top">{{% md %}} A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether or not the policy is enabled. The default is true.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The unique resource name for this policy. Its syntax is: projects/[PROJECT_ID]/alertPolicies/[ALERT_POLICY_ID]
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification_<wbr>channels</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} Identifies the notification channels to which notifications should be sent when incidents are opened or closed or when
new violations occur on an already opened incident. Each element of this array corresponds to the name field in each of
the NotificationChannel objects that are returned from the notificationChannels.list method. The syntax of the entries
in this field is &#39;projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID]&#39;
 {{% /md %}}

            
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
            <td class="align-top">user_<wbr>labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} This field is intended to be used for organizing and identifying the AlertPolicy objects.The field can contain up to 64
entries. Each key and value is limited to 63 Unicode characters or 128 bytes, whichever is smaller. Labels and values
can contain only lowercase letters, numerals, underscores, and dashes. Keys must begin with a letter.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing AlertPolicy Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/monitoring/#AlertPolicyState">AlertPolicyState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/monitoring/#AlertPolicy">AlertPolicy</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>combiner=None<span class="p">, </span>conditions=None<span class="p">, </span>creation_record=None<span class="p">, </span>display_name=None<span class="p">, </span>documentation=None<span class="p">, </span>enabled=None<span class="p">, </span>name=None<span class="p">, </span>notification_channels=None<span class="p">, </span>project=None<span class="p">, </span>user_labels=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAlertPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyState">AlertPolicyState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicy">AlertPolicy</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicy.html">AlertPolicy</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyState.html">AlertPolicyState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing AlertPolicy resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Combiner</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How to combine the results of multiple conditions to determine if an incident should be opened.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Conditions</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycondition">List&lt;Alert<wbr>Policy<wbr>Condition<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of conditions for the policy. The conditions are combined by AND or OR according to the combiner field. If the
combined conditions evaluate to true, then an incident is created. A policy can have from one to six conditions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Record</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycreationrecord">Alert<wbr>Policy<wbr>Creation<wbr>Record<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A read-only record of the creation of the alerting policy. If provided in a call to create or update, this field will be
ignored.
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
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Documentation</td>
            <td class="align-top">
                
                <code><a href="#alertpolicydocumentation">Alert<wbr>Policy<wbr>Documentation<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
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
Whether or not the policy is enabled. The default is true.
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
The unique resource name for this policy. Its syntax is: projects/[PROJECT_ID]/alertPolicies/[ALERT_POLICY_ID]
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Channels</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifies the notification channels to which notifications should be sent when incidents are opened or closed or when
new violations occur on an already opened incident. Each element of this array corresponds to the name field in each of
the NotificationChannel objects that are returned from the notificationChannels.list method. The syntax of the entries
in this field is &#39;projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID]&#39;
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
This field is intended to be used for organizing and identifying the AlertPolicy objects.The field can contain up to 64
entries. Each key and value is limited to 63 Unicode characters or 128 bytes, whichever is smaller. Labels and values
can contain only lowercase letters, numerals, underscores, and dashes. Keys must begin with a letter.
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
            <td class="align-top">Combiner</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How to combine the results of multiple conditions to determine if an incident should be opened.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Conditions</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycondition">[]Alert<wbr>Policy<wbr>Condition</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of conditions for the policy. The conditions are combined by AND or OR according to the combiner field. If the
combined conditions evaluate to true, then an incident is created. A policy can have from one to six conditions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Record</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycreationrecord">*Alert<wbr>Policy<wbr>Creation<wbr>Record</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A read-only record of the creation of the alerting policy. If provided in a call to create or update, this field will be
ignored.
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
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Documentation</td>
            <td class="align-top">
                
                <code><a href="#alertpolicydocumentation">*Alert<wbr>Policy<wbr>Documentation</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
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
Whether or not the policy is enabled. The default is true.
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
The unique resource name for this policy. Its syntax is: projects/[PROJECT_ID]/alertPolicies/[ALERT_POLICY_ID]
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Notification<wbr>Channels</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifies the notification channels to which notifications should be sent when incidents are opened or closed or when
new violations occur on an already opened incident. Each element of this array corresponds to the name field in each of
the NotificationChannel objects that are returned from the notificationChannels.list method. The syntax of the entries
in this field is &#39;projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID]&#39;
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
This field is intended to be used for organizing and identifying the AlertPolicy objects.The field can contain up to 64
entries. Each key and value is limited to 63 Unicode characters or 128 bytes, whichever is smaller. Labels and values
can contain only lowercase letters, numerals, underscores, and dashes. Keys must begin with a letter.
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
            <td class="align-top">combiner</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How to combine the results of multiple conditions to determine if an incident should be opened.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">conditions</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycondition">Alert<wbr>Policy<wbr>Condition[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of conditions for the policy. The conditions are combined by AND or OR according to the combiner field. If the
combined conditions evaluate to true, then an incident is created. A policy can have from one to six conditions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation<wbr>Record</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycreationrecord">Alert<wbr>Policy<wbr>Creation<wbr>Record?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A read-only record of the creation of the alerting policy. If provided in a call to create or update, this field will be
ignored.
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
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">documentation</td>
            <td class="align-top">
                
                <code><a href="#alertpolicydocumentation">Alert<wbr>Policy<wbr>Documentation?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
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
Whether or not the policy is enabled. The default is true.
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
The unique resource name for this policy. Its syntax is: projects/[PROJECT_ID]/alertPolicies/[ALERT_POLICY_ID]
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification<wbr>Channels</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifies the notification channels to which notifications should be sent when incidents are opened or closed or when
new violations occur on an already opened incident. Each element of this array corresponds to the name field in each of
the NotificationChannel objects that are returned from the notificationChannels.list method. The syntax of the entries
in this field is &#39;projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID]&#39;
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
This field is intended to be used for organizing and identifying the AlertPolicy objects.The field can contain up to 64
entries. Each key and value is limited to 63 Unicode characters or 128 bytes, whichever is smaller. Labels and values
can contain only lowercase letters, numerals, underscores, and dashes. Keys must begin with a letter.
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
            <td class="align-top">combiner</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How to combine the results of multiple conditions to determine if an incident should be opened.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">conditions</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycondition">List[Alert<wbr>Policy<wbr>Condition]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of conditions for the policy. The conditions are combined by AND or OR according to the combiner field. If the
combined conditions evaluate to true, then an incident is created. A policy can have from one to six conditions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation_<wbr>record</td>
            <td class="align-top">
                
                <code><a href="#alertpolicycreationrecord">Dict[Alert<wbr>Policy<wbr>Creation<wbr>Record]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A read-only record of the creation of the alerting policy. If provided in a call to create or update, this field will be
ignored.
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
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">documentation</td>
            <td class="align-top">
                
                <code><a href="#alertpolicydocumentation">Dict[Alert<wbr>Policy<wbr>Documentation]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A short name or phrase used to identify the policy in dashboards, notifications, and incidents. To avoid confusion,
don&#39;t use the same display name for multiple policies in the same project. The name is limited to 512 Unicode
characters.
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
Whether or not the policy is enabled. The default is true.
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
The unique resource name for this policy. Its syntax is: projects/[PROJECT_ID]/alertPolicies/[ALERT_POLICY_ID]
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">notification_<wbr>channels</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifies the notification channels to which notifications should be sent when incidents are opened or closed or when
new violations occur on an already opened incident. Each element of this array corresponds to the name field in each of
the NotificationChannel objects that are returned from the notificationChannels.list method. The syntax of the entries
in this field is &#39;projects/[PROJECT_ID]/notificationChannels/[CHANNEL_ID]&#39;
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
This field is intended to be used for organizing and identifying the AlertPolicy objects.The field can contain up to 64
entries. Each key and value is limited to 63 Unicode characters or 128 bytes, whichever is smaller. Labels and values
can contain only lowercase letters, numerals, underscores, and dashes. Keys must begin with a letter.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### AlertPolicyCondition
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#AlertPolicyCondition">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#AlertPolicyCondition">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyConditionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyCondition.html">output</a> API doc for this type.
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
            <td class="align-top">Condition<wbr>Absent</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionabsent">Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Absent<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Condition<wbr>Threshold</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthreshold">Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Condition<wbr>Absent</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionabsent">*Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Absent</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Condition<wbr>Threshold</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthreshold">*Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">condition<wbr>Absent</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionabsent">Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Absent?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">condition<wbr>Threshold</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthreshold">Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">condition<wbr>Absent</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionabsent">Dict[Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Absent]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">condition<wbr>Threshold</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthreshold">Dict[Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### AlertPolicyConditionConditionAbsent
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#AlertPolicyConditionConditionAbsent">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#AlertPolicyConditionConditionAbsent">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionConditionAbsentArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionConditionAbsentOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyConditionConditionAbsentArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyConditionConditionAbsent.html">output</a> API doc for this type.
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
            <td class="align-top">Aggregations</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionabsentaggregation">List&lt;Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Absent<wbr>Aggregation<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Duration</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trigger</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionabsenttrigger">Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Absent<wbr>Trigger<wbr>Args?</a></code>
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
            <td class="align-top">Aggregations</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionabsentaggregation">[]Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Absent<wbr>Aggregation</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Duration</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trigger</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionabsenttrigger">*Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Absent<wbr>Trigger</a></code>
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
            <td class="align-top">aggregations</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionabsentaggregation">Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Absent<wbr>Aggregation[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">duration</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trigger</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionabsenttrigger">Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Absent<wbr>Trigger?</a></code>
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
            <td class="align-top">aggregations</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionabsentaggregation">List[Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Absent<wbr>Aggregation]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">duration</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trigger</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionabsenttrigger">Dict[Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Absent<wbr>Trigger]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### AlertPolicyConditionConditionAbsentAggregation
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#AlertPolicyConditionConditionAbsentAggregation">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#AlertPolicyConditionConditionAbsentAggregation">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionConditionAbsentAggregationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionConditionAbsentAggregationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyConditionConditionAbsentAggregationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyConditionConditionAbsentAggregation.html">output</a> API doc for this type.
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
            <td class="align-top">Alignment<wbr>Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cross<wbr>Series<wbr>Reducer</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>By<wbr>Fields</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Per<wbr>Series<wbr>Aligner</td>
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
            <td class="align-top">Alignment<wbr>Period</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cross<wbr>Series<wbr>Reducer</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>By<wbr>Fields</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Per<wbr>Series<wbr>Aligner</td>
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
            <td class="align-top">alignment<wbr>Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cross<wbr>Series<wbr>Reducer</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group<wbr>By<wbr>Fields</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">per<wbr>Series<wbr>Aligner</td>
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
            <td class="align-top">alignment<wbr>Period</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cross<wbr>Series<wbr>Reducer</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group<wbr>By<wbr>Fields</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">per<wbr>Series<wbr>Aligner</td>
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





#### AlertPolicyConditionConditionAbsentTrigger
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#AlertPolicyConditionConditionAbsentTrigger">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#AlertPolicyConditionConditionAbsentTrigger">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionConditionAbsentTriggerArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionConditionAbsentTriggerOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyConditionConditionAbsentTriggerArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyConditionConditionAbsentTrigger.html">output</a> API doc for this type.
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
            <td class="align-top">Count</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Percent</td>
            <td class="align-top">
                
                <code>double?</code>
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
            <td class="align-top">Count</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Percent</td>
            <td class="align-top">
                
                <code>*float64</code>
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
            <td class="align-top">count</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">percent</td>
            <td class="align-top">
                
                <code>number?</code>
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
            <td class="align-top">count</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">percent</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### AlertPolicyConditionConditionThreshold
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#AlertPolicyConditionConditionThreshold">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#AlertPolicyConditionConditionThreshold">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionConditionThresholdArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionConditionThresholdOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyConditionConditionThresholdArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyConditionConditionThreshold.html">output</a> API doc for this type.
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
            <td class="align-top">Aggregations</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthresholdaggregation">List&lt;Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold<wbr>Aggregation<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Comparison</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Denominator<wbr>Aggregations</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthresholddenominatoraggregation">List&lt;Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold<wbr>Denominator<wbr>Aggregation<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Denominator<wbr>Filter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Duration</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Threshold<wbr>Value</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trigger</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthresholdtrigger">Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold<wbr>Trigger<wbr>Args?</a></code>
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
            <td class="align-top">Aggregations</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthresholdaggregation">[]Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold<wbr>Aggregation</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Comparison</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Denominator<wbr>Aggregations</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthresholddenominatoraggregation">[]Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold<wbr>Denominator<wbr>Aggregation</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Denominator<wbr>Filter</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Duration</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Threshold<wbr>Value</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trigger</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthresholdtrigger">*Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold<wbr>Trigger</a></code>
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
            <td class="align-top">aggregations</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthresholdaggregation">Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold<wbr>Aggregation[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">comparison</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">denominator<wbr>Aggregations</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthresholddenominatoraggregation">Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold<wbr>Denominator<wbr>Aggregation[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">denominator<wbr>Filter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">duration</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">threshold<wbr>Value</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trigger</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthresholdtrigger">Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold<wbr>Trigger?</a></code>
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
            <td class="align-top">aggregations</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthresholdaggregation">List[Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold<wbr>Aggregation]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">comparison</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">denominator<wbr>Aggregations</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthresholddenominatoraggregation">List[Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold<wbr>Denominator<wbr>Aggregation]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">denominator<wbr>Filter</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">duration</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">threshold<wbr>Value</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trigger</td>
            <td class="align-top">
                
                <code><a href="#alertpolicyconditionconditionthresholdtrigger">Dict[Alert<wbr>Policy<wbr>Condition<wbr>Condition<wbr>Threshold<wbr>Trigger]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### AlertPolicyConditionConditionThresholdAggregation
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#AlertPolicyConditionConditionThresholdAggregation">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#AlertPolicyConditionConditionThresholdAggregation">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionConditionThresholdAggregationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionConditionThresholdAggregationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyConditionConditionThresholdAggregationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyConditionConditionThresholdAggregation.html">output</a> API doc for this type.
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
            <td class="align-top">Alignment<wbr>Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cross<wbr>Series<wbr>Reducer</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>By<wbr>Fields</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Per<wbr>Series<wbr>Aligner</td>
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
            <td class="align-top">Alignment<wbr>Period</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cross<wbr>Series<wbr>Reducer</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>By<wbr>Fields</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Per<wbr>Series<wbr>Aligner</td>
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
            <td class="align-top">alignment<wbr>Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cross<wbr>Series<wbr>Reducer</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group<wbr>By<wbr>Fields</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">per<wbr>Series<wbr>Aligner</td>
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
            <td class="align-top">alignment<wbr>Period</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cross<wbr>Series<wbr>Reducer</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group<wbr>By<wbr>Fields</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">per<wbr>Series<wbr>Aligner</td>
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





#### AlertPolicyConditionConditionThresholdDenominatorAggregation
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#AlertPolicyConditionConditionThresholdDenominatorAggregation">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#AlertPolicyConditionConditionThresholdDenominatorAggregation">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionConditionThresholdDenominatorAggregationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionConditionThresholdDenominatorAggregationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyConditionConditionThresholdDenominatorAggregationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyConditionConditionThresholdDenominatorAggregation.html">output</a> API doc for this type.
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
            <td class="align-top">Alignment<wbr>Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cross<wbr>Series<wbr>Reducer</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>By<wbr>Fields</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Per<wbr>Series<wbr>Aligner</td>
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
            <td class="align-top">Alignment<wbr>Period</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cross<wbr>Series<wbr>Reducer</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>By<wbr>Fields</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Per<wbr>Series<wbr>Aligner</td>
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
            <td class="align-top">alignment<wbr>Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cross<wbr>Series<wbr>Reducer</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group<wbr>By<wbr>Fields</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">per<wbr>Series<wbr>Aligner</td>
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
            <td class="align-top">alignment<wbr>Period</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cross<wbr>Series<wbr>Reducer</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group<wbr>By<wbr>Fields</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">per<wbr>Series<wbr>Aligner</td>
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





#### AlertPolicyConditionConditionThresholdTrigger
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#AlertPolicyConditionConditionThresholdTrigger">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#AlertPolicyConditionConditionThresholdTrigger">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionConditionThresholdTriggerArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyConditionConditionThresholdTriggerOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyConditionConditionThresholdTriggerArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyConditionConditionThresholdTrigger.html">output</a> API doc for this type.
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
            <td class="align-top">Count</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Percent</td>
            <td class="align-top">
                
                <code>double?</code>
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
            <td class="align-top">Count</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Percent</td>
            <td class="align-top">
                
                <code>*float64</code>
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
            <td class="align-top">count</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">percent</td>
            <td class="align-top">
                
                <code>number?</code>
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
            <td class="align-top">count</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">percent</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### AlertPolicyCreationRecord
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#AlertPolicyCreationRecord">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyCreationRecordOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyCreationRecord.html">output</a> API doc for this type.
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
            <td class="align-top">Mutate<wbr>Time</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mutated<wbr>By</td>
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
            <td class="align-top">Mutate<wbr>Time</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mutated<wbr>By</td>
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
            <td class="align-top">mutate<wbr>Time</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mutated<wbr>By</td>
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
            <td class="align-top">mutate<wbr>Time</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mutated<wbr>By</td>
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





#### AlertPolicyDocumentation
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#AlertPolicyDocumentation">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#AlertPolicyDocumentation">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyDocumentationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#AlertPolicyDocumentationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyDocumentationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.AlertPolicyDocumentation.html">output</a> API doc for this type.
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
            <td class="align-top">Content</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mime<wbr>Type</td>
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
            <td class="align-top">Content</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mime<wbr>Type</td>
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
            <td class="align-top">content</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mime<wbr>Type</td>
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
            <td class="align-top">content</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mime<wbr>Type</td>
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








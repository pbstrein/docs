
---
title: "UptimeCheckConfig"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a UptimeCheckConfig Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/monitoring/#UptimeCheckConfig">UptimeCheckConfig</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/monitoring/#UptimeCheckConfigArgs">UptimeCheckConfigArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">UptimeCheckConfig</span><span class="p">(resource_name, opts=None, </span>content_matchers=None<span class="p">, </span>display_name=None<span class="p">, </span>http_check=None<span class="p">, </span>monitored_resource=None<span class="p">, </span>period=None<span class="p">, </span>project=None<span class="p">, </span>resource_group=None<span class="p">, </span>selected_regions=None<span class="p">, </span>tcp_check=None<span class="p">, </span>timeout=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewUptimeCheckConfig<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfigArgs">UptimeCheckConfigArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfig">UptimeCheckConfig</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfig.html">UptimeCheckConfig</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfigArgs.html">UptimeCheckConfigArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a UptimeCheckConfig resource with the given unique name, arguments, and options.

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
            <td class="align-top">Content<wbr>Matchers</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigcontentmatcher">List&lt;Uptime<wbr>Check<wbr>Config<wbr>Content<wbr>Matcher<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The expected content on the page the check is run against. Currently, only the first entry in the list is supported, and
other entries will be ignored. The server will look for an exact match of the string in the page response&#39;s content.
This field is optional and should only be specified if a content match is required.
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
A human-friendly name for the uptime check configuration. The display name should be unique within a Stackdriver
Workspace in order to make it easier to identify; however, uniqueness is not enforced.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheck">Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make an HTTP or HTTPS check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Monitored<wbr>Resource</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigmonitoredresource">Uptime<wbr>Check<wbr>Config<wbr>Monitored<wbr>Resource<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitored resource (https://cloud.google.com/monitoring/api/resources) associated with the configuration. The
following monitored resource types are supported for uptime checks: uptime_url gce_instance gae_app aws_ec2_instance
aws_elb_load_balancer
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often, in seconds, the uptime check is performed. Currently, the only supported values are 60s (1 minute), 300s (5
minutes), 600s (10 minutes), and 900s (15 minutes). Optional, defaults to 300s.
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
            <td class="align-top">Resource<wbr>Group</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigresourcegroup">Uptime<wbr>Check<wbr>Config<wbr>Resource<wbr>Group<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The group resource associated with the configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Selected<wbr>Regions</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of regions from which the check will be run. Some regions contain one location, and others contain more than
one. If this field is specified, enough regions to include a minimum of 3 locations must be provided, or an error
message is returned. Not specifying this field will result in uptime checks running from all regions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigtcpcheck">Uptime<wbr>Check<wbr>Config<wbr>Tcp<wbr>Check<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make a TCP check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The maximum amount of time to wait for the request to complete (must be between 1 and 60 seconds). Accepted formats
https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#google.protobuf.Duration
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
            <td class="align-top">Content<wbr>Matchers</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigcontentmatcher">[]Uptime<wbr>Check<wbr>Config<wbr>Content<wbr>Matcher</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The expected content on the page the check is run against. Currently, only the first entry in the list is supported, and
other entries will be ignored. The server will look for an exact match of the string in the page response&#39;s content.
This field is optional and should only be specified if a content match is required.
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
A human-friendly name for the uptime check configuration. The display name should be unique within a Stackdriver
Workspace in order to make it easier to identify; however, uniqueness is not enforced.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheck">*Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make an HTTP or HTTPS check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Monitored<wbr>Resource</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigmonitoredresource">*Uptime<wbr>Check<wbr>Config<wbr>Monitored<wbr>Resource</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitored resource (https://cloud.google.com/monitoring/api/resources) associated with the configuration. The
following monitored resource types are supported for uptime checks: uptime_url gce_instance gae_app aws_ec2_instance
aws_elb_load_balancer
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Period</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often, in seconds, the uptime check is performed. Currently, the only supported values are 60s (1 minute), 300s (5
minutes), 600s (10 minutes), and 900s (15 minutes). Optional, defaults to 300s.
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
            <td class="align-top">Resource<wbr>Group</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigresourcegroup">*Uptime<wbr>Check<wbr>Config<wbr>Resource<wbr>Group</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The group resource associated with the configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Selected<wbr>Regions</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of regions from which the check will be run. Some regions contain one location, and others contain more than
one. If this field is specified, enough regions to include a minimum of 3 locations must be provided, or an error
message is returned. Not specifying this field will result in uptime checks running from all regions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigtcpcheck">*Uptime<wbr>Check<wbr>Config<wbr>Tcp<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make a TCP check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The maximum amount of time to wait for the request to complete (must be between 1 and 60 seconds). Accepted formats
https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#google.protobuf.Duration
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
            <td class="align-top">content<wbr>Matchers</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigcontentmatcher">Uptime<wbr>Check<wbr>Config<wbr>Content<wbr>Matcher[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The expected content on the page the check is run against. Currently, only the first entry in the list is supported, and
other entries will be ignored. The server will look for an exact match of the string in the page response&#39;s content.
This field is optional and should only be specified if a content match is required.
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
A human-friendly name for the uptime check configuration. The display name should be unique within a Stackdriver
Workspace in order to make it easier to identify; however, uniqueness is not enforced.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheck">Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make an HTTP or HTTPS check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">monitored<wbr>Resource</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigmonitoredresource">Uptime<wbr>Check<wbr>Config<wbr>Monitored<wbr>Resource?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitored resource (https://cloud.google.com/monitoring/api/resources) associated with the configuration. The
following monitored resource types are supported for uptime checks: uptime_url gce_instance gae_app aws_ec2_instance
aws_elb_load_balancer
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often, in seconds, the uptime check is performed. Currently, the only supported values are 60s (1 minute), 300s (5
minutes), 600s (10 minutes), and 900s (15 minutes). Optional, defaults to 300s.
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
            <td class="align-top">resource<wbr>Group</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigresourcegroup">Uptime<wbr>Check<wbr>Config<wbr>Resource<wbr>Group?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The group resource associated with the configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">selected<wbr>Regions</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of regions from which the check will be run. Some regions contain one location, and others contain more than
one. If this field is specified, enough regions to include a minimum of 3 locations must be provided, or an error
message is returned. Not specifying this field will result in uptime checks running from all regions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigtcpcheck">Uptime<wbr>Check<wbr>Config<wbr>Tcp<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make a TCP check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The maximum amount of time to wait for the request to complete (must be between 1 and 60 seconds). Accepted formats
https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#google.protobuf.Duration
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
            <td class="align-top">content_<wbr>matchers</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigcontentmatcher">List[Uptime<wbr>Check<wbr>Config<wbr>Content<wbr>Matcher]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The expected content on the page the check is run against. Currently, only the first entry in the list is supported, and
other entries will be ignored. The server will look for an exact match of the string in the page response&#39;s content.
This field is optional and should only be specified if a content match is required.
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
A human-friendly name for the uptime check configuration. The display name should be unique within a Stackdriver
Workspace in order to make it easier to identify; however, uniqueness is not enforced.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheck">Dict[Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make an HTTP or HTTPS check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">monitored_<wbr>resource</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigmonitoredresource">Dict[Uptime<wbr>Check<wbr>Config<wbr>Monitored<wbr>Resource]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitored resource (https://cloud.google.com/monitoring/api/resources) associated with the configuration. The
following monitored resource types are supported for uptime checks: uptime_url gce_instance gae_app aws_ec2_instance
aws_elb_load_balancer
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">period</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often, in seconds, the uptime check is performed. Currently, the only supported values are 60s (1 minute), 300s (5
minutes), 600s (10 minutes), and 900s (15 minutes). Optional, defaults to 300s.
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
            <td class="align-top">resource_<wbr>group</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigresourcegroup">Dict[Uptime<wbr>Check<wbr>Config<wbr>Resource<wbr>Group]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The group resource associated with the configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">selected_<wbr>regions</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of regions from which the check will be run. Some regions contain one location, and others contain more than
one. If this field is specified, enough regions to include a minimum of 3 locations must be provided, or an error
message is returned. Not specifying this field will result in uptime checks running from all regions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigtcpcheck">Dict[Uptime<wbr>Check<wbr>Config<wbr>Tcp<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make a TCP check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The maximum amount of time to wait for the request to complete (must be between 1 and 60 seconds). Accepted formats
https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#google.protobuf.Duration
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## UptimeCheckConfig Output Properties

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
            <td class="align-top">Content<wbr>Matchers</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigcontentmatcher">List&lt;Uptime<wbr>Check<wbr>Config<wbr>Content<wbr>Matcher&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} The expected content on the page the check is run against. Currently, only the first entry in the list is supported, and
other entries will be ignored. The server will look for an exact match of the string in the page response&#39;s content.
This field is optional and should only be specified if a content match is required.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A human-friendly name for the uptime check configuration. The display name should be unique within a Stackdriver
Workspace in order to make it easier to identify; however, uniqueness is not enforced.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheck">Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} Contains information needed to make an HTTP or HTTPS check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Monitored<wbr>Resource</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigmonitoredresource">Uptime<wbr>Check<wbr>Config<wbr>Monitored<wbr>Resource?</a></code>
            </td>
            <td class="align-top">{{% md %}} The monitored resource (https://cloud.google.com/monitoring/api/resources) associated with the configuration. The
following monitored resource types are supported for uptime checks: uptime_url gce_instance gae_app aws_ec2_instance
aws_elb_load_balancer
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A unique resource name for this UptimeCheckConfig. The format is
projects/[PROJECT_ID]/uptimeCheckConfigs/[UPTIME_CHECK_ID].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} How often, in seconds, the uptime check is performed. Currently, the only supported values are 60s (1 minute), 300s (5
minutes), 600s (10 minutes), and 900s (15 minutes). Optional, defaults to 300s.
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
            <td class="align-top">Resource<wbr>Group</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigresourcegroup">Uptime<wbr>Check<wbr>Config<wbr>Resource<wbr>Group?</a></code>
            </td>
            <td class="align-top">{{% md %}} The group resource associated with the configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Selected<wbr>Regions</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} The list of regions from which the check will be run. Some regions contain one location, and others contain more than
one. If this field is specified, enough regions to include a minimum of 3 locations must be provided, or an error
message is returned. Not specifying this field will result in uptime checks running from all regions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigtcpcheck">Uptime<wbr>Check<wbr>Config<wbr>Tcp<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} Contains information needed to make a TCP check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The maximum amount of time to wait for the request to complete (must be between 1 and 60 seconds). Accepted formats
https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#google.protobuf.Duration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Uptime<wbr>Check<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The id of the uptime check
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
            <td class="align-top">Content<wbr>Matchers</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigcontentmatcher">[]Uptime<wbr>Check<wbr>Config<wbr>Content<wbr>Matcher</a></code>
            </td>
            <td class="align-top">{{% md %}} The expected content on the page the check is run against. Currently, only the first entry in the list is supported, and
other entries will be ignored. The server will look for an exact match of the string in the page response&#39;s content.
This field is optional and should only be specified if a content match is required.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A human-friendly name for the uptime check configuration. The display name should be unique within a Stackdriver
Workspace in order to make it easier to identify; however, uniqueness is not enforced.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheck">*Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} Contains information needed to make an HTTP or HTTPS check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Monitored<wbr>Resource</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigmonitoredresource">*Uptime<wbr>Check<wbr>Config<wbr>Monitored<wbr>Resource</a></code>
            </td>
            <td class="align-top">{{% md %}} The monitored resource (https://cloud.google.com/monitoring/api/resources) associated with the configuration. The
following monitored resource types are supported for uptime checks: uptime_url gce_instance gae_app aws_ec2_instance
aws_elb_load_balancer
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A unique resource name for this UptimeCheckConfig. The format is
projects/[PROJECT_ID]/uptimeCheckConfigs/[UPTIME_CHECK_ID].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Period</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} How often, in seconds, the uptime check is performed. Currently, the only supported values are 60s (1 minute), 300s (5
minutes), 600s (10 minutes), and 900s (15 minutes). Optional, defaults to 300s.
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
            <td class="align-top">Resource<wbr>Group</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigresourcegroup">*Uptime<wbr>Check<wbr>Config<wbr>Resource<wbr>Group</a></code>
            </td>
            <td class="align-top">{{% md %}} The group resource associated with the configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Selected<wbr>Regions</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} The list of regions from which the check will be run. Some regions contain one location, and others contain more than
one. If this field is specified, enough regions to include a minimum of 3 locations must be provided, or an error
message is returned. Not specifying this field will result in uptime checks running from all regions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigtcpcheck">*Uptime<wbr>Check<wbr>Config<wbr>Tcp<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} Contains information needed to make a TCP check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The maximum amount of time to wait for the request to complete (must be between 1 and 60 seconds). Accepted formats
https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#google.protobuf.Duration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Uptime<wbr>Check<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The id of the uptime check
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
            <td class="align-top">content<wbr>Matchers</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigcontentmatcher">Uptime<wbr>Check<wbr>Config<wbr>Content<wbr>Matcher[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} The expected content on the page the check is run against. Currently, only the first entry in the list is supported, and
other entries will be ignored. The server will look for an exact match of the string in the page response&#39;s content.
This field is optional and should only be specified if a content match is required.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A human-friendly name for the uptime check configuration. The display name should be unique within a Stackdriver
Workspace in order to make it easier to identify; however, uniqueness is not enforced.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheck">Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} Contains information needed to make an HTTP or HTTPS check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">monitored<wbr>Resource</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigmonitoredresource">Uptime<wbr>Check<wbr>Config<wbr>Monitored<wbr>Resource?</a></code>
            </td>
            <td class="align-top">{{% md %}} The monitored resource (https://cloud.google.com/monitoring/api/resources) associated with the configuration. The
following monitored resource types are supported for uptime checks: uptime_url gce_instance gae_app aws_ec2_instance
aws_elb_load_balancer
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A unique resource name for this UptimeCheckConfig. The format is
projects/[PROJECT_ID]/uptimeCheckConfigs/[UPTIME_CHECK_ID].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} How often, in seconds, the uptime check is performed. Currently, the only supported values are 60s (1 minute), 300s (5
minutes), 600s (10 minutes), and 900s (15 minutes). Optional, defaults to 300s.
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
            <td class="align-top">resource<wbr>Group</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigresourcegroup">Uptime<wbr>Check<wbr>Config<wbr>Resource<wbr>Group?</a></code>
            </td>
            <td class="align-top">{{% md %}} The group resource associated with the configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">selected<wbr>Regions</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} The list of regions from which the check will be run. Some regions contain one location, and others contain more than
one. If this field is specified, enough regions to include a minimum of 3 locations must be provided, or an error
message is returned. Not specifying this field will result in uptime checks running from all regions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigtcpcheck">Uptime<wbr>Check<wbr>Config<wbr>Tcp<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} Contains information needed to make a TCP check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The maximum amount of time to wait for the request to complete (must be between 1 and 60 seconds). Accepted formats
https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#google.protobuf.Duration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">uptime<wbr>Check<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The id of the uptime check
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
            <td class="align-top">content_<wbr>matchers</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigcontentmatcher">List[Uptime<wbr>Check<wbr>Config<wbr>Content<wbr>Matcher]</a></code>
            </td>
            <td class="align-top">{{% md %}} The expected content on the page the check is run against. Currently, only the first entry in the list is supported, and
other entries will be ignored. The server will look for an exact match of the string in the page response&#39;s content.
This field is optional and should only be specified if a content match is required.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A human-friendly name for the uptime check configuration. The display name should be unique within a Stackdriver
Workspace in order to make it easier to identify; however, uniqueness is not enforced.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheck">Dict[Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} Contains information needed to make an HTTP or HTTPS check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">monitored_<wbr>resource</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigmonitoredresource">Dict[Uptime<wbr>Check<wbr>Config<wbr>Monitored<wbr>Resource]</a></code>
            </td>
            <td class="align-top">{{% md %}} The monitored resource (https://cloud.google.com/monitoring/api/resources) associated with the configuration. The
following monitored resource types are supported for uptime checks: uptime_url gce_instance gae_app aws_ec2_instance
aws_elb_load_balancer
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A unique resource name for this UptimeCheckConfig. The format is
projects/[PROJECT_ID]/uptimeCheckConfigs/[UPTIME_CHECK_ID].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">period</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} How often, in seconds, the uptime check is performed. Currently, the only supported values are 60s (1 minute), 300s (5
minutes), 600s (10 minutes), and 900s (15 minutes). Optional, defaults to 300s.
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
            <td class="align-top">resource_<wbr>group</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigresourcegroup">Dict[Uptime<wbr>Check<wbr>Config<wbr>Resource<wbr>Group]</a></code>
            </td>
            <td class="align-top">{{% md %}} The group resource associated with the configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">selected_<wbr>regions</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} The list of regions from which the check will be run. Some regions contain one location, and others contain more than
one. If this field is specified, enough regions to include a minimum of 3 locations must be provided, or an error
message is returned. Not specifying this field will result in uptime checks running from all regions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigtcpcheck">Dict[Uptime<wbr>Check<wbr>Config<wbr>Tcp<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} Contains information needed to make a TCP check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The maximum amount of time to wait for the request to complete (must be between 1 and 60 seconds). Accepted formats
https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#google.protobuf.Duration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">uptime_<wbr>check_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The id of the uptime check
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing UptimeCheckConfig Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/monitoring/#UptimeCheckConfigState">UptimeCheckConfigState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/monitoring/#UptimeCheckConfig">UptimeCheckConfig</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>content_matchers=None<span class="p">, </span>display_name=None<span class="p">, </span>http_check=None<span class="p">, </span>monitored_resource=None<span class="p">, </span>name=None<span class="p">, </span>period=None<span class="p">, </span>project=None<span class="p">, </span>resource_group=None<span class="p">, </span>selected_regions=None<span class="p">, </span>tcp_check=None<span class="p">, </span>timeout=None<span class="p">, </span>uptime_check_id=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetUptimeCheckConfig<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfigState">UptimeCheckConfigState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfig">UptimeCheckConfig</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfig.html">UptimeCheckConfig</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfigState.html">UptimeCheckConfigState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing UptimeCheckConfig resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Content<wbr>Matchers</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigcontentmatcher">List&lt;Uptime<wbr>Check<wbr>Config<wbr>Content<wbr>Matcher<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The expected content on the page the check is run against. Currently, only the first entry in the list is supported, and
other entries will be ignored. The server will look for an exact match of the string in the page response&#39;s content.
This field is optional and should only be specified if a content match is required.
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
A human-friendly name for the uptime check configuration. The display name should be unique within a Stackdriver
Workspace in order to make it easier to identify; however, uniqueness is not enforced.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheck">Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make an HTTP or HTTPS check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Monitored<wbr>Resource</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigmonitoredresource">Uptime<wbr>Check<wbr>Config<wbr>Monitored<wbr>Resource<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitored resource (https://cloud.google.com/monitoring/api/resources) associated with the configuration. The
following monitored resource types are supported for uptime checks: uptime_url gce_instance gae_app aws_ec2_instance
aws_elb_load_balancer
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
A unique resource name for this UptimeCheckConfig. The format is
projects/[PROJECT_ID]/uptimeCheckConfigs/[UPTIME_CHECK_ID].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often, in seconds, the uptime check is performed. Currently, the only supported values are 60s (1 minute), 300s (5
minutes), 600s (10 minutes), and 900s (15 minutes). Optional, defaults to 300s.
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
            <td class="align-top">Resource<wbr>Group</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigresourcegroup">Uptime<wbr>Check<wbr>Config<wbr>Resource<wbr>Group<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The group resource associated with the configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Selected<wbr>Regions</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of regions from which the check will be run. Some regions contain one location, and others contain more than
one. If this field is specified, enough regions to include a minimum of 3 locations must be provided, or an error
message is returned. Not specifying this field will result in uptime checks running from all regions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigtcpcheck">Uptime<wbr>Check<wbr>Config<wbr>Tcp<wbr>Check<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make a TCP check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum amount of time to wait for the request to complete (must be between 1 and 60 seconds). Accepted formats
https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#google.protobuf.Duration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Uptime<wbr>Check<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The id of the uptime check
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
            <td class="align-top">Content<wbr>Matchers</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigcontentmatcher">[]Uptime<wbr>Check<wbr>Config<wbr>Content<wbr>Matcher</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The expected content on the page the check is run against. Currently, only the first entry in the list is supported, and
other entries will be ignored. The server will look for an exact match of the string in the page response&#39;s content.
This field is optional and should only be specified if a content match is required.
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
A human-friendly name for the uptime check configuration. The display name should be unique within a Stackdriver
Workspace in order to make it easier to identify; however, uniqueness is not enforced.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheck">*Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make an HTTP or HTTPS check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Monitored<wbr>Resource</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigmonitoredresource">*Uptime<wbr>Check<wbr>Config<wbr>Monitored<wbr>Resource</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitored resource (https://cloud.google.com/monitoring/api/resources) associated with the configuration. The
following monitored resource types are supported for uptime checks: uptime_url gce_instance gae_app aws_ec2_instance
aws_elb_load_balancer
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
A unique resource name for this UptimeCheckConfig. The format is
projects/[PROJECT_ID]/uptimeCheckConfigs/[UPTIME_CHECK_ID].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Period</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often, in seconds, the uptime check is performed. Currently, the only supported values are 60s (1 minute), 300s (5
minutes), 600s (10 minutes), and 900s (15 minutes). Optional, defaults to 300s.
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
            <td class="align-top">Resource<wbr>Group</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigresourcegroup">*Uptime<wbr>Check<wbr>Config<wbr>Resource<wbr>Group</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The group resource associated with the configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Selected<wbr>Regions</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of regions from which the check will be run. Some regions contain one location, and others contain more than
one. If this field is specified, enough regions to include a minimum of 3 locations must be provided, or an error
message is returned. Not specifying this field will result in uptime checks running from all regions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigtcpcheck">*Uptime<wbr>Check<wbr>Config<wbr>Tcp<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make a TCP check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum amount of time to wait for the request to complete (must be between 1 and 60 seconds). Accepted formats
https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#google.protobuf.Duration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Uptime<wbr>Check<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The id of the uptime check
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
            <td class="align-top">content<wbr>Matchers</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigcontentmatcher">Uptime<wbr>Check<wbr>Config<wbr>Content<wbr>Matcher[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The expected content on the page the check is run against. Currently, only the first entry in the list is supported, and
other entries will be ignored. The server will look for an exact match of the string in the page response&#39;s content.
This field is optional and should only be specified if a content match is required.
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
A human-friendly name for the uptime check configuration. The display name should be unique within a Stackdriver
Workspace in order to make it easier to identify; however, uniqueness is not enforced.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheck">Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make an HTTP or HTTPS check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">monitored<wbr>Resource</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigmonitoredresource">Uptime<wbr>Check<wbr>Config<wbr>Monitored<wbr>Resource?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitored resource (https://cloud.google.com/monitoring/api/resources) associated with the configuration. The
following monitored resource types are supported for uptime checks: uptime_url gce_instance gae_app aws_ec2_instance
aws_elb_load_balancer
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
A unique resource name for this UptimeCheckConfig. The format is
projects/[PROJECT_ID]/uptimeCheckConfigs/[UPTIME_CHECK_ID].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often, in seconds, the uptime check is performed. Currently, the only supported values are 60s (1 minute), 300s (5
minutes), 600s (10 minutes), and 900s (15 minutes). Optional, defaults to 300s.
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
            <td class="align-top">resource<wbr>Group</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigresourcegroup">Uptime<wbr>Check<wbr>Config<wbr>Resource<wbr>Group?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The group resource associated with the configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">selected<wbr>Regions</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of regions from which the check will be run. Some regions contain one location, and others contain more than
one. If this field is specified, enough regions to include a minimum of 3 locations must be provided, or an error
message is returned. Not specifying this field will result in uptime checks running from all regions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigtcpcheck">Uptime<wbr>Check<wbr>Config<wbr>Tcp<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make a TCP check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum amount of time to wait for the request to complete (must be between 1 and 60 seconds). Accepted formats
https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#google.protobuf.Duration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">uptime<wbr>Check<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The id of the uptime check
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
            <td class="align-top">content_<wbr>matchers</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigcontentmatcher">List[Uptime<wbr>Check<wbr>Config<wbr>Content<wbr>Matcher]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The expected content on the page the check is run against. Currently, only the first entry in the list is supported, and
other entries will be ignored. The server will look for an exact match of the string in the page response&#39;s content.
This field is optional and should only be specified if a content match is required.
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
A human-friendly name for the uptime check configuration. The display name should be unique within a Stackdriver
Workspace in order to make it easier to identify; however, uniqueness is not enforced.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheck">Dict[Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make an HTTP or HTTPS check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">monitored_<wbr>resource</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigmonitoredresource">Dict[Uptime<wbr>Check<wbr>Config<wbr>Monitored<wbr>Resource]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitored resource (https://cloud.google.com/monitoring/api/resources) associated with the configuration. The
following monitored resource types are supported for uptime checks: uptime_url gce_instance gae_app aws_ec2_instance
aws_elb_load_balancer
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
A unique resource name for this UptimeCheckConfig. The format is
projects/[PROJECT_ID]/uptimeCheckConfigs/[UPTIME_CHECK_ID].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">period</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often, in seconds, the uptime check is performed. Currently, the only supported values are 60s (1 minute), 300s (5
minutes), 600s (10 minutes), and 900s (15 minutes). Optional, defaults to 300s.
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
            <td class="align-top">resource_<wbr>group</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigresourcegroup">Dict[Uptime<wbr>Check<wbr>Config<wbr>Resource<wbr>Group]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The group resource associated with the configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">selected_<wbr>regions</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of regions from which the check will be run. Some regions contain one location, and others contain more than
one. If this field is specified, enough regions to include a minimum of 3 locations must be provided, or an error
message is returned. Not specifying this field will result in uptime checks running from all regions.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfigtcpcheck">Dict[Uptime<wbr>Check<wbr>Config<wbr>Tcp<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contains information needed to make a TCP check.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum amount of time to wait for the request to complete (must be between 1 and 60 seconds). Accepted formats
https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#google.protobuf.Duration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">uptime_<wbr>check_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The id of the uptime check
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### UptimeCheckConfigContentMatcher
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#UptimeCheckConfigContentMatcher">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#UptimeCheckConfigContentMatcher">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfigContentMatcherArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfigContentMatcherOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfigContentMatcherArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfigContentMatcher.html">output</a> API doc for this type.
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
            <td class="align-top">Content</td>
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
            <td class="align-top">content</td>
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
            <td class="align-top">content</td>
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





#### UptimeCheckConfigHttpCheck
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#UptimeCheckConfigHttpCheck">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#UptimeCheckConfigHttpCheck">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfigHttpCheckArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfigHttpCheckOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfigHttpCheckArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfigHttpCheck.html">output</a> API doc for this type.
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
            <td class="align-top">Auth<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheckauthinfo">Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check<wbr>Auth<wbr>Info<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Headers</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mask<wbr>Headers</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Ssl</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Validate<wbr>Ssl</td>
            <td class="align-top">
                
                <code>bool?</code>
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
            <td class="align-top">Auth<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheckauthinfo">*Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check<wbr>Auth<wbr>Info</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Headers</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mask<wbr>Headers</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Ssl</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Validate<wbr>Ssl</td>
            <td class="align-top">
                
                <code>*bool</code>
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
            <td class="align-top">auth<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheckauthinfo">Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check<wbr>Auth<wbr>Info?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">headers</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mask<wbr>Headers</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">port</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Ssl</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">validate<wbr>Ssl</td>
            <td class="align-top">
                
                <code>boolean?</code>
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
            <td class="align-top">auth<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#uptimecheckconfighttpcheckauthinfo">Dict[Uptime<wbr>Check<wbr>Config<wbr>Http<wbr>Check<wbr>Auth<wbr>Info]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">headers</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mask<wbr>Headers</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">port</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Ssl</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">validate<wbr>Ssl</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### UptimeCheckConfigHttpCheckAuthInfo
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#UptimeCheckConfigHttpCheckAuthInfo">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#UptimeCheckConfigHttpCheckAuthInfo">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfigHttpCheckAuthInfoArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfigHttpCheckAuthInfoOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfigHttpCheckAuthInfoArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfigHttpCheckAuthInfo.html">output</a> API doc for this type.
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
            <td class="align-top">Password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Username</td>
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
            <td class="align-top">Password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Username</td>
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
            <td class="align-top">password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">username</td>
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
            <td class="align-top">password</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">username</td>
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





#### UptimeCheckConfigMonitoredResource
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#UptimeCheckConfigMonitoredResource">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#UptimeCheckConfigMonitoredResource">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfigMonitoredResourceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfigMonitoredResourceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfigMonitoredResourceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfigMonitoredResource.html">output</a> API doc for this type.
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
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### UptimeCheckConfigResourceGroup
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#UptimeCheckConfigResourceGroup">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#UptimeCheckConfigResourceGroup">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfigResourceGroupArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfigResourceGroupOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfigResourceGroupArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfigResourceGroup.html">output</a> API doc for this type.
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
            <td class="align-top">Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Type</td>
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
            <td class="align-top">Group<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Type</td>
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
            <td class="align-top">group<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Type</td>
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
            <td class="align-top">group<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Type</td>
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





#### UptimeCheckConfigTcpCheck
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#UptimeCheckConfigTcpCheck">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#UptimeCheckConfigTcpCheck">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfigTcpCheckArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/monitoring?tab=doc#UptimeCheckConfigTcpCheckOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfigTcpCheckArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Monitoring.UptimeCheckConfigTcpCheck.html">output</a> API doc for this type.
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
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>int</code>
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
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>int</code>
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
            <td class="align-top">port</td>
            <td class="align-top">
                
                <code>number</code>
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
            <td class="align-top">port</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








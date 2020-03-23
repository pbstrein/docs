
---
title: "Job"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a Job Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/cloudscheduler/#Job">Job</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/cloudscheduler/#JobArgs">JobArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Job</span><span class="p">(resource_name, opts=None, </span>app_engine_http_target=None<span class="p">, </span>attempt_deadline=None<span class="p">, </span>description=None<span class="p">, </span>http_target=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>pubsub_target=None<span class="p">, </span>region=None<span class="p">, </span>retry_config=None<span class="p">, </span>schedule=None<span class="p">, </span>time_zone=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewJob<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobArgs">JobArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#Job">Job</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.Job.html">Job</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobArgs.html">JobArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Job resource with the given unique name, arguments, and options.

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
            <td class="align-top">App<wbr>Engine<wbr>Http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptarget">Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
App Engine HTTP target. If the job providers a App Engine HTTP target the cron will send a request to the service
instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Attempt<wbr>Deadline</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The deadline for job attempts. If the request handler does not respond by this deadline then the request is cancelled
and the attempt is marked as a DEADLINE_EXCEEDED failure. The failed attempt can be viewed in execution logs. Cloud
Scheduler will retry the job according to the RetryConfig. The allowed duration for this deadline is: * For HTTP
targets, between 15 seconds and 30 minutes. * For App Engine HTTP targets, between 15 seconds and 24 hours. A duration
in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example: &#34;3.5s&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable description for the job. This string must not contain more than 500 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobhttptarget">Job<wbr>Http<wbr>Target<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
HTTP target. If the job providers a http_target the cron will send a request to the targeted url
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
The name of the job.
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
            <td class="align-top">Pubsub<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobpubsubtarget">Job<wbr>Pubsub<wbr>Target<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Pub/Sub target If the job providers a Pub/Sub target the cron will publish a message to the provided topic
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
Region where the scheduler job resides
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retry<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#jobretryconfig">Job<wbr>Retry<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
By default, if a job does not complete successfully, meaning that an acknowledgement is not received from the handler,
then it will be retried with exponential backoff according to the settings
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the schedule on which the job will be executed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone to be used in interpreting schedule. The value of this field must be a time zone name from the
tz database.
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
            <td class="align-top">App<wbr>Engine<wbr>Http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptarget">*Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
App Engine HTTP target. If the job providers a App Engine HTTP target the cron will send a request to the service
instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Attempt<wbr>Deadline</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The deadline for job attempts. If the request handler does not respond by this deadline then the request is cancelled
and the attempt is marked as a DEADLINE_EXCEEDED failure. The failed attempt can be viewed in execution logs. Cloud
Scheduler will retry the job according to the RetryConfig. The allowed duration for this deadline is: * For HTTP
targets, between 15 seconds and 30 minutes. * For App Engine HTTP targets, between 15 seconds and 24 hours. A duration
in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example: &#34;3.5s&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable description for the job. This string must not contain more than 500 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobhttptarget">*Job<wbr>Http<wbr>Target</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
HTTP target. If the job providers a http_target the cron will send a request to the targeted url
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
The name of the job.
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
            <td class="align-top">Pubsub<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobpubsubtarget">*Job<wbr>Pubsub<wbr>Target</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Pub/Sub target If the job providers a Pub/Sub target the cron will publish a message to the provided topic
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
Region where the scheduler job resides
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retry<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#jobretryconfig">*Job<wbr>Retry<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
By default, if a job does not complete successfully, meaning that an acknowledgement is not received from the handler,
then it will be retried with exponential backoff according to the settings
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the schedule on which the job will be executed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Zone</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone to be used in interpreting schedule. The value of this field must be a time zone name from the
tz database.
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
            <td class="align-top">app<wbr>Engine<wbr>Http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptarget">Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
App Engine HTTP target. If the job providers a App Engine HTTP target the cron will send a request to the service
instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">attempt<wbr>Deadline</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The deadline for job attempts. If the request handler does not respond by this deadline then the request is cancelled
and the attempt is marked as a DEADLINE_EXCEEDED failure. The failed attempt can be viewed in execution logs. Cloud
Scheduler will retry the job according to the RetryConfig. The allowed duration for this deadline is: * For HTTP
targets, between 15 seconds and 30 minutes. * For App Engine HTTP targets, between 15 seconds and 24 hours. A duration
in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example: &#34;3.5s&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable description for the job. This string must not contain more than 500 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobhttptarget">Job<wbr>Http<wbr>Target?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
HTTP target. If the job providers a http_target the cron will send a request to the targeted url
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
The name of the job.
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
            <td class="align-top">pubsub<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobpubsubtarget">Job<wbr>Pubsub<wbr>Target?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Pub/Sub target If the job providers a Pub/Sub target the cron will publish a message to the provided topic
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
Region where the scheduler job resides
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retry<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#jobretryconfig">Job<wbr>Retry<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
By default, if a job does not complete successfully, meaning that an acknowledgement is not received from the handler,
then it will be retried with exponential backoff according to the settings
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the schedule on which the job will be executed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time<wbr>Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone to be used in interpreting schedule. The value of this field must be a time zone name from the
tz database.
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
            <td class="align-top">app_<wbr>engine_<wbr>http_<wbr>target</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptarget">Dict[Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
App Engine HTTP target. If the job providers a App Engine HTTP target the cron will send a request to the service
instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">attempt_<wbr>deadline</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The deadline for job attempts. If the request handler does not respond by this deadline then the request is cancelled
and the attempt is marked as a DEADLINE_EXCEEDED failure. The failed attempt can be viewed in execution logs. Cloud
Scheduler will retry the job according to the RetryConfig. The allowed duration for this deadline is: * For HTTP
targets, between 15 seconds and 30 minutes. * For App Engine HTTP targets, between 15 seconds and 24 hours. A duration
in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example: &#34;3.5s&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable description for the job. This string must not contain more than 500 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http_<wbr>target</td>
            <td class="align-top">
                
                <code><a href="#jobhttptarget">Dict[Job<wbr>Http<wbr>Target]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
HTTP target. If the job providers a http_target the cron will send a request to the targeted url
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
The name of the job.
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
            <td class="align-top">pubsub_<wbr>target</td>
            <td class="align-top">
                
                <code><a href="#jobpubsubtarget">Dict[Job<wbr>Pubsub<wbr>Target]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Pub/Sub target If the job providers a Pub/Sub target the cron will publish a message to the provided topic
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
Region where the scheduler job resides
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retry_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#jobretryconfig">Dict[Job<wbr>Retry<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
By default, if a job does not complete successfully, meaning that an acknowledgement is not received from the handler,
then it will be retried with exponential backoff according to the settings
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the schedule on which the job will be executed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time_<wbr>zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone to be used in interpreting schedule. The value of this field must be a time zone name from the
tz database.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Job Output Properties

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
            <td class="align-top">App<wbr>Engine<wbr>Http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptarget">Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target?</a></code>
            </td>
            <td class="align-top">{{% md %}} App Engine HTTP target. If the job providers a App Engine HTTP target the cron will send a request to the service
instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Attempt<wbr>Deadline</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The deadline for job attempts. If the request handler does not respond by this deadline then the request is cancelled
and the attempt is marked as a DEADLINE_EXCEEDED failure. The failed attempt can be viewed in execution logs. Cloud
Scheduler will retry the job according to the RetryConfig. The allowed duration for this deadline is: * For HTTP
targets, between 15 seconds and 30 minutes. * For App Engine HTTP targets, between 15 seconds and 24 hours. A duration
in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example: &#34;3.5s&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable description for the job. This string must not contain more than 500 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobhttptarget">Job<wbr>Http<wbr>Target?</a></code>
            </td>
            <td class="align-top">{{% md %}} HTTP target. If the job providers a http_target the cron will send a request to the targeted url
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the job.
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
            <td class="align-top">Pubsub<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobpubsubtarget">Job<wbr>Pubsub<wbr>Target?</a></code>
            </td>
            <td class="align-top">{{% md %}} Pub/Sub target If the job providers a Pub/Sub target the cron will publish a message to the provided topic
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Region where the scheduler job resides
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retry<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#jobretryconfig">Job<wbr>Retry<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} By default, if a job does not complete successfully, meaning that an acknowledgement is not received from the handler,
then it will be retried with exponential backoff according to the settings
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Describes the schedule on which the job will be executed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the time zone to be used in interpreting schedule. The value of this field must be a time zone name from the
tz database.
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
            <td class="align-top">App<wbr>Engine<wbr>Http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptarget">*Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target</a></code>
            </td>
            <td class="align-top">{{% md %}} App Engine HTTP target. If the job providers a App Engine HTTP target the cron will send a request to the service
instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Attempt<wbr>Deadline</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The deadline for job attempts. If the request handler does not respond by this deadline then the request is cancelled
and the attempt is marked as a DEADLINE_EXCEEDED failure. The failed attempt can be viewed in execution logs. Cloud
Scheduler will retry the job according to the RetryConfig. The allowed duration for this deadline is: * For HTTP
targets, between 15 seconds and 30 minutes. * For App Engine HTTP targets, between 15 seconds and 24 hours. A duration
in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example: &#34;3.5s&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable description for the job. This string must not contain more than 500 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobhttptarget">*Job<wbr>Http<wbr>Target</a></code>
            </td>
            <td class="align-top">{{% md %}} HTTP target. If the job providers a http_target the cron will send a request to the targeted url
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the job.
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
            <td class="align-top">Pubsub<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobpubsubtarget">*Job<wbr>Pubsub<wbr>Target</a></code>
            </td>
            <td class="align-top">{{% md %}} Pub/Sub target If the job providers a Pub/Sub target the cron will publish a message to the provided topic
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Region where the scheduler job resides
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retry<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#jobretryconfig">*Job<wbr>Retry<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} By default, if a job does not complete successfully, meaning that an acknowledgement is not received from the handler,
then it will be retried with exponential backoff according to the settings
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Describes the schedule on which the job will be executed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Zone</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the time zone to be used in interpreting schedule. The value of this field must be a time zone name from the
tz database.
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
            <td class="align-top">app<wbr>Engine<wbr>Http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptarget">Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target?</a></code>
            </td>
            <td class="align-top">{{% md %}} App Engine HTTP target. If the job providers a App Engine HTTP target the cron will send a request to the service
instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">attempt<wbr>Deadline</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The deadline for job attempts. If the request handler does not respond by this deadline then the request is cancelled
and the attempt is marked as a DEADLINE_EXCEEDED failure. The failed attempt can be viewed in execution logs. Cloud
Scheduler will retry the job according to the RetryConfig. The allowed duration for this deadline is: * For HTTP
targets, between 15 seconds and 30 minutes. * For App Engine HTTP targets, between 15 seconds and 24 hours. A duration
in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example: &#34;3.5s&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable description for the job. This string must not contain more than 500 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobhttptarget">Job<wbr>Http<wbr>Target?</a></code>
            </td>
            <td class="align-top">{{% md %}} HTTP target. If the job providers a http_target the cron will send a request to the targeted url
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the job.
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
            <td class="align-top">pubsub<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobpubsubtarget">Job<wbr>Pubsub<wbr>Target?</a></code>
            </td>
            <td class="align-top">{{% md %}} Pub/Sub target If the job providers a Pub/Sub target the cron will publish a message to the provided topic
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Region where the scheduler job resides
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retry<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#jobretryconfig">Job<wbr>Retry<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} By default, if a job does not complete successfully, meaning that an acknowledgement is not received from the handler,
then it will be retried with exponential backoff according to the settings
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Describes the schedule on which the job will be executed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time<wbr>Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the time zone to be used in interpreting schedule. The value of this field must be a time zone name from the
tz database.
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
            <td class="align-top">app_<wbr>engine_<wbr>http_<wbr>target</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptarget">Dict[Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target]</a></code>
            </td>
            <td class="align-top">{{% md %}} App Engine HTTP target. If the job providers a App Engine HTTP target the cron will send a request to the service
instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">attempt_<wbr>deadline</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The deadline for job attempts. If the request handler does not respond by this deadline then the request is cancelled
and the attempt is marked as a DEADLINE_EXCEEDED failure. The failed attempt can be viewed in execution logs. Cloud
Scheduler will retry the job according to the RetryConfig. The allowed duration for this deadline is: * For HTTP
targets, between 15 seconds and 30 minutes. * For App Engine HTTP targets, between 15 seconds and 24 hours. A duration
in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example: &#34;3.5s&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable description for the job. This string must not contain more than 500 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http_<wbr>target</td>
            <td class="align-top">
                
                <code><a href="#jobhttptarget">Dict[Job<wbr>Http<wbr>Target]</a></code>
            </td>
            <td class="align-top">{{% md %}} HTTP target. If the job providers a http_target the cron will send a request to the targeted url
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the job.
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
            <td class="align-top">pubsub_<wbr>target</td>
            <td class="align-top">
                
                <code><a href="#jobpubsubtarget">Dict[Job<wbr>Pubsub<wbr>Target]</a></code>
            </td>
            <td class="align-top">{{% md %}} Pub/Sub target If the job providers a Pub/Sub target the cron will publish a message to the provided topic
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Region where the scheduler job resides
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retry_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#jobretryconfig">Dict[Job<wbr>Retry<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} By default, if a job does not complete successfully, meaning that an acknowledgement is not received from the handler,
then it will be retried with exponential backoff according to the settings
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Describes the schedule on which the job will be executed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time_<wbr>zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the time zone to be used in interpreting schedule. The value of this field must be a time zone name from the
tz database.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Job Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/cloudscheduler/#JobState">JobState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/cloudscheduler/#Job">Job</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>app_engine_http_target=None<span class="p">, </span>attempt_deadline=None<span class="p">, </span>description=None<span class="p">, </span>http_target=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>pubsub_target=None<span class="p">, </span>region=None<span class="p">, </span>retry_config=None<span class="p">, </span>schedule=None<span class="p">, </span>time_zone=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetJob<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobState">JobState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#Job">Job</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.Job.html">Job</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobState.html">JobState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Job resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">App<wbr>Engine<wbr>Http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptarget">Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
App Engine HTTP target. If the job providers a App Engine HTTP target the cron will send a request to the service
instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Attempt<wbr>Deadline</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The deadline for job attempts. If the request handler does not respond by this deadline then the request is cancelled
and the attempt is marked as a DEADLINE_EXCEEDED failure. The failed attempt can be viewed in execution logs. Cloud
Scheduler will retry the job according to the RetryConfig. The allowed duration for this deadline is: * For HTTP
targets, between 15 seconds and 30 minutes. * For App Engine HTTP targets, between 15 seconds and 24 hours. A duration
in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example: &#34;3.5s&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable description for the job. This string must not contain more than 500 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobhttptarget">Job<wbr>Http<wbr>Target<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
HTTP target. If the job providers a http_target the cron will send a request to the targeted url
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
The name of the job.
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
            <td class="align-top">Pubsub<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobpubsubtarget">Job<wbr>Pubsub<wbr>Target<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Pub/Sub target If the job providers a Pub/Sub target the cron will publish a message to the provided topic
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
Region where the scheduler job resides
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retry<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#jobretryconfig">Job<wbr>Retry<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
By default, if a job does not complete successfully, meaning that an acknowledgement is not received from the handler,
then it will be retried with exponential backoff according to the settings
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the schedule on which the job will be executed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone to be used in interpreting schedule. The value of this field must be a time zone name from the
tz database.
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
            <td class="align-top">App<wbr>Engine<wbr>Http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptarget">*Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
App Engine HTTP target. If the job providers a App Engine HTTP target the cron will send a request to the service
instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Attempt<wbr>Deadline</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The deadline for job attempts. If the request handler does not respond by this deadline then the request is cancelled
and the attempt is marked as a DEADLINE_EXCEEDED failure. The failed attempt can be viewed in execution logs. Cloud
Scheduler will retry the job according to the RetryConfig. The allowed duration for this deadline is: * For HTTP
targets, between 15 seconds and 30 minutes. * For App Engine HTTP targets, between 15 seconds and 24 hours. A duration
in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example: &#34;3.5s&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable description for the job. This string must not contain more than 500 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobhttptarget">*Job<wbr>Http<wbr>Target</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
HTTP target. If the job providers a http_target the cron will send a request to the targeted url
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
The name of the job.
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
            <td class="align-top">Pubsub<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobpubsubtarget">*Job<wbr>Pubsub<wbr>Target</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Pub/Sub target If the job providers a Pub/Sub target the cron will publish a message to the provided topic
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
Region where the scheduler job resides
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retry<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#jobretryconfig">*Job<wbr>Retry<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
By default, if a job does not complete successfully, meaning that an acknowledgement is not received from the handler,
then it will be retried with exponential backoff according to the settings
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the schedule on which the job will be executed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Zone</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone to be used in interpreting schedule. The value of this field must be a time zone name from the
tz database.
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
            <td class="align-top">app<wbr>Engine<wbr>Http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptarget">Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
App Engine HTTP target. If the job providers a App Engine HTTP target the cron will send a request to the service
instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">attempt<wbr>Deadline</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The deadline for job attempts. If the request handler does not respond by this deadline then the request is cancelled
and the attempt is marked as a DEADLINE_EXCEEDED failure. The failed attempt can be viewed in execution logs. Cloud
Scheduler will retry the job according to the RetryConfig. The allowed duration for this deadline is: * For HTTP
targets, between 15 seconds and 30 minutes. * For App Engine HTTP targets, between 15 seconds and 24 hours. A duration
in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example: &#34;3.5s&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable description for the job. This string must not contain more than 500 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobhttptarget">Job<wbr>Http<wbr>Target?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
HTTP target. If the job providers a http_target the cron will send a request to the targeted url
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
The name of the job.
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
            <td class="align-top">pubsub<wbr>Target</td>
            <td class="align-top">
                
                <code><a href="#jobpubsubtarget">Job<wbr>Pubsub<wbr>Target?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Pub/Sub target If the job providers a Pub/Sub target the cron will publish a message to the provided topic
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
Region where the scheduler job resides
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retry<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#jobretryconfig">Job<wbr>Retry<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
By default, if a job does not complete successfully, meaning that an acknowledgement is not received from the handler,
then it will be retried with exponential backoff according to the settings
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the schedule on which the job will be executed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time<wbr>Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone to be used in interpreting schedule. The value of this field must be a time zone name from the
tz database.
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
            <td class="align-top">app_<wbr>engine_<wbr>http_<wbr>target</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptarget">Dict[Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
App Engine HTTP target. If the job providers a App Engine HTTP target the cron will send a request to the service
instance
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">attempt_<wbr>deadline</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The deadline for job attempts. If the request handler does not respond by this deadline then the request is cancelled
and the attempt is marked as a DEADLINE_EXCEEDED failure. The failed attempt can be viewed in execution logs. Cloud
Scheduler will retry the job according to the RetryConfig. The allowed duration for this deadline is: * For HTTP
targets, between 15 seconds and 30 minutes. * For App Engine HTTP targets, between 15 seconds and 24 hours. A duration
in seconds with up to nine fractional digits, terminated by &#39;s&#39;. Example: &#34;3.5s&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable description for the job. This string must not contain more than 500 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http_<wbr>target</td>
            <td class="align-top">
                
                <code><a href="#jobhttptarget">Dict[Job<wbr>Http<wbr>Target]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
HTTP target. If the job providers a http_target the cron will send a request to the targeted url
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
The name of the job.
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
            <td class="align-top">pubsub_<wbr>target</td>
            <td class="align-top">
                
                <code><a href="#jobpubsubtarget">Dict[Job<wbr>Pubsub<wbr>Target]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Pub/Sub target If the job providers a Pub/Sub target the cron will publish a message to the provided topic
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
Region where the scheduler job resides
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retry_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#jobretryconfig">Dict[Job<wbr>Retry<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
By default, if a job does not complete successfully, meaning that an acknowledgement is not received from the handler,
then it will be retried with exponential backoff according to the settings
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the schedule on which the job will be executed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time_<wbr>zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone to be used in interpreting schedule. The value of this field must be a time zone name from the
tz database.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### JobAppEngineHttpTarget
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#JobAppEngineHttpTarget">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#JobAppEngineHttpTarget">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobAppEngineHttpTargetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobAppEngineHttpTargetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobAppEngineHttpTargetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobAppEngineHttpTarget.html">output</a> API doc for this type.
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
            <td class="align-top">App<wbr>Engine<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptargetappenginerouting">Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target<wbr>App<wbr>Engine<wbr>Routing<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Body</td>
            <td class="align-top">
                
                <code>string?</code>
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
            <td class="align-top">Http<wbr>Method</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Relative<wbr>Uri</td>
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
            <td class="align-top">App<wbr>Engine<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptargetappenginerouting">*Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target<wbr>App<wbr>Engine<wbr>Routing</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Body</td>
            <td class="align-top">
                
                <code>*string</code>
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
            <td class="align-top">Http<wbr>Method</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Relative<wbr>Uri</td>
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
            <td class="align-top">app<wbr>Engine<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptargetappenginerouting">Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target<wbr>App<wbr>Engine<wbr>Routing?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">body</td>
            <td class="align-top">
                
                <code>string?</code>
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
            <td class="align-top">http<wbr>Method</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">relative<wbr>Uri</td>
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
            <td class="align-top">app<wbr>Engine<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#jobappenginehttptargetappenginerouting">Dict[Job<wbr>App<wbr>Engine<wbr>Http<wbr>Target<wbr>App<wbr>Engine<wbr>Routing]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">body</td>
            <td class="align-top">
                
                <code>str</code>
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
            <td class="align-top">http<wbr>Method</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">relative<wbr>Uri</td>
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





#### JobAppEngineHttpTargetAppEngineRouting
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#JobAppEngineHttpTargetAppEngineRouting">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#JobAppEngineHttpTargetAppEngineRouting">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobAppEngineHttpTargetAppEngineRoutingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobAppEngineHttpTargetAppEngineRoutingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobAppEngineHttpTargetAppEngineRoutingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobAppEngineHttpTargetAppEngineRouting.html">output</a> API doc for this type.
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
            <td class="align-top">Instance</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Instance</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">instance</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">instance</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### JobHttpTarget
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#JobHttpTarget">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#JobHttpTarget">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobHttpTargetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobHttpTargetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobHttpTargetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobHttpTarget.html">output</a> API doc for this type.
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
            <td class="align-top">Body</td>
            <td class="align-top">
                
                <code>string?</code>
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
            <td class="align-top">Http<wbr>Method</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth<wbr>Token</td>
            <td class="align-top">
                
                <code><a href="#jobhttptargetoauthtoken">Job<wbr>Http<wbr>Target<wbr>Oauth<wbr>Token<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oidc<wbr>Token</td>
            <td class="align-top">
                
                <code><a href="#jobhttptargetoidctoken">Job<wbr>Http<wbr>Target<wbr>Oidc<wbr>Token<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Uri</td>
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
            <td class="align-top">Body</td>
            <td class="align-top">
                
                <code>*string</code>
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
            <td class="align-top">Http<wbr>Method</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth<wbr>Token</td>
            <td class="align-top">
                
                <code><a href="#jobhttptargetoauthtoken">*Job<wbr>Http<wbr>Target<wbr>Oauth<wbr>Token</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oidc<wbr>Token</td>
            <td class="align-top">
                
                <code><a href="#jobhttptargetoidctoken">*Job<wbr>Http<wbr>Target<wbr>Oidc<wbr>Token</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Uri</td>
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
            <td class="align-top">body</td>
            <td class="align-top">
                
                <code>string?</code>
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
            <td class="align-top">http<wbr>Method</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth<wbr>Token</td>
            <td class="align-top">
                
                <code><a href="#jobhttptargetoauthtoken">Job<wbr>Http<wbr>Target<wbr>Oauth<wbr>Token?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oidc<wbr>Token</td>
            <td class="align-top">
                
                <code><a href="#jobhttptargetoidctoken">Job<wbr>Http<wbr>Target<wbr>Oidc<wbr>Token?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">uri</td>
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
            <td class="align-top">body</td>
            <td class="align-top">
                
                <code>str</code>
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
            <td class="align-top">http<wbr>Method</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth<wbr>Token</td>
            <td class="align-top">
                
                <code><a href="#jobhttptargetoauthtoken">Dict[Job<wbr>Http<wbr>Target<wbr>Oauth<wbr>Token]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oidc<wbr>Token</td>
            <td class="align-top">
                
                <code><a href="#jobhttptargetoidctoken">Dict[Job<wbr>Http<wbr>Target<wbr>Oidc<wbr>Token]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">uri</td>
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





#### JobHttpTargetOauthToken
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#JobHttpTargetOauthToken">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#JobHttpTargetOauthToken">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobHttpTargetOauthTokenArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobHttpTargetOauthTokenOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobHttpTargetOauthTokenArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobHttpTargetOauthToken.html">output</a> API doc for this type.
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
            <td class="align-top">Scope</td>
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
            <td class="align-top">Scope</td>
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
            <td class="align-top">scope</td>
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
            <td class="align-top">scope</td>
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





#### JobHttpTargetOidcToken
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#JobHttpTargetOidcToken">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#JobHttpTargetOidcToken">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobHttpTargetOidcTokenArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobHttpTargetOidcTokenOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobHttpTargetOidcTokenArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobHttpTargetOidcToken.html">output</a> API doc for this type.
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





#### JobPubsubTarget
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#JobPubsubTarget">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#JobPubsubTarget">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobPubsubTargetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobPubsubTargetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobPubsubTargetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobPubsubTarget.html">output</a> API doc for this type.
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
            <td class="align-top">Data</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Topic<wbr>Name</td>
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
            <td class="align-top">Data</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Topic<wbr>Name</td>
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
            <td class="align-top">data</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">topic<wbr>Name</td>
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
            <td class="align-top">data</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">topic<wbr>Name</td>
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





#### JobRetryConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#JobRetryConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#JobRetryConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobRetryConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudscheduler?tab=doc#JobRetryConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobRetryConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudscheduler.JobRetryConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Max<wbr>Backoff<wbr>Duration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Doublings</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Retry<wbr>Duration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Backoff<wbr>Duration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retry<wbr>Count</td>
            <td class="align-top">
                
                <code>int?</code>
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
            <td class="align-top">Max<wbr>Backoff<wbr>Duration</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Doublings</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Retry<wbr>Duration</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Backoff<wbr>Duration</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Retry<wbr>Count</td>
            <td class="align-top">
                
                <code>*int</code>
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
            <td class="align-top">max<wbr>Backoff<wbr>Duration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Doublings</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Retry<wbr>Duration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Backoff<wbr>Duration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retry<wbr>Count</td>
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
            <td class="align-top">max<wbr>Backoff<wbr>Duration</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Doublings</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Retry<wbr>Duration</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Backoff<wbr>Duration</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">retry<wbr>Count</td>
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








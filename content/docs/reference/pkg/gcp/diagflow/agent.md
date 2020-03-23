
---
title: "Agent"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a Agent Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/diagflow/#Agent">Agent</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/diagflow/#AgentArgs">AgentArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Agent</span><span class="p">(resource_name, opts=None, </span>api_version=None<span class="p">, </span>avatar_uri=None<span class="p">, </span>classification_threshold=None<span class="p">, </span>default_language_code=None<span class="p">, </span>description=None<span class="p">, </span>display_name=None<span class="p">, </span>enable_logging=None<span class="p">, </span>match_mode=None<span class="p">, </span>project=None<span class="p">, </span>supported_language_codes=None<span class="p">, </span>tier=None<span class="p">, </span>time_zone=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewAgent<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/diagflow?tab=doc#AgentArgs">AgentArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/diagflow?tab=doc#Agent">Agent</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Diagflow.Agent.html">Agent</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Diagflow.AgentArgs.html">AgentArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Agent resource with the given unique name, arguments, and options.

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
            <td class="align-top">Api<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
API version displayed in Dialogflow console. If not specified, V2 API is assumed. Clients are free to query different
service endpoints for different API versions. However, bots connectors and webhook calls will follow the specified API
version. * API_VERSION_V1: Legacy V1 API. * API_VERSION_V2: V2 API. * API_VERSION_V2_BETA_1: V2beta1 API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Avatar<wbr>Uri</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the agent&#39;s avatar, which are used throughout the Dialogflow console. When an image URL is entered into this
field, the Dialogflow will save the image in the backend. The address of the backend image returned from the API will be
shown in the [avatarUriBackend] field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Classification<wbr>Threshold</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
To filter out false positive results and still get variety in matched natural language inputs for your agent, you can
tune the machine learning classification threshold. If the returned score value is less than the threshold value, then a
fallback intent will be triggered or, if there are no fallback intents defined, no intent will be triggered. The score
values range from 0.0 (completely uncertain) to 1.0 (completely certain). If set to 0.0, the default of 0.3 is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Language<wbr>Code</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The default language of the agent as a language tag. [See Language
Support](https://cloud.google.com/dialogflow/docs/reference/language) for a list of the currently supported language
codes. This field cannot be updated after creation.
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
The description of this agent. The maximum length is 500 characters. If exceeded, the request is rejected.
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
The name of this agent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Logging</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines whether this agent should log conversation queries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Match<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines how intents are detected from user queries. * MATCH_MODE_HYBRID: Best for agents with a small number of
examples in intents and/or wide use of templates syntax and composite entities. * MATCH_MODE_ML_ONLY: Can be used for
agents with a large number of examples in intents, especially the ones using @sys.any or very large developer entities.
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
            <td class="align-top">Supported<wbr>Language<wbr>Codes</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of all languages supported by this agent (except for the defaultLanguageCode).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tier</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The agent tier. If not specified, TIER_STANDARD is assumed. * TIER_STANDARD: Standard tier. * TIER_ENTERPRISE:
Enterprise tier (Essentials). * TIER_ENTERPRISE_PLUS: Enterprise tier (Plus). NOTE: This field seems to have eventual
consistency in the API. Updating this field to a new value, or even creating a new agent with a tier that is different
from a previous agent in the same project will take some time to propagate. The provider will wait for the API to show
consistency, which can lead to longer apply times.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Zone</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The time zone of this agent from the [time zone database](https://www.iana.org/time-zones), e.g., America/New_York,
Europe/Paris.
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
            <td class="align-top">Api<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
API version displayed in Dialogflow console. If not specified, V2 API is assumed. Clients are free to query different
service endpoints for different API versions. However, bots connectors and webhook calls will follow the specified API
version. * API_VERSION_V1: Legacy V1 API. * API_VERSION_V2: V2 API. * API_VERSION_V2_BETA_1: V2beta1 API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Avatar<wbr>Uri</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the agent&#39;s avatar, which are used throughout the Dialogflow console. When an image URL is entered into this
field, the Dialogflow will save the image in the backend. The address of the backend image returned from the API will be
shown in the [avatarUriBackend] field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Classification<wbr>Threshold</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
To filter out false positive results and still get variety in matched natural language inputs for your agent, you can
tune the machine learning classification threshold. If the returned score value is less than the threshold value, then a
fallback intent will be triggered or, if there are no fallback intents defined, no intent will be triggered. The score
values range from 0.0 (completely uncertain) to 1.0 (completely certain). If set to 0.0, the default of 0.3 is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Language<wbr>Code</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The default language of the agent as a language tag. [See Language
Support](https://cloud.google.com/dialogflow/docs/reference/language) for a list of the currently supported language
codes. This field cannot be updated after creation.
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
The description of this agent. The maximum length is 500 characters. If exceeded, the request is rejected.
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
The name of this agent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Logging</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines whether this agent should log conversation queries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Match<wbr>Mode</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines how intents are detected from user queries. * MATCH_MODE_HYBRID: Best for agents with a small number of
examples in intents and/or wide use of templates syntax and composite entities. * MATCH_MODE_ML_ONLY: Can be used for
agents with a large number of examples in intents, especially the ones using @sys.any or very large developer entities.
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
            <td class="align-top">Supported<wbr>Language<wbr>Codes</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of all languages supported by this agent (except for the defaultLanguageCode).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tier</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The agent tier. If not specified, TIER_STANDARD is assumed. * TIER_STANDARD: Standard tier. * TIER_ENTERPRISE:
Enterprise tier (Essentials). * TIER_ENTERPRISE_PLUS: Enterprise tier (Plus). NOTE: This field seems to have eventual
consistency in the API. Updating this field to a new value, or even creating a new agent with a tier that is different
from a previous agent in the same project will take some time to propagate. The provider will wait for the API to show
consistency, which can lead to longer apply times.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Zone</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The time zone of this agent from the [time zone database](https://www.iana.org/time-zones), e.g., America/New_York,
Europe/Paris.
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
            <td class="align-top">api<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
API version displayed in Dialogflow console. If not specified, V2 API is assumed. Clients are free to query different
service endpoints for different API versions. However, bots connectors and webhook calls will follow the specified API
version. * API_VERSION_V1: Legacy V1 API. * API_VERSION_V2: V2 API. * API_VERSION_V2_BETA_1: V2beta1 API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">avatar<wbr>Uri</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the agent&#39;s avatar, which are used throughout the Dialogflow console. When an image URL is entered into this
field, the Dialogflow will save the image in the backend. The address of the backend image returned from the API will be
shown in the [avatarUriBackend] field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">classification<wbr>Threshold</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
To filter out false positive results and still get variety in matched natural language inputs for your agent, you can
tune the machine learning classification threshold. If the returned score value is less than the threshold value, then a
fallback intent will be triggered or, if there are no fallback intents defined, no intent will be triggered. The score
values range from 0.0 (completely uncertain) to 1.0 (completely certain). If set to 0.0, the default of 0.3 is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Language<wbr>Code</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The default language of the agent as a language tag. [See Language
Support](https://cloud.google.com/dialogflow/docs/reference/language) for a list of the currently supported language
codes. This field cannot be updated after creation.
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
The description of this agent. The maximum length is 500 characters. If exceeded, the request is rejected.
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
The name of this agent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Logging</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines whether this agent should log conversation queries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">match<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines how intents are detected from user queries. * MATCH_MODE_HYBRID: Best for agents with a small number of
examples in intents and/or wide use of templates syntax and composite entities. * MATCH_MODE_ML_ONLY: Can be used for
agents with a large number of examples in intents, especially the ones using @sys.any or very large developer entities.
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
            <td class="align-top">supported<wbr>Language<wbr>Codes</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of all languages supported by this agent (except for the defaultLanguageCode).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tier</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The agent tier. If not specified, TIER_STANDARD is assumed. * TIER_STANDARD: Standard tier. * TIER_ENTERPRISE:
Enterprise tier (Essentials). * TIER_ENTERPRISE_PLUS: Enterprise tier (Plus). NOTE: This field seems to have eventual
consistency in the API. Updating this field to a new value, or even creating a new agent with a tier that is different
from a previous agent in the same project will take some time to propagate. The provider will wait for the API to show
consistency, which can lead to longer apply times.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time<wbr>Zone</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The time zone of this agent from the [time zone database](https://www.iana.org/time-zones), e.g., America/New_York,
Europe/Paris.
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
            <td class="align-top">api_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
API version displayed in Dialogflow console. If not specified, V2 API is assumed. Clients are free to query different
service endpoints for different API versions. However, bots connectors and webhook calls will follow the specified API
version. * API_VERSION_V1: Legacy V1 API. * API_VERSION_V2: V2 API. * API_VERSION_V2_BETA_1: V2beta1 API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">avatar_<wbr>uri</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the agent&#39;s avatar, which are used throughout the Dialogflow console. When an image URL is entered into this
field, the Dialogflow will save the image in the backend. The address of the backend image returned from the API will be
shown in the [avatarUriBackend] field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">classification_<wbr>threshold</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
To filter out false positive results and still get variety in matched natural language inputs for your agent, you can
tune the machine learning classification threshold. If the returned score value is less than the threshold value, then a
fallback intent will be triggered or, if there are no fallback intents defined, no intent will be triggered. The score
values range from 0.0 (completely uncertain) to 1.0 (completely certain). If set to 0.0, the default of 0.3 is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>language_<wbr>code</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The default language of the agent as a language tag. [See Language
Support](https://cloud.google.com/dialogflow/docs/reference/language) for a list of the currently supported language
codes. This field cannot be updated after creation.
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
The description of this agent. The maximum length is 500 characters. If exceeded, the request is rejected.
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
The name of this agent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>logging</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines whether this agent should log conversation queries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">match_<wbr>mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines how intents are detected from user queries. * MATCH_MODE_HYBRID: Best for agents with a small number of
examples in intents and/or wide use of templates syntax and composite entities. * MATCH_MODE_ML_ONLY: Can be used for
agents with a large number of examples in intents, especially the ones using @sys.any or very large developer entities.
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
            <td class="align-top">supported_<wbr>language_<wbr>codes</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of all languages supported by this agent (except for the defaultLanguageCode).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tier</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The agent tier. If not specified, TIER_STANDARD is assumed. * TIER_STANDARD: Standard tier. * TIER_ENTERPRISE:
Enterprise tier (Essentials). * TIER_ENTERPRISE_PLUS: Enterprise tier (Plus). NOTE: This field seems to have eventual
consistency in the API. Updating this field to a new value, or even creating a new agent with a tier that is different
from a previous agent in the same project will take some time to propagate. The provider will wait for the API to show
consistency, which can lead to longer apply times.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time_<wbr>zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The time zone of this agent from the [time zone database](https://www.iana.org/time-zones), e.g., America/New_York,
Europe/Paris.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Agent Output Properties

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
            <td class="align-top">Api<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} API version displayed in Dialogflow console. If not specified, V2 API is assumed. Clients are free to query different
service endpoints for different API versions. However, bots connectors and webhook calls will follow the specified API
version. * API_VERSION_V1: Legacy V1 API. * API_VERSION_V2: V2 API. * API_VERSION_V2_BETA_1: V2beta1 API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Avatar<wbr>Uri</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the agent&#39;s avatar, which are used throughout the Dialogflow console. When an image URL is entered into this
field, the Dialogflow will save the image in the backend. The address of the backend image returned from the API will be
shown in the [avatarUriBackend] field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Avatar<wbr>Uri<wbr>Backend</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the agent&#39;s avatar as returned from the API. Output only. To provide an image URL for the agent avatar, the
[avatarUri] field can be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Classification<wbr>Threshold</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} To filter out false positive results and still get variety in matched natural language inputs for your agent, you can
tune the machine learning classification threshold. If the returned score value is less than the threshold value, then a
fallback intent will be triggered or, if there are no fallback intents defined, no intent will be triggered. The score
values range from 0.0 (completely uncertain) to 1.0 (completely certain). If set to 0.0, the default of 0.3 is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Language<wbr>Code</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The default language of the agent as a language tag. [See Language
Support](https://cloud.google.com/dialogflow/docs/reference/language) for a list of the currently supported language
codes. This field cannot be updated after creation.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The description of this agent. The maximum length is 500 characters. If exceeded, the request is rejected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of this agent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Logging</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Determines whether this agent should log conversation queries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Match<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Determines how intents are detected from user queries. * MATCH_MODE_HYBRID: Best for agents with a small number of
examples in intents and/or wide use of templates syntax and composite entities. * MATCH_MODE_ML_ONLY: Can be used for
agents with a large number of examples in intents, especially the ones using @sys.any or very large developer entities.
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
            <td class="align-top">Supported<wbr>Language<wbr>Codes</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} The list of all languages supported by this agent (except for the defaultLanguageCode).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tier</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The agent tier. If not specified, TIER_STANDARD is assumed. * TIER_STANDARD: Standard tier. * TIER_ENTERPRISE:
Enterprise tier (Essentials). * TIER_ENTERPRISE_PLUS: Enterprise tier (Plus). NOTE: This field seems to have eventual
consistency in the API. Updating this field to a new value, or even creating a new agent with a tier that is different
from a previous agent in the same project will take some time to propagate. The provider will wait for the API to show
consistency, which can lead to longer apply times.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Zone</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The time zone of this agent from the [time zone database](https://www.iana.org/time-zones), e.g., America/New_York,
Europe/Paris.
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
            <td class="align-top">Api<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} API version displayed in Dialogflow console. If not specified, V2 API is assumed. Clients are free to query different
service endpoints for different API versions. However, bots connectors and webhook calls will follow the specified API
version. * API_VERSION_V1: Legacy V1 API. * API_VERSION_V2: V2 API. * API_VERSION_V2_BETA_1: V2beta1 API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Avatar<wbr>Uri</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the agent&#39;s avatar, which are used throughout the Dialogflow console. When an image URL is entered into this
field, the Dialogflow will save the image in the backend. The address of the backend image returned from the API will be
shown in the [avatarUriBackend] field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Avatar<wbr>Uri<wbr>Backend</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the agent&#39;s avatar as returned from the API. Output only. To provide an image URL for the agent avatar, the
[avatarUri] field can be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Classification<wbr>Threshold</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} To filter out false positive results and still get variety in matched natural language inputs for your agent, you can
tune the machine learning classification threshold. If the returned score value is less than the threshold value, then a
fallback intent will be triggered or, if there are no fallback intents defined, no intent will be triggered. The score
values range from 0.0 (completely uncertain) to 1.0 (completely certain). If set to 0.0, the default of 0.3 is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Language<wbr>Code</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The default language of the agent as a language tag. [See Language
Support](https://cloud.google.com/dialogflow/docs/reference/language) for a list of the currently supported language
codes. This field cannot be updated after creation.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The description of this agent. The maximum length is 500 characters. If exceeded, the request is rejected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of this agent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Logging</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Determines whether this agent should log conversation queries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Match<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Determines how intents are detected from user queries. * MATCH_MODE_HYBRID: Best for agents with a small number of
examples in intents and/or wide use of templates syntax and composite entities. * MATCH_MODE_ML_ONLY: Can be used for
agents with a large number of examples in intents, especially the ones using @sys.any or very large developer entities.
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
            <td class="align-top">Supported<wbr>Language<wbr>Codes</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} The list of all languages supported by this agent (except for the defaultLanguageCode).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tier</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The agent tier. If not specified, TIER_STANDARD is assumed. * TIER_STANDARD: Standard tier. * TIER_ENTERPRISE:
Enterprise tier (Essentials). * TIER_ENTERPRISE_PLUS: Enterprise tier (Plus). NOTE: This field seems to have eventual
consistency in the API. Updating this field to a new value, or even creating a new agent with a tier that is different
from a previous agent in the same project will take some time to propagate. The provider will wait for the API to show
consistency, which can lead to longer apply times.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Zone</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The time zone of this agent from the [time zone database](https://www.iana.org/time-zones), e.g., America/New_York,
Europe/Paris.
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
            <td class="align-top">api<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} API version displayed in Dialogflow console. If not specified, V2 API is assumed. Clients are free to query different
service endpoints for different API versions. However, bots connectors and webhook calls will follow the specified API
version. * API_VERSION_V1: Legacy V1 API. * API_VERSION_V2: V2 API. * API_VERSION_V2_BETA_1: V2beta1 API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">avatar<wbr>Uri</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the agent&#39;s avatar, which are used throughout the Dialogflow console. When an image URL is entered into this
field, the Dialogflow will save the image in the backend. The address of the backend image returned from the API will be
shown in the [avatarUriBackend] field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">avatar<wbr>Uri<wbr>Backend</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the agent&#39;s avatar as returned from the API. Output only. To provide an image URL for the agent avatar, the
[avatarUri] field can be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">classification<wbr>Threshold</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} To filter out false positive results and still get variety in matched natural language inputs for your agent, you can
tune the machine learning classification threshold. If the returned score value is less than the threshold value, then a
fallback intent will be triggered or, if there are no fallback intents defined, no intent will be triggered. The score
values range from 0.0 (completely uncertain) to 1.0 (completely certain). If set to 0.0, the default of 0.3 is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Language<wbr>Code</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The default language of the agent as a language tag. [See Language
Support](https://cloud.google.com/dialogflow/docs/reference/language) for a list of the currently supported language
codes. This field cannot be updated after creation.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The description of this agent. The maximum length is 500 characters. If exceeded, the request is rejected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of this agent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Logging</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Determines whether this agent should log conversation queries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">match<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Determines how intents are detected from user queries. * MATCH_MODE_HYBRID: Best for agents with a small number of
examples in intents and/or wide use of templates syntax and composite entities. * MATCH_MODE_ML_ONLY: Can be used for
agents with a large number of examples in intents, especially the ones using @sys.any or very large developer entities.
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
            <td class="align-top">supported<wbr>Language<wbr>Codes</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} The list of all languages supported by this agent (except for the defaultLanguageCode).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tier</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The agent tier. If not specified, TIER_STANDARD is assumed. * TIER_STANDARD: Standard tier. * TIER_ENTERPRISE:
Enterprise tier (Essentials). * TIER_ENTERPRISE_PLUS: Enterprise tier (Plus). NOTE: This field seems to have eventual
consistency in the API. Updating this field to a new value, or even creating a new agent with a tier that is different
from a previous agent in the same project will take some time to propagate. The provider will wait for the API to show
consistency, which can lead to longer apply times.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time<wbr>Zone</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The time zone of this agent from the [time zone database](https://www.iana.org/time-zones), e.g., America/New_York,
Europe/Paris.
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
            <td class="align-top">api_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} API version displayed in Dialogflow console. If not specified, V2 API is assumed. Clients are free to query different
service endpoints for different API versions. However, bots connectors and webhook calls will follow the specified API
version. * API_VERSION_V1: Legacy V1 API. * API_VERSION_V2: V2 API. * API_VERSION_V2_BETA_1: V2beta1 API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">avatar_<wbr>uri</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the agent&#39;s avatar, which are used throughout the Dialogflow console. When an image URL is entered into this
field, the Dialogflow will save the image in the backend. The address of the backend image returned from the API will be
shown in the [avatarUriBackend] field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">avatar_<wbr>uri_<wbr>backend</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the agent&#39;s avatar as returned from the API. Output only. To provide an image URL for the agent avatar, the
[avatarUri] field can be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">classification_<wbr>threshold</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} To filter out false positive results and still get variety in matched natural language inputs for your agent, you can
tune the machine learning classification threshold. If the returned score value is less than the threshold value, then a
fallback intent will be triggered or, if there are no fallback intents defined, no intent will be triggered. The score
values range from 0.0 (completely uncertain) to 1.0 (completely certain). If set to 0.0, the default of 0.3 is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>language_<wbr>code</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The default language of the agent as a language tag. [See Language
Support](https://cloud.google.com/dialogflow/docs/reference/language) for a list of the currently supported language
codes. This field cannot be updated after creation.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The description of this agent. The maximum length is 500 characters. If exceeded, the request is rejected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of this agent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>logging</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Determines whether this agent should log conversation queries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">match_<wbr>mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Determines how intents are detected from user queries. * MATCH_MODE_HYBRID: Best for agents with a small number of
examples in intents and/or wide use of templates syntax and composite entities. * MATCH_MODE_ML_ONLY: Can be used for
agents with a large number of examples in intents, especially the ones using @sys.any or very large developer entities.
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
            <td class="align-top">supported_<wbr>language_<wbr>codes</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} The list of all languages supported by this agent (except for the defaultLanguageCode).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tier</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The agent tier. If not specified, TIER_STANDARD is assumed. * TIER_STANDARD: Standard tier. * TIER_ENTERPRISE:
Enterprise tier (Essentials). * TIER_ENTERPRISE_PLUS: Enterprise tier (Plus). NOTE: This field seems to have eventual
consistency in the API. Updating this field to a new value, or even creating a new agent with a tier that is different
from a previous agent in the same project will take some time to propagate. The provider will wait for the API to show
consistency, which can lead to longer apply times.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time_<wbr>zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The time zone of this agent from the [time zone database](https://www.iana.org/time-zones), e.g., America/New_York,
Europe/Paris.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Agent Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/diagflow/#AgentState">AgentState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/diagflow/#Agent">Agent</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>api_version=None<span class="p">, </span>avatar_uri=None<span class="p">, </span>avatar_uri_backend=None<span class="p">, </span>classification_threshold=None<span class="p">, </span>default_language_code=None<span class="p">, </span>description=None<span class="p">, </span>display_name=None<span class="p">, </span>enable_logging=None<span class="p">, </span>match_mode=None<span class="p">, </span>project=None<span class="p">, </span>supported_language_codes=None<span class="p">, </span>tier=None<span class="p">, </span>time_zone=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAgent<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/diagflow?tab=doc#AgentState">AgentState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/diagflow?tab=doc#Agent">Agent</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Diagflow.Agent.html">Agent</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Diagflow.AgentState.html">AgentState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Agent resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Api<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
API version displayed in Dialogflow console. If not specified, V2 API is assumed. Clients are free to query different
service endpoints for different API versions. However, bots connectors and webhook calls will follow the specified API
version. * API_VERSION_V1: Legacy V1 API. * API_VERSION_V2: V2 API. * API_VERSION_V2_BETA_1: V2beta1 API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Avatar<wbr>Uri</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the agent&#39;s avatar, which are used throughout the Dialogflow console. When an image URL is entered into this
field, the Dialogflow will save the image in the backend. The address of the backend image returned from the API will be
shown in the [avatarUriBackend] field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Avatar<wbr>Uri<wbr>Backend</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the agent&#39;s avatar as returned from the API. Output only. To provide an image URL for the agent avatar, the
[avatarUri] field can be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Classification<wbr>Threshold</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
To filter out false positive results and still get variety in matched natural language inputs for your agent, you can
tune the machine learning classification threshold. If the returned score value is less than the threshold value, then a
fallback intent will be triggered or, if there are no fallback intents defined, no intent will be triggered. The score
values range from 0.0 (completely uncertain) to 1.0 (completely certain). If set to 0.0, the default of 0.3 is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Language<wbr>Code</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default language of the agent as a language tag. [See Language
Support](https://cloud.google.com/dialogflow/docs/reference/language) for a list of the currently supported language
codes. This field cannot be updated after creation.
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
The description of this agent. The maximum length is 500 characters. If exceeded, the request is rejected.
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
The name of this agent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Logging</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines whether this agent should log conversation queries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Match<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines how intents are detected from user queries. * MATCH_MODE_HYBRID: Best for agents with a small number of
examples in intents and/or wide use of templates syntax and composite entities. * MATCH_MODE_ML_ONLY: Can be used for
agents with a large number of examples in intents, especially the ones using @sys.any or very large developer entities.
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
            <td class="align-top">Supported<wbr>Language<wbr>Codes</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of all languages supported by this agent (except for the defaultLanguageCode).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tier</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The agent tier. If not specified, TIER_STANDARD is assumed. * TIER_STANDARD: Standard tier. * TIER_ENTERPRISE:
Enterprise tier (Essentials). * TIER_ENTERPRISE_PLUS: Enterprise tier (Plus). NOTE: This field seems to have eventual
consistency in the API. Updating this field to a new value, or even creating a new agent with a tier that is different
from a previous agent in the same project will take some time to propagate. The provider will wait for the API to show
consistency, which can lead to longer apply times.
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
The time zone of this agent from the [time zone database](https://www.iana.org/time-zones), e.g., America/New_York,
Europe/Paris.
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
            <td class="align-top">Api<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
API version displayed in Dialogflow console. If not specified, V2 API is assumed. Clients are free to query different
service endpoints for different API versions. However, bots connectors and webhook calls will follow the specified API
version. * API_VERSION_V1: Legacy V1 API. * API_VERSION_V2: V2 API. * API_VERSION_V2_BETA_1: V2beta1 API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Avatar<wbr>Uri</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the agent&#39;s avatar, which are used throughout the Dialogflow console. When an image URL is entered into this
field, the Dialogflow will save the image in the backend. The address of the backend image returned from the API will be
shown in the [avatarUriBackend] field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Avatar<wbr>Uri<wbr>Backend</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the agent&#39;s avatar as returned from the API. Output only. To provide an image URL for the agent avatar, the
[avatarUri] field can be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Classification<wbr>Threshold</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
To filter out false positive results and still get variety in matched natural language inputs for your agent, you can
tune the machine learning classification threshold. If the returned score value is less than the threshold value, then a
fallback intent will be triggered or, if there are no fallback intents defined, no intent will be triggered. The score
values range from 0.0 (completely uncertain) to 1.0 (completely certain). If set to 0.0, the default of 0.3 is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Language<wbr>Code</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default language of the agent as a language tag. [See Language
Support](https://cloud.google.com/dialogflow/docs/reference/language) for a list of the currently supported language
codes. This field cannot be updated after creation.
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
The description of this agent. The maximum length is 500 characters. If exceeded, the request is rejected.
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
The name of this agent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Logging</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines whether this agent should log conversation queries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Match<wbr>Mode</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines how intents are detected from user queries. * MATCH_MODE_HYBRID: Best for agents with a small number of
examples in intents and/or wide use of templates syntax and composite entities. * MATCH_MODE_ML_ONLY: Can be used for
agents with a large number of examples in intents, especially the ones using @sys.any or very large developer entities.
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
            <td class="align-top">Supported<wbr>Language<wbr>Codes</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of all languages supported by this agent (except for the defaultLanguageCode).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tier</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The agent tier. If not specified, TIER_STANDARD is assumed. * TIER_STANDARD: Standard tier. * TIER_ENTERPRISE:
Enterprise tier (Essentials). * TIER_ENTERPRISE_PLUS: Enterprise tier (Plus). NOTE: This field seems to have eventual
consistency in the API. Updating this field to a new value, or even creating a new agent with a tier that is different
from a previous agent in the same project will take some time to propagate. The provider will wait for the API to show
consistency, which can lead to longer apply times.
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
The time zone of this agent from the [time zone database](https://www.iana.org/time-zones), e.g., America/New_York,
Europe/Paris.
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
            <td class="align-top">api<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
API version displayed in Dialogflow console. If not specified, V2 API is assumed. Clients are free to query different
service endpoints for different API versions. However, bots connectors and webhook calls will follow the specified API
version. * API_VERSION_V1: Legacy V1 API. * API_VERSION_V2: V2 API. * API_VERSION_V2_BETA_1: V2beta1 API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">avatar<wbr>Uri</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the agent&#39;s avatar, which are used throughout the Dialogflow console. When an image URL is entered into this
field, the Dialogflow will save the image in the backend. The address of the backend image returned from the API will be
shown in the [avatarUriBackend] field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">avatar<wbr>Uri<wbr>Backend</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the agent&#39;s avatar as returned from the API. Output only. To provide an image URL for the agent avatar, the
[avatarUri] field can be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">classification<wbr>Threshold</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
To filter out false positive results and still get variety in matched natural language inputs for your agent, you can
tune the machine learning classification threshold. If the returned score value is less than the threshold value, then a
fallback intent will be triggered or, if there are no fallback intents defined, no intent will be triggered. The score
values range from 0.0 (completely uncertain) to 1.0 (completely certain). If set to 0.0, the default of 0.3 is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Language<wbr>Code</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default language of the agent as a language tag. [See Language
Support](https://cloud.google.com/dialogflow/docs/reference/language) for a list of the currently supported language
codes. This field cannot be updated after creation.
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
The description of this agent. The maximum length is 500 characters. If exceeded, the request is rejected.
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
The name of this agent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Logging</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines whether this agent should log conversation queries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">match<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines how intents are detected from user queries. * MATCH_MODE_HYBRID: Best for agents with a small number of
examples in intents and/or wide use of templates syntax and composite entities. * MATCH_MODE_ML_ONLY: Can be used for
agents with a large number of examples in intents, especially the ones using @sys.any or very large developer entities.
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
            <td class="align-top">supported<wbr>Language<wbr>Codes</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of all languages supported by this agent (except for the defaultLanguageCode).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tier</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The agent tier. If not specified, TIER_STANDARD is assumed. * TIER_STANDARD: Standard tier. * TIER_ENTERPRISE:
Enterprise tier (Essentials). * TIER_ENTERPRISE_PLUS: Enterprise tier (Plus). NOTE: This field seems to have eventual
consistency in the API. Updating this field to a new value, or even creating a new agent with a tier that is different
from a previous agent in the same project will take some time to propagate. The provider will wait for the API to show
consistency, which can lead to longer apply times.
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
The time zone of this agent from the [time zone database](https://www.iana.org/time-zones), e.g., America/New_York,
Europe/Paris.
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
            <td class="align-top">api_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
API version displayed in Dialogflow console. If not specified, V2 API is assumed. Clients are free to query different
service endpoints for different API versions. However, bots connectors and webhook calls will follow the specified API
version. * API_VERSION_V1: Legacy V1 API. * API_VERSION_V2: V2 API. * API_VERSION_V2_BETA_1: V2beta1 API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">avatar_<wbr>uri</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the agent&#39;s avatar, which are used throughout the Dialogflow console. When an image URL is entered into this
field, the Dialogflow will save the image in the backend. The address of the backend image returned from the API will be
shown in the [avatarUriBackend] field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">avatar_<wbr>uri_<wbr>backend</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the agent&#39;s avatar as returned from the API. Output only. To provide an image URL for the agent avatar, the
[avatarUri] field can be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">classification_<wbr>threshold</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
To filter out false positive results and still get variety in matched natural language inputs for your agent, you can
tune the machine learning classification threshold. If the returned score value is less than the threshold value, then a
fallback intent will be triggered or, if there are no fallback intents defined, no intent will be triggered. The score
values range from 0.0 (completely uncertain) to 1.0 (completely certain). If set to 0.0, the default of 0.3 is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>language_<wbr>code</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default language of the agent as a language tag. [See Language
Support](https://cloud.google.com/dialogflow/docs/reference/language) for a list of the currently supported language
codes. This field cannot be updated after creation.
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
The description of this agent. The maximum length is 500 characters. If exceeded, the request is rejected.
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
The name of this agent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>logging</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines whether this agent should log conversation queries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">match_<wbr>mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines how intents are detected from user queries. * MATCH_MODE_HYBRID: Best for agents with a small number of
examples in intents and/or wide use of templates syntax and composite entities. * MATCH_MODE_ML_ONLY: Can be used for
agents with a large number of examples in intents, especially the ones using @sys.any or very large developer entities.
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
            <td class="align-top">supported_<wbr>language_<wbr>codes</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of all languages supported by this agent (except for the defaultLanguageCode).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tier</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The agent tier. If not specified, TIER_STANDARD is assumed. * TIER_STANDARD: Standard tier. * TIER_ENTERPRISE:
Enterprise tier (Essentials). * TIER_ENTERPRISE_PLUS: Enterprise tier (Plus). NOTE: This field seems to have eventual
consistency in the API. Updating this field to a new value, or even creating a new agent with a tier that is different
from a previous agent in the same project will take some time to propagate. The provider will wait for the API to show
consistency, which can lead to longer apply times.
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
The time zone of this agent from the [time zone database](https://www.iana.org/time-zones), e.g., America/New_York,
Europe/Paris.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










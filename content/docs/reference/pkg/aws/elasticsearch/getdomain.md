
---
title: "GetDomain"
block_external_search_index: true
---

Use this data source to get information about an Elasticsearch Domain

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const myDomain = aws.elasticsearch.getDomain({
    domainName: "my-domain-name",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/d/elasticsearch_domain.html.markdown.





## Using GetDomain

{{< chooser language "typescript,python,go,csharp" >}}

{{% choosable language typescript %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getDomain<span class="p">(</span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticsearch/#GetDomainArgs">GetDomainArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#InvokeOptions">pulumi.InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticsearch/#GetDomainResult">GetDomainResult</a></span>></span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_domain(</span>domain_name=None<span class="p">, </span>tags=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupDomain<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#LookupDomainArgs">LookupDomainArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">pulumi.InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#LookupDomainResult">LookupDomainResult</a></span>, error)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language csharp %}}
<div class="highlight">
<pre class="chroma">
<code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetDomain </span><span class="p">{</span>
    <span class="k">public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.GetDomainResult.html">GetDomainResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.GetDomainArgs.html">GetDomainArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span>
<span class="p">}</span></code></pre>
</div>
{{% /choosable %}}" }}



The following arguments are supported:



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## GetDomain Result

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Access<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The policy document attached to the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Advanced<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Configs<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainclusterconfig">List&lt;Get<wbr>Domain<wbr>Cluster<wbr>Config&gt;</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cognito<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomaincognitooption">List&lt;Get<wbr>Domain<wbr>Cognito<wbr>Option&gt;</a></span>
    </dt>
    <dd>{{% md %}}Domain Amazon Cognito Authentication options for Kibana.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Status of the creation of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deleted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Status of the deletion of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Domain<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique identifier for the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainebsoption">List&lt;Get<wbr>Domain<wbr>Ebs<wbr>Option&gt;</a></span>
    </dt>
    <dd>{{% md %}}EBS Options for the instances in the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elasticsearch<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ElasticSearch version for the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encryption<wbr>At<wbr>Rests<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainencryptionatrest">List&lt;Get<wbr>Domain<wbr>Encryption<wbr>At<wbr>Rest&gt;</a></span>
    </dt>
    <dd>{{% md %}}Domain encryption at rest related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to submit index, search, and data upload requests.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kibana<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to access the Kibana application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Log<wbr>Publishing<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainlogpublishingoption">List&lt;Get<wbr>Domain<wbr>Log<wbr>Publishing<wbr>Option&gt;</a></span>
    </dt>
    <dd>{{% md %}}Domain log publishing related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>To<wbr>Node<wbr>Encryptions<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainnodetonodeencryption">List&lt;Get<wbr>Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption&gt;</a></span>
    </dt>
    <dd>{{% md %}}Domain in transit encryption related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Processing<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Status of a configuration change in the domain.
* `snapshot_options` – Domain snapshot related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainsnapshotoption">List&lt;Get<wbr>Domain<wbr>Snapshot<wbr>Option&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}The tags assigned to the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainvpcoption">List&lt;Get<wbr>Domain<wbr>Vpc<wbr>Option&gt;</a></span>
    </dt>
    <dd>{{% md %}}VPC Options for private Elasticsearch domains.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Access<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The policy document attached to the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Advanced<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Configs<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainclusterconfig">[]Get<wbr>Domain<wbr>Cluster<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cognito<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomaincognitooption">[]Get<wbr>Domain<wbr>Cognito<wbr>Option</a></span>
    </dt>
    <dd>{{% md %}}Domain Amazon Cognito Authentication options for Kibana.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Status of the creation of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deleted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Status of the deletion of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Domain<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique identifier for the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainebsoption">[]Get<wbr>Domain<wbr>Ebs<wbr>Option</a></span>
    </dt>
    <dd>{{% md %}}EBS Options for the instances in the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elasticsearch<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ElasticSearch version for the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encryption<wbr>At<wbr>Rests<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainencryptionatrest">[]Get<wbr>Domain<wbr>Encryption<wbr>At<wbr>Rest</a></span>
    </dt>
    <dd>{{% md %}}Domain encryption at rest related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to submit index, search, and data upload requests.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kibana<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to access the Kibana application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Log<wbr>Publishing<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainlogpublishingoption">[]Get<wbr>Domain<wbr>Log<wbr>Publishing<wbr>Option</a></span>
    </dt>
    <dd>{{% md %}}Domain log publishing related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>To<wbr>Node<wbr>Encryptions<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainnodetonodeencryption">[]Get<wbr>Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption</a></span>
    </dt>
    <dd>{{% md %}}Domain in transit encryption related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Processing<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Status of a configuration change in the domain.
* `snapshot_options` – Domain snapshot related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainsnapshotoption">[]Get<wbr>Domain<wbr>Snapshot<wbr>Option</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}The tags assigned to the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainvpcoption">[]Get<wbr>Domain<wbr>Vpc<wbr>Option</a></span>
    </dt>
    <dd>{{% md %}}VPC Options for private Elasticsearch domains.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">access<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The policy document attached to the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">advanced<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Configs<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainclusterconfig">Get<wbr>Domain<wbr>Cluster<wbr>Config[]</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cognito<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomaincognitooption">Get<wbr>Domain<wbr>Cognito<wbr>Option[]</a></span>
    </dt>
    <dd>{{% md %}}Domain Amazon Cognito Authentication options for Kibana.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Status of the creation of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deleted<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Status of the deletion of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">domain<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique identifier for the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainebsoption">Get<wbr>Domain<wbr>Ebs<wbr>Option[]</a></span>
    </dt>
    <dd>{{% md %}}EBS Options for the instances in the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">elasticsearch<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ElasticSearch version for the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">encryption<wbr>At<wbr>Rests<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainencryptionatrest">Get<wbr>Domain<wbr>Encryption<wbr>At<wbr>Rest[]</a></span>
    </dt>
    <dd>{{% md %}}Domain encryption at rest related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to submit index, search, and data upload requests.
{{% /md %}}</dd>

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kibana<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to access the Kibana application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">log<wbr>Publishing<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainlogpublishingoption">Get<wbr>Domain<wbr>Log<wbr>Publishing<wbr>Option[]</a></span>
    </dt>
    <dd>{{% md %}}Domain log publishing related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">node<wbr>To<wbr>Node<wbr>Encryptions<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainnodetonodeencryption">Get<wbr>Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption[]</a></span>
    </dt>
    <dd>{{% md %}}Domain in transit encryption related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">processing<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Status of a configuration change in the domain.
* `snapshot_options` – Domain snapshot related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainsnapshotoption">Get<wbr>Domain<wbr>Snapshot<wbr>Option[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}The tags assigned to the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainvpcoption">Get<wbr>Domain<wbr>Vpc<wbr>Option[]</a></span>
    </dt>
    <dd>{{% md %}}VPC Options for private Elasticsearch domains.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">access_<wbr>policies<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The policy document attached to the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">advanced_<wbr>options<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>configs<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainclusterconfig">List[Get<wbr>Domain<wbr>Cluster<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cognito_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomaincognitooption">List[Get<wbr>Domain<wbr>Cognito<wbr>Option]</a></span>
    </dt>
    <dd>{{% md %}}Domain Amazon Cognito Authentication options for Kibana.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Status of the creation of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deleted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Status of the deletion of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">domain_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Unique identifier for the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainebsoption">List[Get<wbr>Domain<wbr>Ebs<wbr>Option]</a></span>
    </dt>
    <dd>{{% md %}}EBS Options for the instances in the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">elasticsearch_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ElasticSearch version for the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">encryption_<wbr>at_<wbr>rests<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainencryptionatrest">List[Get<wbr>Domain<wbr>Encryption<wbr>At<wbr>Rest]</a></span>
    </dt>
    <dd>{{% md %}}Domain encryption at rest related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to submit index, search, and data upload requests.
{{% /md %}}</dd>

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kibana_<wbr>endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to access the Kibana application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">log_<wbr>publishing_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainlogpublishingoption">List[Get<wbr>Domain<wbr>Log<wbr>Publishing<wbr>Option]</a></span>
    </dt>
    <dd>{{% md %}}Domain log publishing related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">node_<wbr>to_<wbr>node_<wbr>encryptions<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainnodetonodeencryption">List[Get<wbr>Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption]</a></span>
    </dt>
    <dd>{{% md %}}Domain in transit encryption related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">processing<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Status of a configuration change in the domain.
* `snapshot_options` – Domain snapshot related options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainsnapshotoption">List[Get<wbr>Domain<wbr>Snapshot<wbr>Option]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The tags assigned to the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainvpcoption">List[Get<wbr>Domain<wbr>Vpc<wbr>Option]</a></span>
    </dt>
    <dd>{{% md %}}VPC Options for private Elasticsearch domains.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## Supporting Types

#### GetDomainClusterConfig
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetDomainClusterConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#GetDomainClusterConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.GetDomainClusterConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Dedicated<wbr>Master<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Number of dedicated master nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Dedicated<wbr>Master<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether dedicated master nodes are enabled for the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Dedicated<wbr>Master<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Instance type of the dedicated master nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Number of instances in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Instance type of data nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Zone<wbr>Awareness<wbr>Configs<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainclusterconfigzoneawarenessconfig">List&lt;Get<wbr>Domain<wbr>Cluster<wbr>Config<wbr>Zone<wbr>Awareness<wbr>Config<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing zone awareness settings.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Zone<wbr>Awareness<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether zone awareness is enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Dedicated<wbr>Master<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Number of dedicated master nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Dedicated<wbr>Master<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether dedicated master nodes are enabled for the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Dedicated<wbr>Master<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Instance type of the dedicated master nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Number of instances in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Instance type of data nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Zone<wbr>Awareness<wbr>Configs<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainclusterconfigzoneawarenessconfig">[]Get<wbr>Domain<wbr>Cluster<wbr>Config<wbr>Zone<wbr>Awareness<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing zone awareness settings.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Zone<wbr>Awareness<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether zone awareness is enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">dedicated<wbr>Master<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Number of dedicated master nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">dedicated<wbr>Master<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Indicates whether dedicated master nodes are enabled for the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">dedicated<wbr>Master<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Instance type of the dedicated master nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Number of instances in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Instance type of data nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">zone<wbr>Awareness<wbr>Configs<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainclusterconfigzoneawarenessconfig">Get<wbr>Domain<wbr>Cluster<wbr>Config<wbr>Zone<wbr>Awareness<wbr>Config[]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing zone awareness settings.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">zone<wbr>Awareness<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Indicates whether zone awareness is enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">dedicated<wbr>Master<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Number of dedicated master nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">dedicated<wbr>Master<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether dedicated master nodes are enabled for the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">dedicated<wbr>Master<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Instance type of the dedicated master nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Number of instances in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Instance type of data nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">zone<wbr>Awareness<wbr>Configs<span class="property-indicator"></span>
        <span class="property-type"><a href="#getdomainclusterconfigzoneawarenessconfig">List[Get<wbr>Domain<wbr>Cluster<wbr>Config<wbr>Zone<wbr>Awareness<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing zone awareness settings.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">zone<wbr>Awareness<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether zone awareness is enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetDomainClusterConfigZoneAwarenessConfig
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetDomainClusterConfigZoneAwarenessConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#GetDomainClusterConfigZoneAwarenessConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.GetDomainClusterConfigZoneAwarenessConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Availability<wbr>Zone<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Number of availability zones used.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Availability<wbr>Zone<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Number of availability zones used.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">availability<wbr>Zone<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Number of availability zones used.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">availability<wbr>Zone<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Number of availability zones used.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetDomainCognitoOption
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetDomainCognitoOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#GetDomainCognitoOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.GetDomainCognitoOption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Identity<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity pool used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM Role with the AmazonESCognitoAccess policy attached.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cognito User pool used by the domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Identity<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity pool used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM Role with the AmazonESCognitoAccess policy attached.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cognito User pool used by the domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">identity<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity pool used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM Role with the AmazonESCognitoAccess policy attached.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cognito User pool used by the domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">identity_<wbr>pool_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity pool used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM Role with the AmazonESCognitoAccess policy attached.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user_<wbr>pool_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Cognito User pool used by the domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetDomainEbsOption
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetDomainEbsOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#GetDomainEbsOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.GetDomainEbsOption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Ebs<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether EBS volumes are attached to data nodes in the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Iops<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The baseline input/output (I/O) performance of EBS volumes
attached to data nodes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size of EBS volumes attached to data nodes (in GB).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of EBS volumes attached to data nodes.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Ebs<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether EBS volumes are attached to data nodes in the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Iops<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The baseline input/output (I/O) performance of EBS volumes
attached to data nodes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size of EBS volumes attached to data nodes (in GB).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of EBS volumes attached to data nodes.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">ebs<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether EBS volumes are attached to data nodes in the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">iops<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The baseline input/output (I/O) performance of EBS volumes
attached to data nodes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The size of EBS volumes attached to data nodes (in GB).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of EBS volumes attached to data nodes.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">ebs<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether EBS volumes are attached to data nodes in the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">iops<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The baseline input/output (I/O) performance of EBS volumes
attached to data nodes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The size of EBS volumes attached to data nodes (in GB).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of EBS volumes attached to data nodes.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetDomainEncryptionAtRest
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetDomainEncryptionAtRest">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#GetDomainEncryptionAtRest">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.GetDomainEncryptionAtRest.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The KMS key id used to encrypt data at rest.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The KMS key id used to encrypt data at rest.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The KMS key id used to encrypt data at rest.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The KMS key id used to encrypt data at rest.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetDomainLogPublishingOption
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetDomainLogPublishingOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#GetDomainLogPublishingOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.GetDomainLogPublishingOption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cloudwatch<wbr>Log<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudWatch Log Group where the logs are published.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Log<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of Elasticsearch log being published.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cloudwatch<wbr>Log<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudWatch Log Group where the logs are published.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Log<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of Elasticsearch log being published.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cloudwatch<wbr>Log<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudWatch Log Group where the logs are published.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">log<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of Elasticsearch log being published.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cloudwatch_<wbr>log_<wbr>group_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CloudWatch Log Group where the logs are published.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">log<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of Elasticsearch log being published.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetDomainNodeToNodeEncryption
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetDomainNodeToNodeEncryption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#GetDomainNodeToNodeEncryption">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.GetDomainNodeToNodeEncryption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether node to node encryption is enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetDomainSnapshotOption
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetDomainSnapshotOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#GetDomainSnapshotOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.GetDomainSnapshotOption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Automated<wbr>Snapshot<wbr>Start<wbr>Hour<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Hour during which the service takes an automated daily
snapshot of the indices in the domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Automated<wbr>Snapshot<wbr>Start<wbr>Hour<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Hour during which the service takes an automated daily
snapshot of the indices in the domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">automated<wbr>Snapshot<wbr>Start<wbr>Hour<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Hour during which the service takes an automated daily
snapshot of the indices in the domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">automated<wbr>Snapshot<wbr>Start<wbr>Hour<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Hour during which the service takes an automated daily
snapshot of the indices in the domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetDomainVpcOption
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetDomainVpcOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#GetDomainVpcOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.GetDomainVpcOption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The availability zones used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The security groups used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The subnets used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The VPC used by the domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The availability zones used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The security groups used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The subnets used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The VPC used by the domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The availability zones used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The security groups used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The subnets used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The VPC used by the domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">availability_<wbr>zones<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The availability zones used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The security groups used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The subnets used by the domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The VPC used by the domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}









---
title: "Cluster"
block_external_search_index: true
---

Manages AWS Managed Streaming for Kafka cluster

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const vpc = new aws.ec2.Vpc("vpc", {
    cidrBlock: "192.168.0.0/22",
});
const azs = aws.getAvailabilityZones({
    state: "available",
});
const subnetAz1 = new aws.ec2.Subnet("subnet_az1", {
    availabilityZone: azs.names[0],
    cidrBlock: "192.168.0.0/24",
    vpcId: vpc.id,
});
const subnetAz2 = new aws.ec2.Subnet("subnet_az2", {
    availabilityZone: azs.names[1],
    cidrBlock: "192.168.1.0/24",
    vpcId: vpc.id,
});
const subnetAz3 = new aws.ec2.Subnet("subnet_az3", {
    availabilityZone: azs.names[2],
    cidrBlock: "192.168.2.0/24",
    vpcId: vpc.id,
});
const sg = new aws.ec2.SecurityGroup("sg", {
    vpcId: vpc.id,
});
const kms = new aws.kms.Key("kms", {
    description: "example",
});
const example = new aws.msk.Cluster("example", {
    brokerNodeGroupInfo: {
        clientSubnets: [
            subnetAz1.id,
            subnetAz2.id,
            subnetAz3.id,
        ],
        ebsVolumeSize: 1000,
        instanceType: "kafka.m5.large",
        securityGroups: [sg.id],
    },
    clusterName: "example",
    encryptionInfo: {
        encryptionAtRestKmsKeyArn: kms.arn,
    },
    kafkaVersion: "2.1.0",
    numberOfBrokerNodes: 3,
    openMonitoring: {
        prometheus: {
            jmxExporter: {
                enabledInBroker: true,
            },
            nodeExporter: {
                enabledInBroker: true,
            },
        },
    },
    tags: {
        foo: "bar",
    },
});

export const zookeeperConnectString = example.zookeeperConnectString;
export const bootstrapBrokers = example.bootstrapBrokers;
export const bootstrapBrokersTls = example.bootstrapBrokersTls;
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/msk_cluster.html.markdown.



## Create a Cluster Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/msk/#Cluster">Cluster</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/msk/#ClusterArgs">ClusterArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Cluster</span><span class="p">(resource_name, opts=None, </span>broker_node_group_info=None<span class="p">, </span>client_authentication=None<span class="p">, </span>cluster_name=None<span class="p">, </span>configuration_info=None<span class="p">, </span>encryption_info=None<span class="p">, </span>enhanced_monitoring=None<span class="p">, </span>kafka_version=None<span class="p">, </span>number_of_broker_nodes=None<span class="p">, </span>open_monitoring=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewCluster<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterArgs">ClusterArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#Cluster">Cluster</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.Cluster.html">Cluster</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterArgs.html">ClusterArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Contructor Arguments

{{% choosable language nodejs %}}

<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        args
        <span class="property-indicator"></span>
    </dt>
    <dd>The arguments to use to populate this resource's properties.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>
{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        args
        <span class="property-indicator"></span>
    </dt>
    <dd>The arguments to use to populate this resource's properties.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        args
        <span class="property-indicator"></span>
    </dt>
    <dd>The arguments to use to populate this resource's properties.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

Resource Arguments




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Broker<wbr>Node<wbr>Group<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterbrokernodegroupinfo">Cluster<wbr>Broker<wbr>Node<wbr>Group<wbr>Info<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the broker nodes of the Kafka cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthentication">Cluster<wbr>Client<wbr>Authentication<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a client authentication. See below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the MSK cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterconfigurationinfo">Cluster<wbr>Configuration<wbr>Info<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a MSK Configuration to attach to Kafka brokers. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfo">Cluster<wbr>Encryption<wbr>Info<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying encryption. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enhanced<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the desired enhanced MSK CloudWatch monitoring level.  See [Monitoring Amazon MSK with Amazon CloudWatch](https://docs.aws.amazon.com/msk/latest/developerguide/monitoring.html)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Kafka<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specify the desired Kafka software version.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Number<wbr>Of<wbr>Broker<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The desired total number of broker nodes in the kafka cluster.  It must be a multiple of the number of specified client subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Open<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoring">Cluster<wbr>Open<wbr>Monitoring<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX and Node monitoring for the MSK cluster. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Broker<wbr>Node<wbr>Group<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterbrokernodegroupinfo">Cluster<wbr>Broker<wbr>Node<wbr>Group<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the broker nodes of the Kafka cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthentication">*Cluster<wbr>Client<wbr>Authentication</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a client authentication. See below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the MSK cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterconfigurationinfo">*Cluster<wbr>Configuration<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a MSK Configuration to attach to Kafka brokers. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfo">*Cluster<wbr>Encryption<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying encryption. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enhanced<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify the desired enhanced MSK CloudWatch monitoring level.  See [Monitoring Amazon MSK with Amazon CloudWatch](https://docs.aws.amazon.com/msk/latest/developerguide/monitoring.html)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Kafka<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specify the desired Kafka software version.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Number<wbr>Of<wbr>Broker<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The desired total number of broker nodes in the kafka cluster.  It must be a multiple of the number of specified client subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Open<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoring">*Cluster<wbr>Open<wbr>Monitoring</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX and Node monitoring for the MSK cluster. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">broker<wbr>Node<wbr>Group<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterbrokernodegroupinfo">Cluster<wbr>Broker<wbr>Node<wbr>Group<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the broker nodes of the Kafka cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthentication">Cluster<wbr>Client<wbr>Authentication?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a client authentication. See below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the MSK cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterconfigurationinfo">Cluster<wbr>Configuration<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a MSK Configuration to attach to Kafka brokers. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfo">Cluster<wbr>Encryption<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying encryption. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enhanced<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the desired enhanced MSK CloudWatch monitoring level.  See [Monitoring Amazon MSK with Amazon CloudWatch](https://docs.aws.amazon.com/msk/latest/developerguide/monitoring.html)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">kafka<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specify the desired Kafka software version.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">number<wbr>Of<wbr>Broker<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The desired total number of broker nodes in the kafka cluster.  It must be a multiple of the number of specified client subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">open<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoring">Cluster<wbr>Open<wbr>Monitoring?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX and Node monitoring for the MSK cluster. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">broker_<wbr>node_<wbr>group_<wbr>info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterbrokernodegroupinfo">Dict[Cluster<wbr>Broker<wbr>Node<wbr>Group<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the broker nodes of the Kafka cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client_<wbr>authentication<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthentication">Dict[Cluster<wbr>Client<wbr>Authentication]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a client authentication. See below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cluster_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the MSK cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration_<wbr>info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterconfigurationinfo">Dict[Cluster<wbr>Configuration<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a MSK Configuration to attach to Kafka brokers. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption_<wbr>info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfo">Dict[Cluster<wbr>Encryption<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying encryption. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enhanced_<wbr>monitoring<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify the desired enhanced MSK CloudWatch monitoring level.  See [Monitoring Amazon MSK with Amazon CloudWatch](https://docs.aws.amazon.com/msk/latest/developerguide/monitoring.html)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">kafka_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify the desired Kafka software version.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">number_<wbr>of_<wbr>broker_<wbr>nodes<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The desired total number of broker nodes in the kafka cluster.  It must be a multiple of the number of specified client subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">open_<wbr>monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoring">Dict[Cluster<wbr>Open<wbr>Monitoring]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX and Node monitoring for the MSK cluster. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Cluster Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bootstrap<wbr>Brokers<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs of kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `PLAINTEXT` or `TLS_PLAINTEXT`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bootstrap<wbr>Brokers<wbr>Tls<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more DNS names (or IPs) and TLS port pairs kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `TLS_PLAINTEXT` or `TLS`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Broker<wbr>Node<wbr>Group<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterbrokernodegroupinfo">Cluster<wbr>Broker<wbr>Node<wbr>Group<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the broker nodes of the Kafka cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Client<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthentication">Cluster<wbr>Client<wbr>Authentication?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a client authentication. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the MSK cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterconfigurationinfo">Cluster<wbr>Configuration<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a MSK Configuration to attach to Kafka brokers. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Current<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Current version of the MSK Cluster used for updates, e.g. `K13V1IB3VIYZZH`
* `encryption_info.0.encryption_at_rest_kms_key_arn` - The ARN of the KMS key used for encryption at rest of the broker data volumes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encryption<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfo">Cluster<wbr>Encryption<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying encryption. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enhanced<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the desired enhanced MSK CloudWatch monitoring level.  See [Monitoring Amazon MSK with Amazon CloudWatch](https://docs.aws.amazon.com/msk/latest/developerguide/monitoring.html)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kafka<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specify the desired Kafka software version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Number<wbr>Of<wbr>Broker<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The desired total number of broker nodes in the kafka cluster.  It must be a multiple of the number of specified client subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Open<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoring">Cluster<wbr>Open<wbr>Monitoring?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX and Node monitoring for the MSK cluster. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-"
            title="">Zookeeper<wbr>Connect<wbr>String<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs to use to connect to the Apache Zookeeper cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bootstrap<wbr>Brokers<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs of kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `PLAINTEXT` or `TLS_PLAINTEXT`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bootstrap<wbr>Brokers<wbr>Tls<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more DNS names (or IPs) and TLS port pairs kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `TLS_PLAINTEXT` or `TLS`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Broker<wbr>Node<wbr>Group<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterbrokernodegroupinfo">Cluster<wbr>Broker<wbr>Node<wbr>Group<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the broker nodes of the Kafka cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Client<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthentication">*Cluster<wbr>Client<wbr>Authentication</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a client authentication. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the MSK cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterconfigurationinfo">*Cluster<wbr>Configuration<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a MSK Configuration to attach to Kafka brokers. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Current<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Current version of the MSK Cluster used for updates, e.g. `K13V1IB3VIYZZH`
* `encryption_info.0.encryption_at_rest_kms_key_arn` - The ARN of the KMS key used for encryption at rest of the broker data volumes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encryption<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfo">*Cluster<wbr>Encryption<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying encryption. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enhanced<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify the desired enhanced MSK CloudWatch monitoring level.  See [Monitoring Amazon MSK with Amazon CloudWatch](https://docs.aws.amazon.com/msk/latest/developerguide/monitoring.html)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kafka<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specify the desired Kafka software version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Number<wbr>Of<wbr>Broker<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The desired total number of broker nodes in the kafka cluster.  It must be a multiple of the number of specified client subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Open<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoring">*Cluster<wbr>Open<wbr>Monitoring</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX and Node monitoring for the MSK cluster. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-"
            title="">Zookeeper<wbr>Connect<wbr>String<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs to use to connect to the Apache Zookeeper cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bootstrap<wbr>Brokers<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs of kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `PLAINTEXT` or `TLS_PLAINTEXT`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bootstrap<wbr>Brokers<wbr>Tls<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more DNS names (or IPs) and TLS port pairs kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `TLS_PLAINTEXT` or `TLS`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">broker<wbr>Node<wbr>Group<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterbrokernodegroupinfo">Cluster<wbr>Broker<wbr>Node<wbr>Group<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the broker nodes of the Kafka cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">client<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthentication">Cluster<wbr>Client<wbr>Authentication?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a client authentication. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the MSK cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterconfigurationinfo">Cluster<wbr>Configuration<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a MSK Configuration to attach to Kafka brokers. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">current<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Current version of the MSK Cluster used for updates, e.g. `K13V1IB3VIYZZH`
* `encryption_info.0.encryption_at_rest_kms_key_arn` - The ARN of the KMS key used for encryption at rest of the broker data volumes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">encryption<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfo">Cluster<wbr>Encryption<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying encryption. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enhanced<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the desired enhanced MSK CloudWatch monitoring level.  See [Monitoring Amazon MSK with Amazon CloudWatch](https://docs.aws.amazon.com/msk/latest/developerguide/monitoring.html)
{{% /md %}}</dd>

    <dt class="property-"
            title="">kafka<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specify the desired Kafka software version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">number<wbr>Of<wbr>Broker<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The desired total number of broker nodes in the kafka cluster.  It must be a multiple of the number of specified client subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">open<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoring">Cluster<wbr>Open<wbr>Monitoring?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX and Node monitoring for the MSK cluster. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-"
            title="">zookeeper<wbr>Connect<wbr>String<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs to use to connect to the Apache Zookeeper cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bootstrap_<wbr>brokers<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs of kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `PLAINTEXT` or `TLS_PLAINTEXT`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bootstrap_<wbr>brokers_<wbr>tls<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more DNS names (or IPs) and TLS port pairs kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `TLS_PLAINTEXT` or `TLS`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">broker_<wbr>node_<wbr>group_<wbr>info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterbrokernodegroupinfo">Dict[Cluster<wbr>Broker<wbr>Node<wbr>Group<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the broker nodes of the Kafka cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">client_<wbr>authentication<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthentication">Dict[Cluster<wbr>Client<wbr>Authentication]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a client authentication. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the MSK cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration_<wbr>info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterconfigurationinfo">Dict[Cluster<wbr>Configuration<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a MSK Configuration to attach to Kafka brokers. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">current_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Current version of the MSK Cluster used for updates, e.g. `K13V1IB3VIYZZH`
* `encryption_info.0.encryption_at_rest_kms_key_arn` - The ARN of the KMS key used for encryption at rest of the broker data volumes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">encryption_<wbr>info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfo">Dict[Cluster<wbr>Encryption<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying encryption. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enhanced_<wbr>monitoring<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify the desired enhanced MSK CloudWatch monitoring level.  See [Monitoring Amazon MSK with Amazon CloudWatch](https://docs.aws.amazon.com/msk/latest/developerguide/monitoring.html)
{{% /md %}}</dd>

    <dt class="property-"
            title="">kafka_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify the desired Kafka software version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">number_<wbr>of_<wbr>broker_<wbr>nodes<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The desired total number of broker nodes in the kafka cluster.  It must be a multiple of the number of specified client subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">open_<wbr>monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoring">Dict[Cluster<wbr>Open<wbr>Monitoring]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX and Node monitoring for the MSK cluster. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-"
            title="">zookeeper_<wbr>connect_<wbr>string<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs to use to connect to the Apache Zookeeper cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Cluster Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/msk/#ClusterState">ClusterState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/msk/#Cluster">Cluster</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>bootstrap_brokers=None<span class="p">, </span>bootstrap_brokers_tls=None<span class="p">, </span>broker_node_group_info=None<span class="p">, </span>client_authentication=None<span class="p">, </span>cluster_name=None<span class="p">, </span>configuration_info=None<span class="p">, </span>current_version=None<span class="p">, </span>encryption_info=None<span class="p">, </span>enhanced_monitoring=None<span class="p">, </span>kafka_version=None<span class="p">, </span>number_of_broker_nodes=None<span class="p">, </span>open_monitoring=None<span class="p">, </span>tags=None<span class="p">, </span>zookeeper_connect_string=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetCluster<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterState">ClusterState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#Cluster">Cluster</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.Cluster.html">Cluster</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterState.html">ClusterState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Cluster resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bootstrap<wbr>Brokers<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs of kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `PLAINTEXT` or `TLS_PLAINTEXT`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bootstrap<wbr>Brokers<wbr>Tls<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more DNS names (or IPs) and TLS port pairs kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `TLS_PLAINTEXT` or `TLS`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Broker<wbr>Node<wbr>Group<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterbrokernodegroupinfo">Cluster<wbr>Broker<wbr>Node<wbr>Group<wbr>Info<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the broker nodes of the Kafka cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthentication">Cluster<wbr>Client<wbr>Authentication<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a client authentication. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the MSK cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterconfigurationinfo">Cluster<wbr>Configuration<wbr>Info<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a MSK Configuration to attach to Kafka brokers. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Current<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Current version of the MSK Cluster used for updates, e.g. `K13V1IB3VIYZZH`
* `encryption_info.0.encryption_at_rest_kms_key_arn` - The ARN of the KMS key used for encryption at rest of the broker data volumes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfo">Cluster<wbr>Encryption<wbr>Info<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying encryption. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enhanced<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the desired enhanced MSK CloudWatch monitoring level.  See [Monitoring Amazon MSK with Amazon CloudWatch](https://docs.aws.amazon.com/msk/latest/developerguide/monitoring.html)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kafka<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the desired Kafka software version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Of<wbr>Broker<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The desired total number of broker nodes in the kafka cluster.  It must be a multiple of the number of specified client subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Open<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoring">Cluster<wbr>Open<wbr>Monitoring<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX and Node monitoring for the MSK cluster. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Zookeeper<wbr>Connect<wbr>String<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs to use to connect to the Apache Zookeeper cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bootstrap<wbr>Brokers<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs of kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `PLAINTEXT` or `TLS_PLAINTEXT`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bootstrap<wbr>Brokers<wbr>Tls<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more DNS names (or IPs) and TLS port pairs kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `TLS_PLAINTEXT` or `TLS`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Broker<wbr>Node<wbr>Group<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterbrokernodegroupinfo">*Cluster<wbr>Broker<wbr>Node<wbr>Group<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the broker nodes of the Kafka cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthentication">*Cluster<wbr>Client<wbr>Authentication</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a client authentication. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the MSK cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterconfigurationinfo">*Cluster<wbr>Configuration<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a MSK Configuration to attach to Kafka brokers. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Current<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Current version of the MSK Cluster used for updates, e.g. `K13V1IB3VIYZZH`
* `encryption_info.0.encryption_at_rest_kms_key_arn` - The ARN of the KMS key used for encryption at rest of the broker data volumes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfo">*Cluster<wbr>Encryption<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying encryption. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enhanced<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify the desired enhanced MSK CloudWatch monitoring level.  See [Monitoring Amazon MSK with Amazon CloudWatch](https://docs.aws.amazon.com/msk/latest/developerguide/monitoring.html)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kafka<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify the desired Kafka software version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Of<wbr>Broker<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The desired total number of broker nodes in the kafka cluster.  It must be a multiple of the number of specified client subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Open<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoring">*Cluster<wbr>Open<wbr>Monitoring</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX and Node monitoring for the MSK cluster. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Zookeeper<wbr>Connect<wbr>String<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs to use to connect to the Apache Zookeeper cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bootstrap<wbr>Brokers<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs of kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `PLAINTEXT` or `TLS_PLAINTEXT`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bootstrap<wbr>Brokers<wbr>Tls<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more DNS names (or IPs) and TLS port pairs kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `TLS_PLAINTEXT` or `TLS`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">broker<wbr>Node<wbr>Group<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterbrokernodegroupinfo">Cluster<wbr>Broker<wbr>Node<wbr>Group<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the broker nodes of the Kafka cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthentication">Cluster<wbr>Client<wbr>Authentication?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a client authentication. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the MSK cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterconfigurationinfo">Cluster<wbr>Configuration<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a MSK Configuration to attach to Kafka brokers. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">current<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Current version of the MSK Cluster used for updates, e.g. `K13V1IB3VIYZZH`
* `encryption_info.0.encryption_at_rest_kms_key_arn` - The ARN of the KMS key used for encryption at rest of the broker data volumes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfo">Cluster<wbr>Encryption<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying encryption. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enhanced<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the desired enhanced MSK CloudWatch monitoring level.  See [Monitoring Amazon MSK with Amazon CloudWatch](https://docs.aws.amazon.com/msk/latest/developerguide/monitoring.html)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kafka<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the desired Kafka software version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number<wbr>Of<wbr>Broker<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The desired total number of broker nodes in the kafka cluster.  It must be a multiple of the number of specified client subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">open<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoring">Cluster<wbr>Open<wbr>Monitoring?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX and Node monitoring for the MSK cluster. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">zookeeper<wbr>Connect<wbr>String<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs to use to connect to the Apache Zookeeper cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bootstrap_<wbr>brokers<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs of kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `PLAINTEXT` or `TLS_PLAINTEXT`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bootstrap_<wbr>brokers_<wbr>tls<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more DNS names (or IPs) and TLS port pairs kafka brokers suitable to boostrap connectivity to the kafka cluster. Only contains value if `client_broker` encryption in transit is set to `TLS_PLAINTEXT` or `TLS`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">broker_<wbr>node_<wbr>group_<wbr>info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterbrokernodegroupinfo">Dict[Cluster<wbr>Broker<wbr>Node<wbr>Group<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the broker nodes of the Kafka cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client_<wbr>authentication<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthentication">Dict[Cluster<wbr>Client<wbr>Authentication]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a client authentication. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the MSK cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration_<wbr>info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterconfigurationinfo">Dict[Cluster<wbr>Configuration<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying a MSK Configuration to attach to Kafka brokers. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">current_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Current version of the MSK Cluster used for updates, e.g. `K13V1IB3VIYZZH`
* `encryption_info.0.encryption_at_rest_kms_key_arn` - The ARN of the KMS key used for encryption at rest of the broker data volumes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption_<wbr>info<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfo">Dict[Cluster<wbr>Encryption<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying encryption. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enhanced_<wbr>monitoring<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify the desired enhanced MSK CloudWatch monitoring level.  See [Monitoring Amazon MSK with Amazon CloudWatch](https://docs.aws.amazon.com/msk/latest/developerguide/monitoring.html)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kafka_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify the desired Kafka software version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number_<wbr>of_<wbr>broker_<wbr>nodes<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The desired total number of broker nodes in the kafka cluster.  It must be a multiple of the number of specified client subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">open_<wbr>monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoring">Dict[Cluster<wbr>Open<wbr>Monitoring]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX and Node monitoring for the MSK cluster. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">zookeeper_<wbr>connect_<wbr>string<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A comma separated list of one or more hostname:port pairs to use to connect to the Apache Zookeeper cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### ClusterBrokerNodeGroupInfo
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClusterBrokerNodeGroupInfo">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClusterBrokerNodeGroupInfo">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterBrokerNodeGroupInfoArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterBrokerNodeGroupInfoOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterBrokerNodeGroupInfoArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterBrokerNodeGroupInfo.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Az<wbr>Distribution<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The distribution of broker nodes across availability zones ([documentation](https://docs.aws.amazon.com/msk/1.0/apireference/clusters.html#clusters-model-brokerazdistribution)). Currently the only valid value is `DEFAULT`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Client<wbr>Subnets<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of subnets to connect to in client VPC ([documentation](https://docs.aws.amazon.com/msk/1.0/apireference/clusters.html#clusters-prop-brokernodegroupinfo-clientsubnets)).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Ebs<wbr>Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size in GiB of the EBS volume for the data drive on each broker node.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specify the instance type to use for the kafka brokers. e.g. kafka.m5.large. ([Pricing info](https://aws.amazon.com/msk/pricing/))
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of the security groups to associate with the elastic network interfaces to control who can communicate with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Az<wbr>Distribution<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The distribution of broker nodes across availability zones ([documentation](https://docs.aws.amazon.com/msk/1.0/apireference/clusters.html#clusters-model-brokerazdistribution)). Currently the only valid value is `DEFAULT`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Client<wbr>Subnets<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of subnets to connect to in client VPC ([documentation](https://docs.aws.amazon.com/msk/1.0/apireference/clusters.html#clusters-prop-brokernodegroupinfo-clientsubnets)).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Ebs<wbr>Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size in GiB of the EBS volume for the data drive on each broker node.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specify the instance type to use for the kafka brokers. e.g. kafka.m5.large. ([Pricing info](https://aws.amazon.com/msk/pricing/))
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of the security groups to associate with the elastic network interfaces to control who can communicate with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">az<wbr>Distribution<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The distribution of broker nodes across availability zones ([documentation](https://docs.aws.amazon.com/msk/1.0/apireference/clusters.html#clusters-model-brokerazdistribution)). Currently the only valid value is `DEFAULT`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">client<wbr>Subnets<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of subnets to connect to in client VPC ([documentation](https://docs.aws.amazon.com/msk/1.0/apireference/clusters.html#clusters-prop-brokernodegroupinfo-clientsubnets)).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">ebs<wbr>Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The size in GiB of the EBS volume for the data drive on each broker node.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specify the instance type to use for the kafka brokers. e.g. kafka.m5.large. ([Pricing info](https://aws.amazon.com/msk/pricing/))
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of the security groups to associate with the elastic network interfaces to control who can communicate with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">az<wbr>Distribution<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The distribution of broker nodes across availability zones ([documentation](https://docs.aws.amazon.com/msk/1.0/apireference/clusters.html#clusters-model-brokerazdistribution)). Currently the only valid value is `DEFAULT`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">client<wbr>Subnets<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of subnets to connect to in client VPC ([documentation](https://docs.aws.amazon.com/msk/1.0/apireference/clusters.html#clusters-prop-brokernodegroupinfo-clientsubnets)).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">ebs<wbr>Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The size in GiB of the EBS volume for the data drive on each broker node.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify the instance type to use for the kafka brokers. e.g. kafka.m5.large. ([Pricing info](https://aws.amazon.com/msk/pricing/))
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of the security groups to associate with the elastic network interfaces to control who can communicate with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ClusterClientAuthentication
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClusterClientAuthentication">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClusterClientAuthentication">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterClientAuthenticationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterClientAuthenticationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterClientAuthenticationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterClientAuthentication.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Tls<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthenticationtls">Cluster<wbr>Client<wbr>Authentication<wbr>Tls<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying TLS client authentication. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Tls<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthenticationtls">*Cluster<wbr>Client<wbr>Authentication<wbr>Tls</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying TLS client authentication. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">tls<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthenticationtls">Cluster<wbr>Client<wbr>Authentication<wbr>Tls?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying TLS client authentication. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">tls<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterclientauthenticationtls">Dict[Cluster<wbr>Client<wbr>Authentication<wbr>Tls]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for specifying TLS client authentication. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ClusterClientAuthenticationTls
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClusterClientAuthenticationTls">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClusterClientAuthenticationTls">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterClientAuthenticationTlsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterClientAuthenticationTlsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterClientAuthenticationTlsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterClientAuthenticationTls.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Authority<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of ACM Certificate Authority Amazon Resource Names (ARNs).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Authority<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of ACM Certificate Authority Amazon Resource Names (ARNs).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">certificate<wbr>Authority<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of ACM Certificate Authority Amazon Resource Names (ARNs).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">certificate<wbr>Authority<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of ACM Certificate Authority Amazon Resource Names (ARNs).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ClusterConfigurationInfo
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClusterConfigurationInfo">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClusterConfigurationInfo">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterConfigurationInfoArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterConfigurationInfoOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterConfigurationInfoArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterConfigurationInfo.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Revision<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Revision of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Revision<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Revision of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">revision<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Revision of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">revision<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Revision of the MSK Configuration to use in the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ClusterEncryptionInfo
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClusterEncryptionInfo">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClusterEncryptionInfo">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterEncryptionInfoArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterEncryptionInfoOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterEncryptionInfoArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterEncryptionInfo.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Encryption<wbr>At<wbr>Rest<wbr>Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}You may specify a KMS key short ID or ARN (it will always output an ARN) to use for encrypting your data at rest.  If no key is specified, an AWS managed KMS (&#39;aws/msk&#39; managed service) key will be used for encrypting the data at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>In<wbr>Transit<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfoencryptionintransit">Cluster<wbr>Encryption<wbr>Info<wbr>Encryption<wbr>In<wbr>Transit<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to specify encryption in transit. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Encryption<wbr>At<wbr>Rest<wbr>Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}You may specify a KMS key short ID or ARN (it will always output an ARN) to use for encrypting your data at rest.  If no key is specified, an AWS managed KMS (&#39;aws/msk&#39; managed service) key will be used for encrypting the data at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>In<wbr>Transit<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfoencryptionintransit">*Cluster<wbr>Encryption<wbr>Info<wbr>Encryption<wbr>In<wbr>Transit</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to specify encryption in transit. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">encryption<wbr>At<wbr>Rest<wbr>Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}You may specify a KMS key short ID or ARN (it will always output an ARN) to use for encrypting your data at rest.  If no key is specified, an AWS managed KMS (&#39;aws/msk&#39; managed service) key will be used for encrypting the data at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption<wbr>In<wbr>Transit<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfoencryptionintransit">Cluster<wbr>Encryption<wbr>Info<wbr>Encryption<wbr>In<wbr>Transit?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to specify encryption in transit. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">encryption<wbr>At<wbr>Rest<wbr>Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}You may specify a KMS key short ID or ARN (it will always output an ARN) to use for encrypting your data at rest.  If no key is specified, an AWS managed KMS (&#39;aws/msk&#39; managed service) key will be used for encrypting the data at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption<wbr>In<wbr>Transit<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterencryptioninfoencryptionintransit">Dict[Cluster<wbr>Encryption<wbr>Info<wbr>Encryption<wbr>In<wbr>Transit]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to specify encryption in transit. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ClusterEncryptionInfoEncryptionInTransit
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClusterEncryptionInfoEncryptionInTransit">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClusterEncryptionInfoEncryptionInTransit">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterEncryptionInfoEncryptionInTransitArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterEncryptionInfoEncryptionInTransitOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterEncryptionInfoEncryptionInTransitArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterEncryptionInfoEncryptionInTransit.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Client<wbr>Broker<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Encryption setting for data in transit between clients and brokers. Valid values: `TLS`, `TLS_PLAINTEXT`, and `PLAINTEXT`. Default value is `TLS_PLAINTEXT` when `encryption_in_transit` block defined, but `TLS` when `encryption_in_transit` block omitted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">In<wbr>Cluster<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether data communication among broker nodes is encrypted. Default value: `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Client<wbr>Broker<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Encryption setting for data in transit between clients and brokers. Valid values: `TLS`, `TLS_PLAINTEXT`, and `PLAINTEXT`. Default value is `TLS_PLAINTEXT` when `encryption_in_transit` block defined, but `TLS` when `encryption_in_transit` block omitted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">In<wbr>Cluster<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether data communication among broker nodes is encrypted. Default value: `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">client<wbr>Broker<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Encryption setting for data in transit between clients and brokers. Valid values: `TLS`, `TLS_PLAINTEXT`, and `PLAINTEXT`. Default value is `TLS_PLAINTEXT` when `encryption_in_transit` block defined, but `TLS` when `encryption_in_transit` block omitted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">in<wbr>Cluster<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether data communication among broker nodes is encrypted. Default value: `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">client<wbr>Broker<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Encryption setting for data in transit between clients and brokers. Valid values: `TLS`, `TLS_PLAINTEXT`, and `PLAINTEXT`. Default value is `TLS_PLAINTEXT` when `encryption_in_transit` block defined, but `TLS` when `encryption_in_transit` block omitted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">in<wbr>Cluster<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether data communication among broker nodes is encrypted. Default value: `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ClusterOpenMonitoring
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClusterOpenMonitoring">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClusterOpenMonitoring">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterOpenMonitoringArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterOpenMonitoringOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterOpenMonitoringArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterOpenMonitoring.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Prometheus<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoringprometheus">Cluster<wbr>Open<wbr>Monitoring<wbr>Prometheus<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for Prometheus settings for open monitoring. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Prometheus<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoringprometheus">Cluster<wbr>Open<wbr>Monitoring<wbr>Prometheus</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for Prometheus settings for open monitoring. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">prometheus<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoringprometheus">Cluster<wbr>Open<wbr>Monitoring<wbr>Prometheus</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for Prometheus settings for open monitoring. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">prometheus<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoringprometheus">Dict[Cluster<wbr>Open<wbr>Monitoring<wbr>Prometheus]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for Prometheus settings for open monitoring. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ClusterOpenMonitoringPrometheus
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClusterOpenMonitoringPrometheus">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClusterOpenMonitoringPrometheus">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterOpenMonitoringPrometheusArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterOpenMonitoringPrometheusOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterOpenMonitoringPrometheusArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterOpenMonitoringPrometheus.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Jmx<wbr>Exporter<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoringprometheusjmxexporter">Cluster<wbr>Open<wbr>Monitoring<wbr>Prometheus<wbr>Jmx<wbr>Exporter<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX Exporter. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Exporter<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoringprometheusnodeexporter">Cluster<wbr>Open<wbr>Monitoring<wbr>Prometheus<wbr>Node<wbr>Exporter<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for Node Exporter. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Jmx<wbr>Exporter<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoringprometheusjmxexporter">*Cluster<wbr>Open<wbr>Monitoring<wbr>Prometheus<wbr>Jmx<wbr>Exporter</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX Exporter. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Exporter<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoringprometheusnodeexporter">*Cluster<wbr>Open<wbr>Monitoring<wbr>Prometheus<wbr>Node<wbr>Exporter</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for Node Exporter. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">jmx<wbr>Exporter<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoringprometheusjmxexporter">Cluster<wbr>Open<wbr>Monitoring<wbr>Prometheus<wbr>Jmx<wbr>Exporter?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX Exporter. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node<wbr>Exporter<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoringprometheusnodeexporter">Cluster<wbr>Open<wbr>Monitoring<wbr>Prometheus<wbr>Node<wbr>Exporter?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for Node Exporter. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">jmx<wbr>Exporter<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoringprometheusjmxexporter">Dict[Cluster<wbr>Open<wbr>Monitoring<wbr>Prometheus<wbr>Jmx<wbr>Exporter]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for JMX Exporter. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node<wbr>Exporter<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusteropenmonitoringprometheusnodeexporter">Dict[Cluster<wbr>Open<wbr>Monitoring<wbr>Prometheus<wbr>Node<wbr>Exporter]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for Node Exporter. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ClusterOpenMonitoringPrometheusJmxExporter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClusterOpenMonitoringPrometheusJmxExporter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClusterOpenMonitoringPrometheusJmxExporter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterOpenMonitoringPrometheusJmxExporterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterOpenMonitoringPrometheusJmxExporterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterOpenMonitoringPrometheusJmxExporterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterOpenMonitoringPrometheusJmxExporter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<wbr>In<wbr>Broker<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to enable or disable the Node Exporter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<wbr>In<wbr>Broker<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to enable or disable the Node Exporter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<wbr>In<wbr>Broker<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to enable or disable the Node Exporter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<wbr>In<wbr>Broker<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to enable or disable the Node Exporter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ClusterOpenMonitoringPrometheusNodeExporter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClusterOpenMonitoringPrometheusNodeExporter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClusterOpenMonitoringPrometheusNodeExporter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterOpenMonitoringPrometheusNodeExporterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/msk?tab=doc#ClusterOpenMonitoringPrometheusNodeExporterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterOpenMonitoringPrometheusNodeExporterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Msk.ClusterOpenMonitoringPrometheusNodeExporter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<wbr>In<wbr>Broker<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to enable or disable the Node Exporter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<wbr>In<wbr>Broker<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to enable or disable the Node Exporter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<wbr>In<wbr>Broker<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to enable or disable the Node Exporter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<wbr>In<wbr>Broker<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to enable or disable the Node Exporter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








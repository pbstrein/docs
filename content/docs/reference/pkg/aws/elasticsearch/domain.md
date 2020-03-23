
---
title: "Domain"
block_external_search_index: true
---

Manages an AWS Elasticsearch Domain.

## Example Usage

### Basic Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.elasticsearch.Domain("example", {
    clusterConfig: {
        instanceType: "r4.large.elasticsearch",
    },
    elasticsearchVersion: "1.5",
    snapshotOptions: {
        automatedSnapshotStartHour: 23,
    },
    tags: {
        Domain: "TestDomain",
    },
});
```

### Access Policy

> See also: [`aws.elasticsearch.DomainPolicy` resource](https://www.terraform.io/docs/providers/aws/r/elasticsearch_domain_policy.html)

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const config = new pulumi.Config();
const domain = config.get("domain") || "tf-test";

const currentRegion = aws.getRegion();
const currentCallerIdentity = aws.getCallerIdentity();
const example = new aws.elasticsearch.Domain("example", {
    accessPolicies: `{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": "es:*",
      "Principal": "*",
      "Effect": "Allow",
      "Resource": "arn:aws:es:${currentRegion.name!}:${currentCallerIdentity.accountId}:domain/${domain}/*",
      "Condition": {
        "IpAddress": {"aws:SourceIp": ["66.193.100.22/32"]}
      }
    }
  ]
}
`,
});
```

### Log Publishing to CloudWatch Logs

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleLogGroup = new aws.cloudwatch.LogGroup("example", {});
const exampleLogResourcePolicy = new aws.cloudwatch.LogResourcePolicy("example", {
    policyDocument: `{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "es.amazonaws.com"
      },
      "Action": [
        "logs:PutLogEvents",
        "logs:PutLogEventsBatch",
        "logs:CreateLogStream"
      ],
      "Resource": "arn:aws:logs:*"
    }
  ]
}
`,
    policyName: "example",
});
const exampleDomain = new aws.elasticsearch.Domain("example", {
    logPublishingOptions: [{
        cloudwatchLogGroupArn: exampleLogGroup.arn,
        logType: "INDEX_SLOW_LOGS",
    }],
});
```

### VPC based ES

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const config = new pulumi.Config();
const vpc = config.require("vpc");
const domain = config.get("domain") || "tf-test";

const selectedVpc = aws.ec2.getVpc({
    tags: {
        Name: vpc,
    },
});
const selectedSubnetIds = aws.ec2.getSubnetIds({
    tags: {
        Tier: "private",
    },
    vpcId: selectedVpc.id!,
});
const currentRegion = aws.getRegion();
const currentCallerIdentity = aws.getCallerIdentity();
const esSecurityGroup = new aws.ec2.SecurityGroup("es", {
    description: "Managed by Pulumi",
    ingress: [{
        cidrBlocks: [selectedVpc.cidrBlock!],
        fromPort: 443,
        protocol: "tcp",
        toPort: 443,
    }],
    vpcId: selectedVpc.id!,
});
const esServiceLinkedRole = new aws.iam.ServiceLinkedRole("es", {
    awsServiceName: "es.amazonaws.com",
});
const esDomain = new aws.elasticsearch.Domain("es", {
    accessPolicies: `{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Action": "es:*",
			"Principal": "*",
			"Effect": "Allow",
			"Resource": "arn:aws:es:${currentRegion.name!}:${currentCallerIdentity.accountId}:domain/${domain}/*"
		}
	]
}
`,
    advancedOptions: {
        "rest.action.multi.allow_explicit_index": "true",
    },
    clusterConfig: {
        instanceType: "m4.large.elasticsearch",
    },
    elasticsearchVersion: "6.3",
    snapshotOptions: {
        automatedSnapshotStartHour: 23,
    },
    tags: {
        Domain: "TestDomain",
    },
    vpcOptions: {
        securityGroupIds: [aws_security_group_elasticsearch.id],
        subnetIds: [
            selectedSubnetIds.ids[0],
            selectedSubnetIds.ids[1],
        ],
    },
}, {dependsOn: [esServiceLinkedRole]});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/elasticsearch_domain.html.markdown.



## Create a Domain Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticsearch/#Domain">Domain</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticsearch/#DomainArgs">DomainArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Domain</span><span class="p">(resource_name, opts=None, </span>access_policies=None<span class="p">, </span>advanced_options=None<span class="p">, </span>cluster_config=None<span class="p">, </span>cognito_options=None<span class="p">, </span>domain_endpoint_options=None<span class="p">, </span>domain_name=None<span class="p">, </span>ebs_options=None<span class="p">, </span>elasticsearch_version=None<span class="p">, </span>encrypt_at_rest=None<span class="p">, </span>log_publishing_options=None<span class="p">, </span>node_to_node_encryption=None<span class="p">, </span>snapshot_options=None<span class="p">, </span>tags=None<span class="p">, </span>vpc_options=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDomain<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainArgs">DomainArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#Domain">Domain</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.Domain.html">Domain</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainArgs.html">DomainArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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

    <dt class="property-optional"
            title="Optional">Access<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM policy document specifying the access policies for the domain
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Advanced<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
Note that the values for these configuration options must be strings (wrapped in quotes) or they
may be wrong and cause a perpetual diff, causing this provider to want to recreate your Elasticsearch
domain on every apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfig">Domain<wbr>Cluster<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cognito<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaincognitooptions">Domain<wbr>Cognito<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Endpoint<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaindomainendpointoptions">Domain<wbr>Domain<wbr>Endpoint<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Domain endpoint HTTP(S) related options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainebsoptions">Domain<wbr>Ebs<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}EBS related options, may be required based on chosen [instance size](https://aws.amazon.com/elasticsearch-service/pricing/). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elasticsearch<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of Elasticsearch to deploy. Defaults to `1.5`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypt<wbr>At<wbr>Rest<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainencryptatrest">Domain<wbr>Encrypt<wbr>At<wbr>Rest<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options. Only available for [certain instance types](http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/aes-supported-instance-types.html). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Publishing<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainlogpublishingoption">List&lt;Domain<wbr>Log<wbr>Publishing<wbr>Option<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Options for publishing slow logs to CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>To<wbr>Node<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainnodetonodeencryption">Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Node-to-node encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainsnapshotoptions">Domain<wbr>Snapshot<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Snapshot related options, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainvpcoptions">Domain<wbr>Vpc<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}VPC related options, see below. Adding or removing this configuration forces a new resource ([documentation](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-vpc.html#es-vpc-limitations)).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Access<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}IAM policy document specifying the access policies for the domain
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Advanced<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
Note that the values for these configuration options must be strings (wrapped in quotes) or they
may be wrong and cause a perpetual diff, causing this provider to want to recreate your Elasticsearch
domain on every apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfig">*Domain<wbr>Cluster<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cognito<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaincognitooptions">*Domain<wbr>Cognito<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Endpoint<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaindomainendpointoptions">*Domain<wbr>Domain<wbr>Endpoint<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}Domain endpoint HTTP(S) related options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainebsoptions">*Domain<wbr>Ebs<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}EBS related options, may be required based on chosen [instance size](https://aws.amazon.com/elasticsearch-service/pricing/). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elasticsearch<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version of Elasticsearch to deploy. Defaults to `1.5`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypt<wbr>At<wbr>Rest<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainencryptatrest">*Domain<wbr>Encrypt<wbr>At<wbr>Rest</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options. Only available for [certain instance types](http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/aes-supported-instance-types.html). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Publishing<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainlogpublishingoption">[]Domain<wbr>Log<wbr>Publishing<wbr>Option</a></span>
    </dt>
    <dd>{{% md %}}Options for publishing slow logs to CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>To<wbr>Node<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainnodetonodeencryption">*Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption</a></span>
    </dt>
    <dd>{{% md %}}Node-to-node encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainsnapshotoptions">*Domain<wbr>Snapshot<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}Snapshot related options, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainvpcoptions">*Domain<wbr>Vpc<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}VPC related options, see below. Adding or removing this configuration forces a new resource ([documentation](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-vpc.html#es-vpc-limitations)).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type">string | PolicyDocument</span>
    </dt>
    <dd>{{% md %}}IAM policy document specifying the access policies for the domain
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">advanced<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
Note that the values for these configuration options must be strings (wrapped in quotes) or they
may be wrong and cause a perpetual diff, causing this provider to want to recreate your Elasticsearch
domain on every apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfig">Domain<wbr>Cluster<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cognito<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaincognitooptions">Domain<wbr>Cognito<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain<wbr>Endpoint<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaindomainendpointoptions">Domain<wbr>Domain<wbr>Endpoint<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}Domain endpoint HTTP(S) related options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainebsoptions">Domain<wbr>Ebs<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}EBS related options, may be required based on chosen [instance size](https://aws.amazon.com/elasticsearch-service/pricing/). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elasticsearch<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of Elasticsearch to deploy. Defaults to `1.5`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypt<wbr>At<wbr>Rest<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainencryptatrest">Domain<wbr>Encrypt<wbr>At<wbr>Rest?</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options. Only available for [certain instance types](http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/aes-supported-instance-types.html). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log<wbr>Publishing<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainlogpublishingoption">Domain<wbr>Log<wbr>Publishing<wbr>Option[]?</a></span>
    </dt>
    <dd>{{% md %}}Options for publishing slow logs to CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node<wbr>To<wbr>Node<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainnodetonodeencryption">Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption?</a></span>
    </dt>
    <dd>{{% md %}}Node-to-node encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainsnapshotoptions">Domain<wbr>Snapshot<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}Snapshot related options, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainvpcoptions">Domain<wbr>Vpc<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}VPC related options, see below. Adding or removing this configuration forces a new resource ([documentation](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-vpc.html#es-vpc-limitations)).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access_<wbr>policies<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}IAM policy document specifying the access policies for the domain
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">advanced_<wbr>options<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
Note that the values for these configuration options must be strings (wrapped in quotes) or they
may be wrong and cause a perpetual diff, causing this provider to want to recreate your Elasticsearch
domain on every apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfig">Dict[Domain<wbr>Cluster<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cognito_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaincognitooptions">Dict[Domain<wbr>Cognito<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain_<wbr>endpoint_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaindomainendpointoptions">Dict[Domain<wbr>Domain<wbr>Endpoint<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}Domain endpoint HTTP(S) related options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainebsoptions">Dict[Domain<wbr>Ebs<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}EBS related options, may be required based on chosen [instance size](https://aws.amazon.com/elasticsearch-service/pricing/). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elasticsearch_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of Elasticsearch to deploy. Defaults to `1.5`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypt_<wbr>at_<wbr>rest<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainencryptatrest">Dict[Domain<wbr>Encrypt<wbr>At<wbr>Rest]</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options. Only available for [certain instance types](http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/aes-supported-instance-types.html). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log_<wbr>publishing_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainlogpublishingoption">List[Domain<wbr>Log<wbr>Publishing<wbr>Option]</a></span>
    </dt>
    <dd>{{% md %}}Options for publishing slow logs to CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node_<wbr>to_<wbr>node_<wbr>encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainnodetonodeencryption">Dict[Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption]</a></span>
    </dt>
    <dd>{{% md %}}Node-to-node encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainsnapshotoptions">Dict[Domain<wbr>Snapshot<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}Snapshot related options, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainvpcoptions">Dict[Domain<wbr>Vpc<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}VPC related options, see below. Adding or removing this configuration forces a new resource ([documentation](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-vpc.html#es-vpc-limitations)).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Domain Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Access<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}IAM policy document specifying the access policies for the domain
{{% /md %}}</dd>

    <dt class="property-"
            title="">Advanced<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
Note that the values for these configuration options must be strings (wrapped in quotes) or they
may be wrong and cause a perpetual diff, causing this provider to want to recreate your Elasticsearch
domain on every apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfig">Domain<wbr>Cluster<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain, see below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cognito<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaincognitooptions">Domain<wbr>Cognito<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Domain<wbr>Endpoint<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaindomainendpointoptions">Domain<wbr>Domain<wbr>Endpoint<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}Domain endpoint HTTP(S) related options. See below.
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
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainebsoptions">Domain<wbr>Ebs<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}EBS related options, may be required based on chosen [instance size](https://aws.amazon.com/elasticsearch-service/pricing/). See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elasticsearch<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of Elasticsearch to deploy. Defaults to `1.5`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encrypt<wbr>At<wbr>Rest<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainencryptatrest">Domain<wbr>Encrypt<wbr>At<wbr>Rest</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options. Only available for [certain instance types](http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/aes-supported-instance-types.html). See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to submit index, search, and data upload requests.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kibana<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint for kibana without https scheme.
* `vpc_options.0.availability_zones` - If the domain was created inside a VPC, the names of the availability zones the configured `subnet_ids` were created inside.
* `vpc_options.0.vpc_id` - If the domain was created inside a VPC, the ID of the VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Log<wbr>Publishing<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainlogpublishingoption">List&lt;Domain<wbr>Log<wbr>Publishing<wbr>Option&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Options for publishing slow logs to CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>To<wbr>Node<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainnodetonodeencryption">Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption</a></span>
    </dt>
    <dd>{{% md %}}Node-to-node encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainsnapshotoptions">Domain<wbr>Snapshot<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}Snapshot related options, see below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainvpcoptions">Domain<wbr>Vpc<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}VPC related options, see below. Adding or removing this configuration forces a new resource ([documentation](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-vpc.html#es-vpc-limitations)).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Access<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}IAM policy document specifying the access policies for the domain
{{% /md %}}</dd>

    <dt class="property-"
            title="">Advanced<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
Note that the values for these configuration options must be strings (wrapped in quotes) or they
may be wrong and cause a perpetual diff, causing this provider to want to recreate your Elasticsearch
domain on every apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfig">Domain<wbr>Cluster<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain, see below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cognito<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaincognitooptions">*Domain<wbr>Cognito<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Domain<wbr>Endpoint<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaindomainendpointoptions">Domain<wbr>Domain<wbr>Endpoint<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}Domain endpoint HTTP(S) related options. See below.
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
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainebsoptions">Domain<wbr>Ebs<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}EBS related options, may be required based on chosen [instance size](https://aws.amazon.com/elasticsearch-service/pricing/). See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elasticsearch<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version of Elasticsearch to deploy. Defaults to `1.5`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encrypt<wbr>At<wbr>Rest<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainencryptatrest">Domain<wbr>Encrypt<wbr>At<wbr>Rest</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options. Only available for [certain instance types](http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/aes-supported-instance-types.html). See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to submit index, search, and data upload requests.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kibana<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint for kibana without https scheme.
* `vpc_options.0.availability_zones` - If the domain was created inside a VPC, the names of the availability zones the configured `subnet_ids` were created inside.
* `vpc_options.0.vpc_id` - If the domain was created inside a VPC, the ID of the VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Log<wbr>Publishing<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainlogpublishingoption">[]Domain<wbr>Log<wbr>Publishing<wbr>Option</a></span>
    </dt>
    <dd>{{% md %}}Options for publishing slow logs to CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>To<wbr>Node<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainnodetonodeencryption">Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption</a></span>
    </dt>
    <dd>{{% md %}}Node-to-node encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainsnapshotoptions">*Domain<wbr>Snapshot<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}Snapshot related options, see below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainvpcoptions">*Domain<wbr>Vpc<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}VPC related options, see below. Adding or removing this configuration forces a new resource ([documentation](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-vpc.html#es-vpc-limitations)).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">access<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}IAM policy document specifying the access policies for the domain
{{% /md %}}</dd>

    <dt class="property-"
            title="">advanced<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
Note that the values for these configuration options must be strings (wrapped in quotes) or they
may be wrong and cause a perpetual diff, causing this provider to want to recreate your Elasticsearch
domain on every apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfig">Domain<wbr>Cluster<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain, see below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cognito<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaincognitooptions">Domain<wbr>Cognito<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">domain<wbr>Endpoint<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaindomainendpointoptions">Domain<wbr>Domain<wbr>Endpoint<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}Domain endpoint HTTP(S) related options. See below.
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
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainebsoptions">Domain<wbr>Ebs<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}EBS related options, may be required based on chosen [instance size](https://aws.amazon.com/elasticsearch-service/pricing/). See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">elasticsearch<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of Elasticsearch to deploy. Defaults to `1.5`
{{% /md %}}</dd>

    <dt class="property-"
            title="">encrypt<wbr>At<wbr>Rest<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainencryptatrest">Domain<wbr>Encrypt<wbr>At<wbr>Rest</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options. Only available for [certain instance types](http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/aes-supported-instance-types.html). See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to submit index, search, and data upload requests.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kibana<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint for kibana without https scheme.
* `vpc_options.0.availability_zones` - If the domain was created inside a VPC, the names of the availability zones the configured `subnet_ids` were created inside.
* `vpc_options.0.vpc_id` - If the domain was created inside a VPC, the ID of the VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">log<wbr>Publishing<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainlogpublishingoption">Domain<wbr>Log<wbr>Publishing<wbr>Option[]?</a></span>
    </dt>
    <dd>{{% md %}}Options for publishing slow logs to CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">node<wbr>To<wbr>Node<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainnodetonodeencryption">Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption</a></span>
    </dt>
    <dd>{{% md %}}Node-to-node encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainsnapshotoptions">Domain<wbr>Snapshot<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}Snapshot related options, see below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainvpcoptions">Domain<wbr>Vpc<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}VPC related options, see below. Adding or removing this configuration forces a new resource ([documentation](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-vpc.html#es-vpc-limitations)).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">access_<wbr>policies<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM policy document specifying the access policies for the domain
{{% /md %}}</dd>

    <dt class="property-"
            title="">advanced_<wbr>options<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
Note that the values for these configuration options must be strings (wrapped in quotes) or they
may be wrong and cause a perpetual diff, causing this provider to want to recreate your Elasticsearch
domain on every apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfig">Dict[Domain<wbr>Cluster<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain, see below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cognito_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaincognitooptions">Dict[Domain<wbr>Cognito<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">domain_<wbr>endpoint_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaindomainendpointoptions">Dict[Domain<wbr>Domain<wbr>Endpoint<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}Domain endpoint HTTP(S) related options. See below.
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
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainebsoptions">Dict[Domain<wbr>Ebs<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}EBS related options, may be required based on chosen [instance size](https://aws.amazon.com/elasticsearch-service/pricing/). See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">elasticsearch_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of Elasticsearch to deploy. Defaults to `1.5`
{{% /md %}}</dd>

    <dt class="property-"
            title="">encrypt_<wbr>at_<wbr>rest<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainencryptatrest">Dict[Domain<wbr>Encrypt<wbr>At<wbr>Rest]</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options. Only available for [certain instance types](http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/aes-supported-instance-types.html). See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to submit index, search, and data upload requests.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kibana_<wbr>endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint for kibana without https scheme.
* `vpc_options.0.availability_zones` - If the domain was created inside a VPC, the names of the availability zones the configured `subnet_ids` were created inside.
* `vpc_options.0.vpc_id` - If the domain was created inside a VPC, the ID of the VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">log_<wbr>publishing_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainlogpublishingoption">List[Domain<wbr>Log<wbr>Publishing<wbr>Option]</a></span>
    </dt>
    <dd>{{% md %}}Options for publishing slow logs to CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">node_<wbr>to_<wbr>node_<wbr>encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainnodetonodeencryption">Dict[Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption]</a></span>
    </dt>
    <dd>{{% md %}}Node-to-node encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainsnapshotoptions">Dict[Domain<wbr>Snapshot<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}Snapshot related options, see below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainvpcoptions">Dict[Domain<wbr>Vpc<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}VPC related options, see below. Adding or removing this configuration forces a new resource ([documentation](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-vpc.html#es-vpc-limitations)).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Domain Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticsearch/#DomainState">DomainState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticsearch/#Domain">Domain</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>access_policies=None<span class="p">, </span>advanced_options=None<span class="p">, </span>arn=None<span class="p">, </span>cluster_config=None<span class="p">, </span>cognito_options=None<span class="p">, </span>domain_endpoint_options=None<span class="p">, </span>domain_id=None<span class="p">, </span>domain_name=None<span class="p">, </span>ebs_options=None<span class="p">, </span>elasticsearch_version=None<span class="p">, </span>encrypt_at_rest=None<span class="p">, </span>endpoint=None<span class="p">, </span>kibana_endpoint=None<span class="p">, </span>log_publishing_options=None<span class="p">, </span>node_to_node_encryption=None<span class="p">, </span>snapshot_options=None<span class="p">, </span>tags=None<span class="p">, </span>vpc_options=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDomain<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainState">DomainState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#Domain">Domain</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.Domain.html">Domain</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainState.html">DomainState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Domain resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Access<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM policy document specifying the access policies for the domain
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Advanced<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
Note that the values for these configuration options must be strings (wrapped in quotes) or they
may be wrong and cause a perpetual diff, causing this provider to want to recreate your Elasticsearch
domain on every apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfig">Domain<wbr>Cluster<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cognito<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaincognitooptions">Domain<wbr>Cognito<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Endpoint<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaindomainendpointoptions">Domain<wbr>Domain<wbr>Endpoint<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Domain endpoint HTTP(S) related options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Unique identifier for the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainebsoptions">Domain<wbr>Ebs<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}EBS related options, may be required based on chosen [instance size](https://aws.amazon.com/elasticsearch-service/pricing/). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elasticsearch<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of Elasticsearch to deploy. Defaults to `1.5`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypt<wbr>At<wbr>Rest<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainencryptatrest">Domain<wbr>Encrypt<wbr>At<wbr>Rest<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options. Only available for [certain instance types](http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/aes-supported-instance-types.html). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to submit index, search, and data upload requests.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kibana<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint for kibana without https scheme.
* `vpc_options.0.availability_zones` - If the domain was created inside a VPC, the names of the availability zones the configured `subnet_ids` were created inside.
* `vpc_options.0.vpc_id` - If the domain was created inside a VPC, the ID of the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Publishing<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainlogpublishingoption">List&lt;Domain<wbr>Log<wbr>Publishing<wbr>Option<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Options for publishing slow logs to CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>To<wbr>Node<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainnodetonodeencryption">Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Node-to-node encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainsnapshotoptions">Domain<wbr>Snapshot<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Snapshot related options, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainvpcoptions">Domain<wbr>Vpc<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}VPC related options, see below. Adding or removing this configuration forces a new resource ([documentation](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-vpc.html#es-vpc-limitations)).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Access<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}IAM policy document specifying the access policies for the domain
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Advanced<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
Note that the values for these configuration options must be strings (wrapped in quotes) or they
may be wrong and cause a perpetual diff, causing this provider to want to recreate your Elasticsearch
domain on every apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfig">*Domain<wbr>Cluster<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cognito<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaincognitooptions">*Domain<wbr>Cognito<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Endpoint<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaindomainendpointoptions">*Domain<wbr>Domain<wbr>Endpoint<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}Domain endpoint HTTP(S) related options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Unique identifier for the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainebsoptions">*Domain<wbr>Ebs<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}EBS related options, may be required based on chosen [instance size](https://aws.amazon.com/elasticsearch-service/pricing/). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elasticsearch<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version of Elasticsearch to deploy. Defaults to `1.5`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypt<wbr>At<wbr>Rest<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainencryptatrest">*Domain<wbr>Encrypt<wbr>At<wbr>Rest</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options. Only available for [certain instance types](http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/aes-supported-instance-types.html). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to submit index, search, and data upload requests.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kibana<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint for kibana without https scheme.
* `vpc_options.0.availability_zones` - If the domain was created inside a VPC, the names of the availability zones the configured `subnet_ids` were created inside.
* `vpc_options.0.vpc_id` - If the domain was created inside a VPC, the ID of the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Publishing<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainlogpublishingoption">[]Domain<wbr>Log<wbr>Publishing<wbr>Option</a></span>
    </dt>
    <dd>{{% md %}}Options for publishing slow logs to CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>To<wbr>Node<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainnodetonodeencryption">*Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption</a></span>
    </dt>
    <dd>{{% md %}}Node-to-node encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainsnapshotoptions">*Domain<wbr>Snapshot<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}Snapshot related options, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainvpcoptions">*Domain<wbr>Vpc<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}VPC related options, see below. Adding or removing this configuration forces a new resource ([documentation](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-vpc.html#es-vpc-limitations)).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type">string | PolicyDocument</span>
    </dt>
    <dd>{{% md %}}IAM policy document specifying the access policies for the domain
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">advanced<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
Note that the values for these configuration options must be strings (wrapped in quotes) or they
may be wrong and cause a perpetual diff, causing this provider to want to recreate your Elasticsearch
domain on every apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfig">Domain<wbr>Cluster<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cognito<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaincognitooptions">Domain<wbr>Cognito<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain<wbr>Endpoint<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaindomainendpointoptions">Domain<wbr>Domain<wbr>Endpoint<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}Domain endpoint HTTP(S) related options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Unique identifier for the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainebsoptions">Domain<wbr>Ebs<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}EBS related options, may be required based on chosen [instance size](https://aws.amazon.com/elasticsearch-service/pricing/). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elasticsearch<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of Elasticsearch to deploy. Defaults to `1.5`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypt<wbr>At<wbr>Rest<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainencryptatrest">Domain<wbr>Encrypt<wbr>At<wbr>Rest?</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options. Only available for [certain instance types](http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/aes-supported-instance-types.html). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to submit index, search, and data upload requests.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kibana<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint for kibana without https scheme.
* `vpc_options.0.availability_zones` - If the domain was created inside a VPC, the names of the availability zones the configured `subnet_ids` were created inside.
* `vpc_options.0.vpc_id` - If the domain was created inside a VPC, the ID of the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log<wbr>Publishing<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainlogpublishingoption">Domain<wbr>Log<wbr>Publishing<wbr>Option[]?</a></span>
    </dt>
    <dd>{{% md %}}Options for publishing slow logs to CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node<wbr>To<wbr>Node<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainnodetonodeencryption">Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption?</a></span>
    </dt>
    <dd>{{% md %}}Node-to-node encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainsnapshotoptions">Domain<wbr>Snapshot<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}Snapshot related options, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainvpcoptions">Domain<wbr>Vpc<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}VPC related options, see below. Adding or removing this configuration forces a new resource ([documentation](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-vpc.html#es-vpc-limitations)).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access_<wbr>policies<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}IAM policy document specifying the access policies for the domain
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">advanced_<wbr>options<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value string pairs to specify advanced configuration options.
Note that the values for these configuration options must be strings (wrapped in quotes) or they
may be wrong and cause a perpetual diff, causing this provider to want to recreate your Elasticsearch
domain on every apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfig">Dict[Domain<wbr>Cluster<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Cluster configuration of the domain, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cognito_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaincognitooptions">Dict[Domain<wbr>Cognito<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain_<wbr>endpoint_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domaindomainendpointoptions">Dict[Domain<wbr>Domain<wbr>Endpoint<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}Domain endpoint HTTP(S) related options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Unique identifier for the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainebsoptions">Dict[Domain<wbr>Ebs<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}EBS related options, may be required based on chosen [instance size](https://aws.amazon.com/elasticsearch-service/pricing/). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elasticsearch_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of Elasticsearch to deploy. Defaults to `1.5`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypt_<wbr>at_<wbr>rest<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainencryptatrest">Dict[Domain<wbr>Encrypt<wbr>At<wbr>Rest]</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options. Only available for [certain instance types](http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/aes-supported-instance-types.html). See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint used to submit index, search, and data upload requests.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kibana_<wbr>endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Domain-specific endpoint for kibana without https scheme.
* `vpc_options.0.availability_zones` - If the domain was created inside a VPC, the names of the availability zones the configured `subnet_ids` were created inside.
* `vpc_options.0.vpc_id` - If the domain was created inside a VPC, the ID of the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log_<wbr>publishing_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainlogpublishingoption">List[Domain<wbr>Log<wbr>Publishing<wbr>Option]</a></span>
    </dt>
    <dd>{{% md %}}Options for publishing slow logs to CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node_<wbr>to_<wbr>node_<wbr>encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainnodetonodeencryption">Dict[Domain<wbr>Node<wbr>To<wbr>Node<wbr>Encryption]</a></span>
    </dt>
    <dd>{{% md %}}Node-to-node encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainsnapshotoptions">Dict[Domain<wbr>Snapshot<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}Snapshot related options, see below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainvpcoptions">Dict[Domain<wbr>Vpc<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}VPC related options, see below. Adding or removing this configuration forces a new resource ([documentation](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-vpc.html#es-vpc-limitations)).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### DomainClusterConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DomainClusterConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DomainClusterConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainClusterConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainClusterConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainClusterConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainClusterConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Dedicated<wbr>Master<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Number of dedicated master nodes in the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dedicated<wbr>Master<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether dedicated master nodes are enabled for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dedicated<wbr>Master<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Instance type of the dedicated master nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Number of instances in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Instance type of data nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Zone<wbr>Awareness<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfigzoneawarenessconfig">Domain<wbr>Cluster<wbr>Config<wbr>Zone<wbr>Awareness<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing zone awareness settings. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Zone<wbr>Awareness<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether zone awareness is enabled. To enable awareness with three Availability Zones, the `availability_zone_count` within the `zone_awareness_config` must be set to `3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Dedicated<wbr>Master<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Number of dedicated master nodes in the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dedicated<wbr>Master<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether dedicated master nodes are enabled for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dedicated<wbr>Master<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Instance type of the dedicated master nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Number of instances in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Instance type of data nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Zone<wbr>Awareness<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfigzoneawarenessconfig">*Domain<wbr>Cluster<wbr>Config<wbr>Zone<wbr>Awareness<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing zone awareness settings. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Zone<wbr>Awareness<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether zone awareness is enabled. To enable awareness with three Availability Zones, the `availability_zone_count` within the `zone_awareness_config` must be set to `3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">dedicated<wbr>Master<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Number of dedicated master nodes in the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dedicated<wbr>Master<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether dedicated master nodes are enabled for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dedicated<wbr>Master<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Instance type of the dedicated master nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Number of instances in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Instance type of data nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">zone<wbr>Awareness<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfigzoneawarenessconfig">Domain<wbr>Cluster<wbr>Config<wbr>Zone<wbr>Awareness<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing zone awareness settings. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">zone<wbr>Awareness<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether zone awareness is enabled. To enable awareness with three Availability Zones, the `availability_zone_count` within the `zone_awareness_config` must be set to `3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">dedicated<wbr>Master<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Number of dedicated master nodes in the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dedicated<wbr>Master<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether dedicated master nodes are enabled for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dedicated<wbr>Master<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Instance type of the dedicated master nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Number of instances in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Instance type of data nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">zone<wbr>Awareness<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#domainclusterconfigzoneawarenessconfig">Dict[Domain<wbr>Cluster<wbr>Config<wbr>Zone<wbr>Awareness<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing zone awareness settings. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">zone<wbr>Awareness<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether zone awareness is enabled. To enable awareness with three Availability Zones, the `availability_zone_count` within the `zone_awareness_config` must be set to `3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DomainClusterConfigZoneAwarenessConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DomainClusterConfigZoneAwarenessConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DomainClusterConfigZoneAwarenessConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainClusterConfigZoneAwarenessConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainClusterConfigZoneAwarenessConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainClusterConfigZoneAwarenessConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainClusterConfigZoneAwarenessConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Number of Availability Zones for the domain to use with `zone_awareness_enabled`. Defaults to `2`. Valid values: `2` or `3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Number of Availability Zones for the domain to use with `zone_awareness_enabled`. Defaults to `2`. Valid values: `2` or `3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">availability<wbr>Zone<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Number of Availability Zones for the domain to use with `zone_awareness_enabled`. Defaults to `2`. Valid values: `2` or `3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">availability<wbr>Zone<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Number of Availability Zones for the domain to use with `zone_awareness_enabled`. Defaults to `2`. Valid values: `2` or `3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DomainCognitoOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DomainCognitoOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DomainCognitoOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainCognitoOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainCognitoOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainCognitoOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainCognitoOptions.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Identity<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the Cognito Identity Pool to use
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that has the AmazonESCognitoAccess policy attached
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the Cognito User Pool to use
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Identity<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the Cognito Identity Pool to use
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that has the AmazonESCognitoAccess policy attached
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the Cognito User Pool to use
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">identity<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the Cognito Identity Pool to use
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that has the AmazonESCognitoAccess policy attached
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the Cognito User Pool to use
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">identity_<wbr>pool_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ID of the Cognito Identity Pool to use
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that has the AmazonESCognitoAccess policy attached
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user_<wbr>pool_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ID of the Cognito User Pool to use
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DomainDomainEndpointOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DomainDomainEndpointOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DomainDomainEndpointOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainDomainEndpointOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainDomainEndpointOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainDomainEndpointOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainDomainEndpointOptions.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enforce<wbr>Https<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether or not to require HTTPS
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tls<wbr>Security<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enforce<wbr>Https<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether or not to require HTTPS
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tls<wbr>Security<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enforce<wbr>Https<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether or not to require HTTPS
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tls<wbr>Security<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enforce<wbr>Https<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether or not to require HTTPS
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tls<wbr>Security<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DomainEbsOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DomainEbsOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DomainEbsOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainEbsOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainEbsOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainEbsOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainEbsOptions.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Ebs<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether EBS volumes are attached to data nodes in the domain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The baseline input/output (I/O) performance of EBS volumes
attached to data nodes. Applicable only for the Provisioned IOPS EBS volume type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The size of EBS volumes attached to data nodes (in GB).
**Required** if `ebs_enabled` is set to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
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

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The baseline input/output (I/O) performance of EBS volumes
attached to data nodes. Applicable only for the Provisioned IOPS EBS volume type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The size of EBS volumes attached to data nodes (in GB).
**Required** if `ebs_enabled` is set to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
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

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The baseline input/output (I/O) performance of EBS volumes
attached to data nodes. Applicable only for the Provisioned IOPS EBS volume type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The size of EBS volumes attached to data nodes (in GB).
**Required** if `ebs_enabled` is set to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
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

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The baseline input/output (I/O) performance of EBS volumes
attached to data nodes. Applicable only for the Provisioned IOPS EBS volume type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The size of EBS volumes attached to data nodes (in GB).
**Required** if `ebs_enabled` is set to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of EBS volumes attached to data nodes.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DomainEncryptAtRest
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DomainEncryptAtRest">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DomainEncryptAtRest">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainEncryptAtRestArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainEncryptAtRestOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainEncryptAtRestArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainEncryptAtRest.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The KMS key id to encrypt the Elasticsearch domain with. If not specified then it defaults to using the `aws/es` service KMS key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The KMS key id to encrypt the Elasticsearch domain with. If not specified then it defaults to using the `aws/es` service KMS key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The KMS key id to encrypt the Elasticsearch domain with. If not specified then it defaults to using the `aws/es` service KMS key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The KMS key id to encrypt the Elasticsearch domain with. If not specified then it defaults to using the `aws/es` service KMS key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DomainLogPublishingOption
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DomainLogPublishingOption">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DomainLogPublishingOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainLogPublishingOptionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainLogPublishingOptionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainLogPublishingOptionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainLogPublishingOption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cloudwatch<wbr>Log<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the Cloudwatch log group to which log needs to be published.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Log<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A type of Elasticsearch log. Valid values: INDEX_SLOW_LOGS, SEARCH_SLOW_LOGS, ES_APPLICATION_LOGS
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cloudwatch<wbr>Log<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the Cloudwatch log group to which log needs to be published.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Log<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A type of Elasticsearch log. Valid values: INDEX_SLOW_LOGS, SEARCH_SLOW_LOGS, ES_APPLICATION_LOGS
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cloudwatch<wbr>Log<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the Cloudwatch log group to which log needs to be published.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">log<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A type of Elasticsearch log. Valid values: INDEX_SLOW_LOGS, SEARCH_SLOW_LOGS, ES_APPLICATION_LOGS
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cloudwatch_<wbr>log_<wbr>group_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the Cloudwatch log group to which log needs to be published.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">log<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A type of Elasticsearch log. Valid values: INDEX_SLOW_LOGS, SEARCH_SLOW_LOGS, ES_APPLICATION_LOGS
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DomainNodeToNodeEncryption
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DomainNodeToNodeEncryption">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DomainNodeToNodeEncryption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainNodeToNodeEncryptionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainNodeToNodeEncryptionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainNodeToNodeEncryptionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainNodeToNodeEncryption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether Amazon Cognito authentication with Kibana is enabled or not
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DomainSnapshotOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DomainSnapshotOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DomainSnapshotOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainSnapshotOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainSnapshotOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainSnapshotOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainSnapshotOptions.html">output</a> API doc for this type.
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





#### DomainVpcOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DomainVpcOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DomainVpcOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainVpcOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticsearch?tab=doc#DomainVpcOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainVpcOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticsearch.DomainVpcOptions.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of VPC Security Group IDs to be applied to the Elasticsearch domain endpoints. If omitted, the default Security Group for the VPC will be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of VPC Subnet IDs for the Elasticsearch domain endpoints to be created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of VPC Security Group IDs to be applied to the Elasticsearch domain endpoints. If omitted, the default Security Group for the VPC will be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of VPC Subnet IDs for the Elasticsearch domain endpoints to be created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of VPC Security Group IDs to be applied to the Elasticsearch domain endpoints. If omitted, the default Security Group for the VPC will be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of VPC Subnet IDs for the Elasticsearch domain endpoints to be created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">availability_<wbr>zones<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of VPC Security Group IDs to be applied to the Elasticsearch domain endpoints. If omitted, the default Security Group for the VPC will be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of VPC Subnet IDs for the Elasticsearch domain endpoints to be created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








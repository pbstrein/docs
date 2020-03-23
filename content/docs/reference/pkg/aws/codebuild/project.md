
---
title: "Project"
block_external_search_index: true
---

Provides a CodeBuild Project resource. See also the [`aws.codebuild.Webhook` resource](https://www.terraform.io/docs/providers/aws/r/codebuild_webhook.html), which manages the webhook to the source (e.g. the "rebuild every time a code change is pushed" option in the CodeBuild web console).

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleBucket = new aws.s3.Bucket("example", {
    acl: "private",
});
const exampleRole = new aws.iam.Role("example", {
    assumeRolePolicy: `{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "codebuild.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
`,
});
const exampleRolePolicy = new aws.iam.RolePolicy("example", {
    policy: pulumi.interpolate`{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Resource": [
        "*"
      ],
      "Action": [
        "logs:CreateLogGroup",
        "logs:CreateLogStream",
        "logs:PutLogEvents"
      ]
    },
    {
      "Effect": "Allow",
      "Action": [
        "ec2:CreateNetworkInterface",
        "ec2:DescribeDhcpOptions",
        "ec2:DescribeNetworkInterfaces",
        "ec2:DeleteNetworkInterface",
        "ec2:DescribeSubnets",
        "ec2:DescribeSecurityGroups",
        "ec2:DescribeVpcs"
      ],
      "Resource": "*"
    },
    {
      "Effect": "Allow",
      "Action": [
        "ec2:CreateNetworkInterfacePermission"
      ],
      "Resource": [
        "arn:aws:ec2:us-east-1:123456789012:network-interface/*"
      ],
      "Condition": {
        "StringEquals": {
          "ec2:Subnet": [
            "${aws_subnet_example1.arn}",
            "${aws_subnet_example2.arn}"
          ],
          "ec2:AuthorizedService": "codebuild.amazonaws.com"
        }
      }
    },
    {
      "Effect": "Allow",
      "Action": [
        "s3:*"
      ],
      "Resource": [
        "${exampleBucket.arn}",
        "${exampleBucket.arn}/*"
      ]
    }
  ]
}
`,
    role: exampleRole.name,
});
const exampleProject = new aws.codebuild.Project("example", {
    artifacts: {
        type: "NO_ARTIFACTS",
    },
    buildTimeout: 5,
    cache: {
        location: exampleBucket.bucket,
        type: "S3",
    },
    description: "test_codebuild_project",
    environment: {
        computeType: "BUILD_GENERAL1_SMALL",
        environmentVariables: [
            {
                name: "SOME_KEY1",
                value: "SOME_VALUE1",
            },
            {
                name: "SOME_KEY2",
                type: "PARAMETER_STORE",
                value: "SOME_VALUE2",
            },
        ],
        image: "aws/codebuild/standard:1.0",
        imagePullCredentialsType: "CODEBUILD",
        type: "LINUX_CONTAINER",
    },
    logsConfig: {
        cloudwatchLogs: {
            groupName: "log-group",
            streamName: "log-stream",
        },
        s3Logs: {
            location: pulumi.interpolate`${exampleBucket.id}/build-log`,
            status: "ENABLED",
        },
    },
    serviceRole: exampleRole.arn,
    source: {
        gitCloneDepth: 1,
        gitSubmodulesConfig: {
            fetchSubmodules: true,
        },
        location: "https://github.com/mitchellh/packer.git",
        type: "GITHUB",
    },
    sourceVersion: "master",
    tags: {
        Environment: "Test",
    },
    vpcConfig: {
        securityGroupIds: [
            aws_security_group_example1.id,
            aws_security_group_example2.id,
        ],
        subnets: [
            aws_subnet_example1.id,
            aws_subnet_example2.id,
        ],
        vpcId: aws_vpc_example.id,
    },
});
const project_with_cache = new aws.codebuild.Project("project-with-cache", {
    artifacts: {
        type: "NO_ARTIFACTS",
    },
    buildTimeout: 5,
    cache: {
        modes: [
            "LOCAL_DOCKER_LAYER_CACHE",
            "LOCAL_SOURCE_CACHE",
        ],
        type: "LOCAL",
    },
    description: "test_codebuild_project_cache",
    environment: {
        computeType: "BUILD_GENERAL1_SMALL",
        environmentVariables: [{
            name: "SOME_KEY1",
            value: "SOME_VALUE1",
        }],
        image: "aws/codebuild/standard:1.0",
        imagePullCredentialsType: "CODEBUILD",
        type: "LINUX_CONTAINER",
    },
    queuedTimeout: 5,
    serviceRole: exampleRole.arn,
    source: {
        gitCloneDepth: 1,
        location: "https://github.com/mitchellh/packer.git",
        type: "GITHUB",
    },
    tags: {
        Environment: "Test",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/codebuild_project.html.markdown.



## Create a Project Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codebuild/#Project">Project</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codebuild/#ProjectArgs">ProjectArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Project</span><span class="p">(resource_name, opts=None, </span>artifacts=None<span class="p">, </span>badge_enabled=None<span class="p">, </span>build_timeout=None<span class="p">, </span>cache=None<span class="p">, </span>description=None<span class="p">, </span>encryption_key=None<span class="p">, </span>environment=None<span class="p">, </span>logs_config=None<span class="p">, </span>name=None<span class="p">, </span>queued_timeout=None<span class="p">, </span>secondary_artifacts=None<span class="p">, </span>secondary_sources=None<span class="p">, </span>service_role=None<span class="p">, </span>source=None<span class="p">, </span>source_version=None<span class="p">, </span>tags=None<span class="p">, </span>vpc_config=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewProject<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectArgs">ProjectArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#Project">Project</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.Project.html">Project</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectArgs.html">ProjectArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectartifacts">Project<wbr>Artifacts<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build output artifacts. Artifact blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Badge<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Generates a publicly-accessible URL for the projects build badge. Available as `badge_url` attribute when enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Build<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), for AWS CodeBuild to wait until timing out any related build that does not get marked as completed. The default is 60 minutes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectcache">Project<wbr>Cache<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Information about the cache storage for the project. Cache blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A short description of the project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) customer master key (CMK) to be used for encrypting the build project&#39;s build output artifacts.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironment">Project<wbr>Environment<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build environment. Environment blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logs<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfig">Project<wbr>Logs<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store log data to CloudWatch or S3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Queued<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), a build is allowed to be queued before it times out. The default is 8 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secondary<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondaryartifact">List&lt;Project<wbr>Secondary<wbr>Artifact<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary artifacts to be used inside the build. Secondary artifacts blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secondary<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysource">List&lt;Project<wbr>Secondary<wbr>Source<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary sources to be used inside the build. Secondary sources blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the AWS Identity and Access Management (IAM) role that enables AWS CodeBuild to interact with dependent AWS services on behalf of the AWS account.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Source<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsource">Project<wbr>Source<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s input source code. Source blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A version of the build input to be built for this project. If not specified, the latest version is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectvpcconfig">Project<wbr>Vpc<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to run inside a VPC. VPC config blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectartifacts">Project<wbr>Artifacts</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build output artifacts. Artifact blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Badge<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Generates a publicly-accessible URL for the projects build badge. Available as `badge_url` attribute when enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Build<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), for AWS CodeBuild to wait until timing out any related build that does not get marked as completed. The default is 60 minutes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectcache">*Project<wbr>Cache</a></span>
    </dt>
    <dd>{{% md %}}Information about the cache storage for the project. Cache blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A short description of the project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) customer master key (CMK) to be used for encrypting the build project&#39;s build output artifacts.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironment">Project<wbr>Environment</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build environment. Environment blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logs<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfig">*Project<wbr>Logs<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store log data to CloudWatch or S3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Queued<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), a build is allowed to be queued before it times out. The default is 8 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secondary<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondaryartifact">[]Project<wbr>Secondary<wbr>Artifact</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary artifacts to be used inside the build. Secondary artifacts blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secondary<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysource">[]Project<wbr>Secondary<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary sources to be used inside the build. Secondary sources blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the AWS Identity and Access Management (IAM) role that enables AWS CodeBuild to interact with dependent AWS services on behalf of the AWS account.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Source<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsource">Project<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s input source code. Source blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A version of the build input to be built for this project. If not specified, the latest version is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectvpcconfig">*Project<wbr>Vpc<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to run inside a VPC. VPC config blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectartifacts">Project<wbr>Artifacts</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build output artifacts. Artifact blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">badge<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Generates a publicly-accessible URL for the projects build badge. Available as `badge_url` attribute when enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">build<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), for AWS CodeBuild to wait until timing out any related build that does not get marked as completed. The default is 60 minutes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectcache">Project<wbr>Cache?</a></span>
    </dt>
    <dd>{{% md %}}Information about the cache storage for the project. Cache blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A short description of the project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) customer master key (CMK) to be used for encrypting the build project&#39;s build output artifacts.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironment">Project<wbr>Environment</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build environment. Environment blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logs<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfig">Project<wbr>Logs<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store log data to CloudWatch or S3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">queued<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), a build is allowed to be queued before it times out. The default is 8 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secondary<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondaryartifact">Project<wbr>Secondary<wbr>Artifact[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary artifacts to be used inside the build. Secondary artifacts blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secondary<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysource">Project<wbr>Secondary<wbr>Source[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary sources to be used inside the build. Secondary sources blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the AWS Identity and Access Management (IAM) role that enables AWS CodeBuild to interact with dependent AWS services on behalf of the AWS account.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">source<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsource">Project<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s input source code. Source blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A version of the build input to be built for this project. If not specified, the latest version is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectvpcconfig">Project<wbr>Vpc<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to run inside a VPC. VPC config blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectartifacts">Dict[Project<wbr>Artifacts]</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build output artifacts. Artifact blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">badge_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Generates a publicly-accessible URL for the projects build badge. Available as `badge_url` attribute when enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">build_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), for AWS CodeBuild to wait until timing out any related build that does not get marked as completed. The default is 60 minutes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectcache">Dict[Project<wbr>Cache]</a></span>
    </dt>
    <dd>{{% md %}}Information about the cache storage for the project. Cache blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A short description of the project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) customer master key (CMK) to be used for encrypting the build project&#39;s build output artifacts.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironment">Dict[Project<wbr>Environment]</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build environment. Environment blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logs_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfig">Dict[Project<wbr>Logs<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store log data to CloudWatch or S3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">queued_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), a build is allowed to be queued before it times out. The default is 8 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secondary_<wbr>artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondaryartifact">List[Project<wbr>Secondary<wbr>Artifact]</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary artifacts to be used inside the build. Secondary artifacts blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secondary_<wbr>sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysource">List[Project<wbr>Secondary<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary sources to be used inside the build. Secondary sources blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the AWS Identity and Access Management (IAM) role that enables AWS CodeBuild to interact with dependent AWS services on behalf of the AWS account.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">source<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsource">Dict[Project<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s input source code. Source blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A version of the build input to be built for this project. If not specified, the latest version is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectvpcconfig">Dict[Project<wbr>Vpc<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to run inside a VPC. VPC config blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Project Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the CodeBuild project.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectartifacts">Project<wbr>Artifacts</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build output artifacts. Artifact blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Badge<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Generates a publicly-accessible URL for the projects build badge. Available as `badge_url` attribute when enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Badge<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URL of the build badge when `badge_enabled` is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Build<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), for AWS CodeBuild to wait until timing out any related build that does not get marked as completed. The default is 60 minutes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cache<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectcache">Project<wbr>Cache?</a></span>
    </dt>
    <dd>{{% md %}}Information about the cache storage for the project. Cache blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A short description of the project.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encryption<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) customer master key (CMK) to be used for encrypting the build project&#39;s build output artifacts.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironment">Project<wbr>Environment</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build environment. Environment blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logs<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfig">Project<wbr>Logs<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store log data to CloudWatch or S3.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-"
            title="">Queued<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), a build is allowed to be queued before it times out. The default is 8 hours.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Secondary<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondaryartifact">List&lt;Project<wbr>Secondary<wbr>Artifact&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary artifacts to be used inside the build. Secondary artifacts blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Secondary<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysource">List&lt;Project<wbr>Secondary<wbr>Source&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary sources to be used inside the build. Secondary sources blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the AWS Identity and Access Management (IAM) role that enables AWS CodeBuild to interact with dependent AWS services on behalf of the AWS account.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsource">Project<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s input source code. Source blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A version of the build input to be built for this project. If not specified, the latest version is used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectvpcconfig">Project<wbr>Vpc<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to run inside a VPC. VPC config blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the CodeBuild project.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectartifacts">Project<wbr>Artifacts</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build output artifacts. Artifact blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Badge<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Generates a publicly-accessible URL for the projects build badge. Available as `badge_url` attribute when enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Badge<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URL of the build badge when `badge_enabled` is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Build<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), for AWS CodeBuild to wait until timing out any related build that does not get marked as completed. The default is 60 minutes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cache<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectcache">*Project<wbr>Cache</a></span>
    </dt>
    <dd>{{% md %}}Information about the cache storage for the project. Cache blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A short description of the project.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encryption<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) customer master key (CMK) to be used for encrypting the build project&#39;s build output artifacts.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironment">Project<wbr>Environment</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build environment. Environment blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logs<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfig">*Project<wbr>Logs<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store log data to CloudWatch or S3.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-"
            title="">Queued<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), a build is allowed to be queued before it times out. The default is 8 hours.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Secondary<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondaryartifact">[]Project<wbr>Secondary<wbr>Artifact</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary artifacts to be used inside the build. Secondary artifacts blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Secondary<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysource">[]Project<wbr>Secondary<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary sources to be used inside the build. Secondary sources blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the AWS Identity and Access Management (IAM) role that enables AWS CodeBuild to interact with dependent AWS services on behalf of the AWS account.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsource">Project<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s input source code. Source blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A version of the build input to be built for this project. If not specified, the latest version is used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectvpcconfig">*Project<wbr>Vpc<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to run inside a VPC. VPC config blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the CodeBuild project.
{{% /md %}}</dd>

    <dt class="property-"
            title="">artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectartifacts">Project<wbr>Artifacts</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build output artifacts. Artifact blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">badge<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Generates a publicly-accessible URL for the projects build badge. Available as `badge_url` attribute when enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">badge<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URL of the build badge when `badge_enabled` is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">build<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), for AWS CodeBuild to wait until timing out any related build that does not get marked as completed. The default is 60 minutes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cache<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectcache">Project<wbr>Cache?</a></span>
    </dt>
    <dd>{{% md %}}Information about the cache storage for the project. Cache blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A short description of the project.
{{% /md %}}</dd>

    <dt class="property-"
            title="">encryption<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) customer master key (CMK) to be used for encrypting the build project&#39;s build output artifacts.
{{% /md %}}</dd>

    <dt class="property-"
            title="">environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironment">Project<wbr>Environment</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build environment. Environment blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">logs<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfig">Project<wbr>Logs<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store log data to CloudWatch or S3.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-"
            title="">queued<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), a build is allowed to be queued before it times out. The default is 8 hours.
{{% /md %}}</dd>

    <dt class="property-"
            title="">secondary<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondaryartifact">Project<wbr>Secondary<wbr>Artifact[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary artifacts to be used inside the build. Secondary artifacts blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">secondary<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysource">Project<wbr>Secondary<wbr>Source[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary sources to be used inside the build. Secondary sources blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the AWS Identity and Access Management (IAM) role that enables AWS CodeBuild to interact with dependent AWS services on behalf of the AWS account.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsource">Project<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s input source code. Source blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A version of the build input to be built for this project. If not specified, the latest version is used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectvpcconfig">Project<wbr>Vpc<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to run inside a VPC. VPC config blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the CodeBuild project.
{{% /md %}}</dd>

    <dt class="property-"
            title="">artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectartifacts">Dict[Project<wbr>Artifacts]</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build output artifacts. Artifact blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">badge_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Generates a publicly-accessible URL for the projects build badge. Available as `badge_url` attribute when enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">badge_<wbr>url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The URL of the build badge when `badge_enabled` is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">build_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), for AWS CodeBuild to wait until timing out any related build that does not get marked as completed. The default is 60 minutes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cache<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectcache">Dict[Project<wbr>Cache]</a></span>
    </dt>
    <dd>{{% md %}}Information about the cache storage for the project. Cache blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A short description of the project.
{{% /md %}}</dd>

    <dt class="property-"
            title="">encryption_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) customer master key (CMK) to be used for encrypting the build project&#39;s build output artifacts.
{{% /md %}}</dd>

    <dt class="property-"
            title="">environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironment">Dict[Project<wbr>Environment]</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build environment. Environment blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">logs_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfig">Dict[Project<wbr>Logs<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store log data to CloudWatch or S3.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-"
            title="">queued_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), a build is allowed to be queued before it times out. The default is 8 hours.
{{% /md %}}</dd>

    <dt class="property-"
            title="">secondary_<wbr>artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondaryartifact">List[Project<wbr>Secondary<wbr>Artifact]</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary artifacts to be used inside the build. Secondary artifacts blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">secondary_<wbr>sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysource">List[Project<wbr>Secondary<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary sources to be used inside the build. Secondary sources blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the AWS Identity and Access Management (IAM) role that enables AWS CodeBuild to interact with dependent AWS services on behalf of the AWS account.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsource">Dict[Project<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s input source code. Source blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A version of the build input to be built for this project. If not specified, the latest version is used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectvpcconfig">Dict[Project<wbr>Vpc<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to run inside a VPC. VPC config blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Project Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codebuild/#ProjectState">ProjectState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codebuild/#Project">Project</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>artifacts=None<span class="p">, </span>badge_enabled=None<span class="p">, </span>badge_url=None<span class="p">, </span>build_timeout=None<span class="p">, </span>cache=None<span class="p">, </span>description=None<span class="p">, </span>encryption_key=None<span class="p">, </span>environment=None<span class="p">, </span>logs_config=None<span class="p">, </span>name=None<span class="p">, </span>queued_timeout=None<span class="p">, </span>secondary_artifacts=None<span class="p">, </span>secondary_sources=None<span class="p">, </span>service_role=None<span class="p">, </span>source=None<span class="p">, </span>source_version=None<span class="p">, </span>tags=None<span class="p">, </span>vpc_config=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetProject<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectState">ProjectState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#Project">Project</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.Project.html">Project</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectState.html">ProjectState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Project resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The ARN of the CodeBuild project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectartifacts">Project<wbr>Artifacts<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build output artifacts. Artifact blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Badge<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Generates a publicly-accessible URL for the projects build badge. Available as `badge_url` attribute when enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Badge<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The URL of the build badge when `badge_enabled` is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Build<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), for AWS CodeBuild to wait until timing out any related build that does not get marked as completed. The default is 60 minutes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectcache">Project<wbr>Cache<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Information about the cache storage for the project. Cache blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A short description of the project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) customer master key (CMK) to be used for encrypting the build project&#39;s build output artifacts.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironment">Project<wbr>Environment<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build environment. Environment blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logs<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfig">Project<wbr>Logs<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store log data to CloudWatch or S3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Queued<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), a build is allowed to be queued before it times out. The default is 8 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secondary<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondaryartifact">List&lt;Project<wbr>Secondary<wbr>Artifact<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary artifacts to be used inside the build. Secondary artifacts blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secondary<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysource">List&lt;Project<wbr>Secondary<wbr>Source<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary sources to be used inside the build. Secondary sources blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the AWS Identity and Access Management (IAM) role that enables AWS CodeBuild to interact with dependent AWS services on behalf of the AWS account.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsource">Project<wbr>Source<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s input source code. Source blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A version of the build input to be built for this project. If not specified, the latest version is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectvpcconfig">Project<wbr>Vpc<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to run inside a VPC. VPC config blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the CodeBuild project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectartifacts">*Project<wbr>Artifacts</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build output artifacts. Artifact blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Badge<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Generates a publicly-accessible URL for the projects build badge. Available as `badge_url` attribute when enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Badge<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The URL of the build badge when `badge_enabled` is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Build<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), for AWS CodeBuild to wait until timing out any related build that does not get marked as completed. The default is 60 minutes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectcache">*Project<wbr>Cache</a></span>
    </dt>
    <dd>{{% md %}}Information about the cache storage for the project. Cache blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A short description of the project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) customer master key (CMK) to be used for encrypting the build project&#39;s build output artifacts.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironment">*Project<wbr>Environment</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build environment. Environment blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logs<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfig">*Project<wbr>Logs<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store log data to CloudWatch or S3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Queued<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), a build is allowed to be queued before it times out. The default is 8 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secondary<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondaryartifact">[]Project<wbr>Secondary<wbr>Artifact</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary artifacts to be used inside the build. Secondary artifacts blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secondary<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysource">[]Project<wbr>Secondary<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary sources to be used inside the build. Secondary sources blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the AWS Identity and Access Management (IAM) role that enables AWS CodeBuild to interact with dependent AWS services on behalf of the AWS account.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsource">*Project<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s input source code. Source blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A version of the build input to be built for this project. If not specified, the latest version is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectvpcconfig">*Project<wbr>Vpc<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to run inside a VPC. VPC config blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the CodeBuild project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectartifacts">Project<wbr>Artifacts?</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build output artifacts. Artifact blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">badge<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Generates a publicly-accessible URL for the projects build badge. Available as `badge_url` attribute when enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">badge<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The URL of the build badge when `badge_enabled` is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">build<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), for AWS CodeBuild to wait until timing out any related build that does not get marked as completed. The default is 60 minutes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectcache">Project<wbr>Cache?</a></span>
    </dt>
    <dd>{{% md %}}Information about the cache storage for the project. Cache blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A short description of the project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) customer master key (CMK) to be used for encrypting the build project&#39;s build output artifacts.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironment">Project<wbr>Environment?</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build environment. Environment blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logs<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfig">Project<wbr>Logs<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store log data to CloudWatch or S3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">queued<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), a build is allowed to be queued before it times out. The default is 8 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secondary<wbr>Artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondaryartifact">Project<wbr>Secondary<wbr>Artifact[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary artifacts to be used inside the build. Secondary artifacts blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secondary<wbr>Sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysource">Project<wbr>Secondary<wbr>Source[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary sources to be used inside the build. Secondary sources blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the AWS Identity and Access Management (IAM) role that enables AWS CodeBuild to interact with dependent AWS services on behalf of the AWS account.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsource">Project<wbr>Source?</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s input source code. Source blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A version of the build input to be built for this project. If not specified, the latest version is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectvpcconfig">Project<wbr>Vpc<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to run inside a VPC. VPC config blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the CodeBuild project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectartifacts">Dict[Project<wbr>Artifacts]</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build output artifacts. Artifact blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">badge_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Generates a publicly-accessible URL for the projects build badge. Available as `badge_url` attribute when enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">badge_<wbr>url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The URL of the build badge when `badge_enabled` is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">build_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), for AWS CodeBuild to wait until timing out any related build that does not get marked as completed. The default is 60 minutes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectcache">Dict[Project<wbr>Cache]</a></span>
    </dt>
    <dd>{{% md %}}Information about the cache storage for the project. Cache blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A short description of the project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) customer master key (CMK) to be used for encrypting the build project&#39;s build output artifacts.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironment">Dict[Project<wbr>Environment]</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s build environment. Environment blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logs_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfig">Dict[Project<wbr>Logs<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store log data to CloudWatch or S3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">queued_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}How long in minutes, from 5 to 480 (8 hours), a build is allowed to be queued before it times out. The default is 8 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secondary_<wbr>artifacts<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondaryartifact">List[Project<wbr>Secondary<wbr>Artifact]</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary artifacts to be used inside the build. Secondary artifacts blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secondary_<wbr>sources<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysource">List[Project<wbr>Secondary<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}A set of secondary sources to be used inside the build. Secondary sources blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the AWS Identity and Access Management (IAM) role that enables AWS CodeBuild to interact with dependent AWS services on behalf of the AWS account.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsource">Dict[Project<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}Information about the project&#39;s input source code. Source blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A version of the build input to be built for this project. If not specified, the latest version is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectvpcconfig">Dict[Project<wbr>Vpc<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to run inside a VPC. VPC config blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### ProjectArtifacts
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectArtifacts">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectArtifacts">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectArtifactsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectArtifactsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectArtifactsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectArtifacts.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Artifact<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The artifact identifier. Must be the same specified inside AWS CodeBuild buildspec.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Disabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If set to true, output artifacts will not be encrypted. If `type` is set to `NO_ARTIFACTS` then this value will be ignored. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Namespace<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The namespace to use in storing build artifacts. If `type` is set to `S3`, then valid values for this parameter are: `BUILD_ID` or `NONE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Override<wbr>Artifact<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If set to true, a name specified in the build spec file overrides the artifact name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Packaging<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of build output artifact to create. If `type` is set to `S3`, valid values for this parameter are: `NONE` or `ZIP`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `type` is set to `S3`, this is the path to the output artifact
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Artifact<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The artifact identifier. Must be the same specified inside AWS CodeBuild buildspec.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Disabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If set to true, output artifacts will not be encrypted. If `type` is set to `NO_ARTIFACTS` then this value will be ignored. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Namespace<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The namespace to use in storing build artifacts. If `type` is set to `S3`, then valid values for this parameter are: `BUILD_ID` or `NONE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Override<wbr>Artifact<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If set to true, a name specified in the build spec file overrides the artifact name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Packaging<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of build output artifact to create. If `type` is set to `S3`, valid values for this parameter are: `NONE` or `ZIP`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Path<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If `type` is set to `S3`, this is the path to the output artifact
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">artifact<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The artifact identifier. Must be the same specified inside AWS CodeBuild buildspec.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption<wbr>Disabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If set to true, output artifacts will not be encrypted. If `type` is set to `NO_ARTIFACTS` then this value will be ignored. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">namespace<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The namespace to use in storing build artifacts. If `type` is set to `S3`, then valid values for this parameter are: `BUILD_ID` or `NONE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">override<wbr>Artifact<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If set to true, a name specified in the build spec file overrides the artifact name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">packaging<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of build output artifact to create. If `type` is set to `S3`, valid values for this parameter are: `NONE` or `ZIP`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `type` is set to `S3`, this is the path to the output artifact
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">artifact<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The artifact identifier. Must be the same specified inside AWS CodeBuild buildspec.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption<wbr>Disabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set to true, output artifacts will not be encrypted. If `type` is set to `NO_ARTIFACTS` then this value will be ignored. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">namespace<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The namespace to use in storing build artifacts. If `type` is set to `S3`, then valid values for this parameter are: `BUILD_ID` or `NONE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">override<wbr>Artifact<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set to true, a name specified in the build spec file overrides the artifact name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">packaging<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of build output artifact to create. If `type` is set to `S3`, valid values for this parameter are: `NONE` or `ZIP`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If `type` is set to `S3`, this is the path to the output artifact
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ProjectCache
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectCache">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectCache">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectCacheArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectCacheOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectCacheArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectCache.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Modes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Specifies settings that AWS CodeBuild uses to store and reuse build dependencies. Valid values:  `LOCAL_SOURCE_CACHE`, `LOCAL_DOCKER_LAYER_CACHE`, and `LOCAL_CUSTOM_CACHE`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Modes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specifies settings that AWS CodeBuild uses to store and reuse build dependencies. Valid values:  `LOCAL_SOURCE_CACHE`, `LOCAL_DOCKER_LAYER_CACHE`, and `LOCAL_CUSTOM_CACHE`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">modes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Specifies settings that AWS CodeBuild uses to store and reuse build dependencies. Valid values:  `LOCAL_SOURCE_CACHE`, `LOCAL_DOCKER_LAYER_CACHE`, and `LOCAL_CUSTOM_CACHE`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">modes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specifies settings that AWS CodeBuild uses to store and reuse build dependencies. Valid values:  `LOCAL_SOURCE_CACHE`, `LOCAL_DOCKER_LAYER_CACHE`, and `LOCAL_CUSTOM_CACHE`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ProjectEnvironment
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectEnvironment">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectEnvironment">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectEnvironmentArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectEnvironmentOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectEnvironmentArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectEnvironment.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Certificate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket, path prefix and object key that contains the PEM-encoded certificate.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Compute<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Information about the compute resources the build project will use. Available values for this parameter are: `BUILD_GENERAL1_SMALL`, `BUILD_GENERAL1_MEDIUM`, `BUILD_GENERAL1_LARGE` or `BUILD_GENERAL1_2XLARGE`. `BUILD_GENERAL1_SMALL` is only valid if `type` is set to `LINUX_CONTAINER`. When `type` is set to `LINUX_GPU_CONTAINER`, `compute_type` need to be `BUILD_GENERAL1_LARGE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Environment<wbr>Variables<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironmentenvironmentvariable">List&lt;Project<wbr>Environment<wbr>Environment<wbr>Variable<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of environment variables to make available to builds for this build project.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Image<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Docker image to use for this build project. Valid values include [Docker images provided by CodeBuild](https://docs.aws.amazon.com/codebuild/latest/userguide/build-env-ref-available.html) (e.g `aws/codebuild/standard:2.0`), [Docker Hub images](https://hub.docker.com/) (e.g. `nginx:latest`), and full Docker repository URIs such as those for ECR (e.g. `137112412989.dkr.ecr.us-west-2.amazonaws.com/amazonlinux:latest`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Image<wbr>Pull<wbr>Credentials<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of credentials AWS CodeBuild uses to pull images in your build. Available values for this parameter are `CODEBUILD` or `SERVICE_ROLE`. When you use a cross-account or private registry image, you must use SERVICE_ROLE credentials. When you use an AWS CodeBuild curated image, you must use CODEBUILD credentials. Default to `CODEBUILD`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Privileged<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If set to true, enables running the Docker daemon inside a Docker container. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Registry<wbr>Credential<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironmentregistrycredential">Project<wbr>Environment<wbr>Registry<wbr>Credential<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Information about credentials for access to a private Docker registry. Registry Credential config blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Certificate<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket, path prefix and object key that contains the PEM-encoded certificate.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Compute<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Information about the compute resources the build project will use. Available values for this parameter are: `BUILD_GENERAL1_SMALL`, `BUILD_GENERAL1_MEDIUM`, `BUILD_GENERAL1_LARGE` or `BUILD_GENERAL1_2XLARGE`. `BUILD_GENERAL1_SMALL` is only valid if `type` is set to `LINUX_CONTAINER`. When `type` is set to `LINUX_GPU_CONTAINER`, `compute_type` need to be `BUILD_GENERAL1_LARGE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Environment<wbr>Variables<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironmentenvironmentvariable">[]Project<wbr>Environment<wbr>Environment<wbr>Variable</a></span>
    </dt>
    <dd>{{% md %}}A set of environment variables to make available to builds for this build project.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Image<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Docker image to use for this build project. Valid values include [Docker images provided by CodeBuild](https://docs.aws.amazon.com/codebuild/latest/userguide/build-env-ref-available.html) (e.g `aws/codebuild/standard:2.0`), [Docker Hub images](https://hub.docker.com/) (e.g. `nginx:latest`), and full Docker repository URIs such as those for ECR (e.g. `137112412989.dkr.ecr.us-west-2.amazonaws.com/amazonlinux:latest`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Image<wbr>Pull<wbr>Credentials<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of credentials AWS CodeBuild uses to pull images in your build. Available values for this parameter are `CODEBUILD` or `SERVICE_ROLE`. When you use a cross-account or private registry image, you must use SERVICE_ROLE credentials. When you use an AWS CodeBuild curated image, you must use CODEBUILD credentials. Default to `CODEBUILD`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Privileged<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If set to true, enables running the Docker daemon inside a Docker container. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Registry<wbr>Credential<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironmentregistrycredential">*Project<wbr>Environment<wbr>Registry<wbr>Credential</a></span>
    </dt>
    <dd>{{% md %}}Information about credentials for access to a private Docker registry. Registry Credential config blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">certificate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket, path prefix and object key that contains the PEM-encoded certificate.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">compute<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Information about the compute resources the build project will use. Available values for this parameter are: `BUILD_GENERAL1_SMALL`, `BUILD_GENERAL1_MEDIUM`, `BUILD_GENERAL1_LARGE` or `BUILD_GENERAL1_2XLARGE`. `BUILD_GENERAL1_SMALL` is only valid if `type` is set to `LINUX_CONTAINER`. When `type` is set to `LINUX_GPU_CONTAINER`, `compute_type` need to be `BUILD_GENERAL1_LARGE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">environment<wbr>Variables<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironmentenvironmentvariable">Project<wbr>Environment<wbr>Environment<wbr>Variable[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of environment variables to make available to builds for this build project.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">image<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Docker image to use for this build project. Valid values include [Docker images provided by CodeBuild](https://docs.aws.amazon.com/codebuild/latest/userguide/build-env-ref-available.html) (e.g `aws/codebuild/standard:2.0`), [Docker Hub images](https://hub.docker.com/) (e.g. `nginx:latest`), and full Docker repository URIs such as those for ECR (e.g. `137112412989.dkr.ecr.us-west-2.amazonaws.com/amazonlinux:latest`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">image<wbr>Pull<wbr>Credentials<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of credentials AWS CodeBuild uses to pull images in your build. Available values for this parameter are `CODEBUILD` or `SERVICE_ROLE`. When you use a cross-account or private registry image, you must use SERVICE_ROLE credentials. When you use an AWS CodeBuild curated image, you must use CODEBUILD credentials. Default to `CODEBUILD`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">privileged<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If set to true, enables running the Docker daemon inside a Docker container. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">registry<wbr>Credential<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironmentregistrycredential">Project<wbr>Environment<wbr>Registry<wbr>Credential?</a></span>
    </dt>
    <dd>{{% md %}}Information about credentials for access to a private Docker registry. Registry Credential config blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">certificate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket, path prefix and object key that contains the PEM-encoded certificate.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">compute<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Information about the compute resources the build project will use. Available values for this parameter are: `BUILD_GENERAL1_SMALL`, `BUILD_GENERAL1_MEDIUM`, `BUILD_GENERAL1_LARGE` or `BUILD_GENERAL1_2XLARGE`. `BUILD_GENERAL1_SMALL` is only valid if `type` is set to `LINUX_CONTAINER`. When `type` is set to `LINUX_GPU_CONTAINER`, `compute_type` need to be `BUILD_GENERAL1_LARGE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">environment<wbr>Variables<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironmentenvironmentvariable">List[Project<wbr>Environment<wbr>Environment<wbr>Variable]</a></span>
    </dt>
    <dd>{{% md %}}A set of environment variables to make available to builds for this build project.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">image<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Docker image to use for this build project. Valid values include [Docker images provided by CodeBuild](https://docs.aws.amazon.com/codebuild/latest/userguide/build-env-ref-available.html) (e.g `aws/codebuild/standard:2.0`), [Docker Hub images](https://hub.docker.com/) (e.g. `nginx:latest`), and full Docker repository URIs such as those for ECR (e.g. `137112412989.dkr.ecr.us-west-2.amazonaws.com/amazonlinux:latest`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">image<wbr>Pull<wbr>Credentials<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of credentials AWS CodeBuild uses to pull images in your build. Available values for this parameter are `CODEBUILD` or `SERVICE_ROLE`. When you use a cross-account or private registry image, you must use SERVICE_ROLE credentials. When you use an AWS CodeBuild curated image, you must use CODEBUILD credentials. Default to `CODEBUILD`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">privileged<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set to true, enables running the Docker daemon inside a Docker container. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">registry<wbr>Credential<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectenvironmentregistrycredential">Dict[Project<wbr>Environment<wbr>Registry<wbr>Credential]</a></span>
    </dt>
    <dd>{{% md %}}Information about credentials for access to a private Docker registry. Registry Credential config blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ProjectEnvironmentEnvironmentVariable
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectEnvironmentEnvironmentVariable">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectEnvironmentEnvironmentVariable">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectEnvironmentEnvironmentVariableArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectEnvironmentEnvironmentVariableOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectEnvironmentEnvironmentVariableArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectEnvironmentEnvironmentVariable.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The environment variable&#39;s value.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The environment variable&#39;s value.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The environment variable&#39;s value.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The environment variable&#39;s value.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ProjectEnvironmentRegistryCredential
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectEnvironmentRegistryCredential">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectEnvironmentRegistryCredential">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectEnvironmentRegistryCredentialArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectEnvironmentRegistryCredentialOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectEnvironmentRegistryCredentialArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectEnvironmentRegistryCredential.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Credential<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) or name of credentials created using AWS Secrets Manager.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Credential<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The service that created the credentials to access a private Docker registry. The valid value, SECRETS_MANAGER, is for AWS Secrets Manager.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Credential<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) or name of credentials created using AWS Secrets Manager.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Credential<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The service that created the credentials to access a private Docker registry. The valid value, SECRETS_MANAGER, is for AWS Secrets Manager.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">credential<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) or name of credentials created using AWS Secrets Manager.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">credential<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The service that created the credentials to access a private Docker registry. The valid value, SECRETS_MANAGER, is for AWS Secrets Manager.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">credential<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) or name of credentials created using AWS Secrets Manager.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">credential<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The service that created the credentials to access a private Docker registry. The valid value, SECRETS_MANAGER, is for AWS Secrets Manager.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ProjectLogsConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectLogsConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectLogsConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectLogsConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectLogsConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectLogsConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectLogsConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cloudwatch<wbr>Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfigcloudwatchlogs">Project<wbr>Logs<wbr>Config<wbr>Cloudwatch<wbr>Logs<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store logs to CloudWatch
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfigs3logs">Project<wbr>Logs<wbr>Config<wbr>S3Logs<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store logs to S3.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cloudwatch<wbr>Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfigcloudwatchlogs">*Project<wbr>Logs<wbr>Config<wbr>Cloudwatch<wbr>Logs</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store logs to CloudWatch
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfigs3logs">*Project<wbr>Logs<wbr>Config<wbr>S3Logs</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store logs to S3.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cloudwatch<wbr>Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfigcloudwatchlogs">Project<wbr>Logs<wbr>Config<wbr>Cloudwatch<wbr>Logs?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store logs to CloudWatch
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfigs3logs">Project<wbr>Logs<wbr>Config<wbr>S3Logs?</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store logs to S3.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cloudwatch<wbr>Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfigcloudwatchlogs">Dict[Project<wbr>Logs<wbr>Config<wbr>Cloudwatch<wbr>Logs]</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store logs to CloudWatch
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectlogsconfigs3logs">Dict[Project<wbr>Logs<wbr>Config<wbr>S3Logs]</a></span>
    </dt>
    <dd>{{% md %}}Configuration for the builds to store logs to S3.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ProjectLogsConfigCloudwatchLogs
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectLogsConfigCloudwatchLogs">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectLogsConfigCloudwatchLogs">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectLogsConfigCloudwatchLogsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectLogsConfigCloudwatchLogsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectLogsConfigCloudwatchLogsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectLogsConfigCloudwatchLogs.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The group name of the logs in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Current status of logs in S3 for a build project. Valid values: `ENABLED`, `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The stream name of the logs in CloudWatch Logs.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The group name of the logs in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Current status of logs in S3 for a build project. Valid values: `ENABLED`, `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The stream name of the logs in CloudWatch Logs.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The group name of the logs in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Current status of logs in S3 for a build project. Valid values: `ENABLED`, `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The stream name of the logs in CloudWatch Logs.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The group name of the logs in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Current status of logs in S3 for a build project. Valid values: `ENABLED`, `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The stream name of the logs in CloudWatch Logs.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ProjectLogsConfigS3Logs
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectLogsConfigS3Logs">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectLogsConfigS3Logs">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectLogsConfigS3LogsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectLogsConfigS3LogsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectLogsConfigS3LogsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectLogsConfigS3Logs.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Disabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If set to true, output artifacts will not be encrypted. If `type` is set to `NO_ARTIFACTS` then this value will be ignored. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Current status of logs in S3 for a build project. Valid values: `ENABLED`, `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Disabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If set to true, output artifacts will not be encrypted. If `type` is set to `NO_ARTIFACTS` then this value will be ignored. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Current status of logs in S3 for a build project. Valid values: `ENABLED`, `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">encryption<wbr>Disabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If set to true, output artifacts will not be encrypted. If `type` is set to `NO_ARTIFACTS` then this value will be ignored. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Current status of logs in S3 for a build project. Valid values: `ENABLED`, `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">encryption<wbr>Disabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set to true, output artifacts will not be encrypted. If `type` is set to `NO_ARTIFACTS` then this value will be ignored. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Current status of logs in S3 for a build project. Valid values: `ENABLED`, `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ProjectSecondaryArtifact
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectSecondaryArtifact">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectSecondaryArtifact">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectSecondaryArtifactArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectSecondaryArtifactOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectSecondaryArtifactArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectSecondaryArtifact.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Artifact<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The artifact identifier. Must be the same specified inside AWS CodeBuild buildspec.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Disabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If set to true, output artifacts will not be encrypted. If `type` is set to `NO_ARTIFACTS` then this value will be ignored. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Namespace<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The namespace to use in storing build artifacts. If `type` is set to `S3`, then valid values for this parameter are: `BUILD_ID` or `NONE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Override<wbr>Artifact<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If set to true, a name specified in the build spec file overrides the artifact name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Packaging<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of build output artifact to create. If `type` is set to `S3`, valid values for this parameter are: `NONE` or `ZIP`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `type` is set to `S3`, this is the path to the output artifact
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Artifact<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The artifact identifier. Must be the same specified inside AWS CodeBuild buildspec.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Disabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If set to true, output artifacts will not be encrypted. If `type` is set to `NO_ARTIFACTS` then this value will be ignored. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Namespace<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The namespace to use in storing build artifacts. If `type` is set to `S3`, then valid values for this parameter are: `BUILD_ID` or `NONE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Override<wbr>Artifact<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If set to true, a name specified in the build spec file overrides the artifact name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Packaging<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of build output artifact to create. If `type` is set to `S3`, valid values for this parameter are: `NONE` or `ZIP`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Path<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If `type` is set to `S3`, this is the path to the output artifact
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">artifact<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The artifact identifier. Must be the same specified inside AWS CodeBuild buildspec.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption<wbr>Disabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If set to true, output artifacts will not be encrypted. If `type` is set to `NO_ARTIFACTS` then this value will be ignored. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">namespace<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The namespace to use in storing build artifacts. If `type` is set to `S3`, then valid values for this parameter are: `BUILD_ID` or `NONE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">override<wbr>Artifact<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If set to true, a name specified in the build spec file overrides the artifact name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">packaging<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of build output artifact to create. If `type` is set to `S3`, valid values for this parameter are: `NONE` or `ZIP`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `type` is set to `S3`, this is the path to the output artifact
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">artifact<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The artifact identifier. Must be the same specified inside AWS CodeBuild buildspec.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption<wbr>Disabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set to true, output artifacts will not be encrypted. If `type` is set to `NO_ARTIFACTS` then this value will be ignored. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the project. If `type` is set to `S3`, this is the name of the output artifact object
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">namespace<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The namespace to use in storing build artifacts. If `type` is set to `S3`, then valid values for this parameter are: `BUILD_ID` or `NONE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">override<wbr>Artifact<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set to true, a name specified in the build spec file overrides the artifact name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">packaging<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of build output artifact to create. If `type` is set to `S3`, valid values for this parameter are: `NONE` or `ZIP`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If `type` is set to `S3`, this is the path to the output artifact
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ProjectSecondarySource
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectSecondarySource">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectSecondarySource">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectSecondarySourceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectSecondarySourceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectSecondarySourceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectSecondarySource.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Auths<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysourceauth">List&lt;Project<wbr>Secondary<wbr>Source<wbr>Auth<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Information about the authorization settings for AWS CodeBuild to access the source code to be built. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Buildspec<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The build spec declaration to use for this build project&#39;s related builds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Git<wbr>Clone<wbr>Depth<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Truncate git history to this many commits.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Git<wbr>Submodules<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysourcegitsubmodulesconfig">Project<wbr>Secondary<wbr>Source<wbr>Git<wbr>Submodules<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Information about the Git submodules configuration for an AWS CodeBuild build project. Git submodules config blocks are documented below. This option is only valid when the `type` is `CODECOMMIT`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Insecure<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Ignore SSL warnings when connecting to source control.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Report<wbr>Build<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Set to `true` to report the status of a build&#39;s start and finish to your source provider. This option is only valid when your source provider is `GITHUB`, `BITBUCKET`, or `GITHUB_ENTERPRISE`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Source<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The source identifier. Source data will be put inside a folder named as this parameter inside AWS CodeBuild source directory
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Auths<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysourceauth">[]Project<wbr>Secondary<wbr>Source<wbr>Auth</a></span>
    </dt>
    <dd>{{% md %}}Information about the authorization settings for AWS CodeBuild to access the source code to be built. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Buildspec<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The build spec declaration to use for this build project&#39;s related builds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Git<wbr>Clone<wbr>Depth<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Truncate git history to this many commits.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Git<wbr>Submodules<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysourcegitsubmodulesconfig">*Project<wbr>Secondary<wbr>Source<wbr>Git<wbr>Submodules<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Information about the Git submodules configuration for an AWS CodeBuild build project. Git submodules config blocks are documented below. This option is only valid when the `type` is `CODECOMMIT`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Insecure<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Ignore SSL warnings when connecting to source control.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Report<wbr>Build<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Set to `true` to report the status of a build&#39;s start and finish to your source provider. This option is only valid when your source provider is `GITHUB`, `BITBUCKET`, or `GITHUB_ENTERPRISE`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Source<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The source identifier. Source data will be put inside a folder named as this parameter inside AWS CodeBuild source directory
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">auths<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysourceauth">Project<wbr>Secondary<wbr>Source<wbr>Auth[]?</a></span>
    </dt>
    <dd>{{% md %}}Information about the authorization settings for AWS CodeBuild to access the source code to be built. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">buildspec<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The build spec declaration to use for this build project&#39;s related builds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">git<wbr>Clone<wbr>Depth<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Truncate git history to this many commits.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">git<wbr>Submodules<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysourcegitsubmodulesconfig">Project<wbr>Secondary<wbr>Source<wbr>Git<wbr>Submodules<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Information about the Git submodules configuration for an AWS CodeBuild build project. Git submodules config blocks are documented below. This option is only valid when the `type` is `CODECOMMIT`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">insecure<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Ignore SSL warnings when connecting to source control.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">report<wbr>Build<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Set to `true` to report the status of a build&#39;s start and finish to your source provider. This option is only valid when your source provider is `GITHUB`, `BITBUCKET`, or `GITHUB_ENTERPRISE`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">source<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The source identifier. Source data will be put inside a folder named as this parameter inside AWS CodeBuild source directory
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">auths<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysourceauth">List[Project<wbr>Secondary<wbr>Source<wbr>Auth]</a></span>
    </dt>
    <dd>{{% md %}}Information about the authorization settings for AWS CodeBuild to access the source code to be built. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">buildspec<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The build spec declaration to use for this build project&#39;s related builds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">git<wbr>Clone<wbr>Depth<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Truncate git history to this many commits.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">git<wbr>Submodules<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsecondarysourcegitsubmodulesconfig">Dict[Project<wbr>Secondary<wbr>Source<wbr>Git<wbr>Submodules<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Information about the Git submodules configuration for an AWS CodeBuild build project. Git submodules config blocks are documented below. This option is only valid when the `type` is `CODECOMMIT`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">insecure<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Ignore SSL warnings when connecting to source control.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">report<wbr>Build<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Set to `true` to report the status of a build&#39;s start and finish to your source provider. This option is only valid when your source provider is `GITHUB`, `BITBUCKET`, or `GITHUB_ENTERPRISE`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">source<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The source identifier. Source data will be put inside a folder named as this parameter inside AWS CodeBuild source directory
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ProjectSecondarySourceAuth
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectSecondarySourceAuth">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectSecondarySourceAuth">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectSecondarySourceAuthArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectSecondarySourceAuthOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectSecondarySourceAuthArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectSecondarySourceAuth.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Resource<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The resource value that applies to the specified authorization type.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Resource<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The resource value that applies to the specified authorization type.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">resource<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The resource value that applies to the specified authorization type.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">resource<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resource value that applies to the specified authorization type.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ProjectSecondarySourceGitSubmodulesConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectSecondarySourceGitSubmodulesConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectSecondarySourceGitSubmodulesConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectSecondarySourceGitSubmodulesConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectSecondarySourceGitSubmodulesConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectSecondarySourceGitSubmodulesConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectSecondarySourceGitSubmodulesConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Fetch<wbr>Submodules<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set to true, fetches Git submodules for the AWS CodeBuild build project.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Fetch<wbr>Submodules<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set to true, fetches Git submodules for the AWS CodeBuild build project.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">fetch<wbr>Submodules<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If set to true, fetches Git submodules for the AWS CodeBuild build project.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">fetch<wbr>Submodules<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set to true, fetches Git submodules for the AWS CodeBuild build project.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ProjectSource
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectSource">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectSource">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectSourceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectSourceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectSourceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectSource.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Auths<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsourceauth">List&lt;Project<wbr>Source<wbr>Auth<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Information about the authorization settings for AWS CodeBuild to access the source code to be built. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Buildspec<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The build spec declaration to use for this build project&#39;s related builds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Git<wbr>Clone<wbr>Depth<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Truncate git history to this many commits.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Git<wbr>Submodules<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsourcegitsubmodulesconfig">Project<wbr>Source<wbr>Git<wbr>Submodules<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Information about the Git submodules configuration for an AWS CodeBuild build project. Git submodules config blocks are documented below. This option is only valid when the `type` is `CODECOMMIT`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Insecure<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Ignore SSL warnings when connecting to source control.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Report<wbr>Build<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Set to `true` to report the status of a build&#39;s start and finish to your source provider. This option is only valid when your source provider is `GITHUB`, `BITBUCKET`, or `GITHUB_ENTERPRISE`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Auths<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsourceauth">[]Project<wbr>Source<wbr>Auth</a></span>
    </dt>
    <dd>{{% md %}}Information about the authorization settings for AWS CodeBuild to access the source code to be built. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Buildspec<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The build spec declaration to use for this build project&#39;s related builds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Git<wbr>Clone<wbr>Depth<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Truncate git history to this many commits.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Git<wbr>Submodules<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsourcegitsubmodulesconfig">*Project<wbr>Source<wbr>Git<wbr>Submodules<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Information about the Git submodules configuration for an AWS CodeBuild build project. Git submodules config blocks are documented below. This option is only valid when the `type` is `CODECOMMIT`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Insecure<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Ignore SSL warnings when connecting to source control.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Report<wbr>Build<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Set to `true` to report the status of a build&#39;s start and finish to your source provider. This option is only valid when your source provider is `GITHUB`, `BITBUCKET`, or `GITHUB_ENTERPRISE`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">auths<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsourceauth">Project<wbr>Source<wbr>Auth[]?</a></span>
    </dt>
    <dd>{{% md %}}Information about the authorization settings for AWS CodeBuild to access the source code to be built. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">buildspec<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The build spec declaration to use for this build project&#39;s related builds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">git<wbr>Clone<wbr>Depth<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Truncate git history to this many commits.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">git<wbr>Submodules<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsourcegitsubmodulesconfig">Project<wbr>Source<wbr>Git<wbr>Submodules<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Information about the Git submodules configuration for an AWS CodeBuild build project. Git submodules config blocks are documented below. This option is only valid when the `type` is `CODECOMMIT`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">insecure<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Ignore SSL warnings when connecting to source control.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">report<wbr>Build<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Set to `true` to report the status of a build&#39;s start and finish to your source provider. This option is only valid when your source provider is `GITHUB`, `BITBUCKET`, or `GITHUB_ENTERPRISE`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">auths<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsourceauth">List[Project<wbr>Source<wbr>Auth]</a></span>
    </dt>
    <dd>{{% md %}}Information about the authorization settings for AWS CodeBuild to access the source code to be built. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">buildspec<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The build spec declaration to use for this build project&#39;s related builds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">git<wbr>Clone<wbr>Depth<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Truncate git history to this many commits.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">git<wbr>Submodules<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#projectsourcegitsubmodulesconfig">Dict[Project<wbr>Source<wbr>Git<wbr>Submodules<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Information about the Git submodules configuration for an AWS CodeBuild build project. Git submodules config blocks are documented below. This option is only valid when the `type` is `CODECOMMIT`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">insecure<wbr>Ssl<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Ignore SSL warnings when connecting to source control.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The location of the source code from git or s3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">report<wbr>Build<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Set to `true` to report the status of a build&#39;s start and finish to your source provider. This option is only valid when your source provider is `GITHUB`, `BITBUCKET`, or `GITHUB_ENTERPRISE`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ProjectSourceAuth
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectSourceAuth">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectSourceAuth">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectSourceAuthArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectSourceAuthOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectSourceAuthArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectSourceAuth.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Resource<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The resource value that applies to the specified authorization type.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Resource<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The resource value that applies to the specified authorization type.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">resource<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The resource value that applies to the specified authorization type.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">resource<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resource value that applies to the specified authorization type.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of repository that contains the source code to be built. Valid values for this parameter are: `CODECOMMIT`, `CODEPIPELINE`, `GITHUB`, `GITHUB_ENTERPRISE`, `BITBUCKET` or `S3`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ProjectSourceGitSubmodulesConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectSourceGitSubmodulesConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectSourceGitSubmodulesConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectSourceGitSubmodulesConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectSourceGitSubmodulesConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectSourceGitSubmodulesConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectSourceGitSubmodulesConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Fetch<wbr>Submodules<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set to true, fetches Git submodules for the AWS CodeBuild build project.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Fetch<wbr>Submodules<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set to true, fetches Git submodules for the AWS CodeBuild build project.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">fetch<wbr>Submodules<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If set to true, fetches Git submodules for the AWS CodeBuild build project.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">fetch<wbr>Submodules<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set to true, fetches Git submodules for the AWS CodeBuild build project.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ProjectVpcConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ProjectVpcConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ProjectVpcConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectVpcConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#ProjectVpcConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectVpcConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.ProjectVpcConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The security group IDs to assign to running builds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnets<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The subnet IDs within which to run builds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC within which to run builds.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The security group IDs to assign to running builds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnets<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The subnet IDs within which to run builds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC within which to run builds.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The security group IDs to assign to running builds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnets<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The subnet IDs within which to run builds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC within which to run builds.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The security group IDs to assign to running builds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnets<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The subnet IDs within which to run builds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC within which to run builds.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








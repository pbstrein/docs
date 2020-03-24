
---
title: "Trigger"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Configuration for an automated build in response to source repository changes.


To get more information about Trigger, see:

* [API documentation](https://cloud.google.com/cloud-build/docs/api/reference/rest/)
* How-to Guides
    * [Automating builds using build triggers](https://cloud.google.com/cloud-build/docs/running-builds/automate-builds)

## Example Usage - Cloudbuild Trigger Filename


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const filename_trigger = new gcp.cloudbuild.Trigger("filename-trigger", {
    filename: "cloudbuild.yaml",
    substitutions: {
        _BAZ: "qux",
        _FOO: "bar",
    },
    triggerTemplate: {
        branchName: "master",
        repoName: "my-repo",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/cloudbuild_trigger.html.markdown.



## Create a Trigger Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/cloudbuild/#Trigger">Trigger</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/cloudbuild/#TriggerArgs">TriggerArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Trigger</span><span class="p">(resource_name, opts=None, </span>build=None<span class="p">, </span>description=None<span class="p">, </span>disabled=None<span class="p">, </span>filename=None<span class="p">, </span>github=None<span class="p">, </span>ignored_files=None<span class="p">, </span>included_files=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>substitutions=None<span class="p">, </span>trigger_template=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewTrigger<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerArgs">TriggerArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#Trigger">Trigger</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.Trigger.html">Trigger</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerArgs.html">TriggerArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Trigger resource with the given unique name, arguments, and options.

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
            <td class="align-top">Build</td>
            <td class="align-top">
                
                <code><a href="#triggerbuild">Trigger<wbr>Build<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contents of the build template. Either a filename or build template must be provided.
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
Human-readable description of the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the trigger is disabled or not. If true, the trigger will never result in a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filename</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Path, from the source root, to a file whose contents is used for the template. Either a filename or build template must
be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Github</td>
            <td class="align-top">
                
                <code><a href="#triggergithub">Trigger<wbr>Github<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the configuration of a trigger that creates a build whenever a GitHub event is received. One of
&#39;trigger_template&#39; or &#39;github&#39; must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ignored<wbr>Files</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If ignoredFiles and changed files are both empty, then they are not used to determine whether or not
to trigger a build. If ignoredFiles is not empty, then we ignore any files that match any of the ignored_file globs. If
the change has no files that are outside of the ignoredFiles globs, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Included<wbr>Files</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If any of the files altered in the commit pass the ignoredFiles filter and includedFiles is empty,
then as far as this filter is concerned, we should trigger the build. If any of the files altered in the commit pass the
ignoredFiles filter and includedFiles is not empty, then we make sure that at least one of those files matches a
includedFiles glob. If not, then we do not trigger a build.
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
Name of the trigger. Must be unique within the project.
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
            <td class="align-top">Substitutions</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Substitutions data for Build resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trigger<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#triggertriggertemplate">Trigger<wbr>Trigger<wbr>Template<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Template describing the types of source changes to trigger a build. Branch and tag names in trigger templates are
interpreted as regular expressions. Any branch or tag change that matches that regular expression will trigger a build.
One of &#39;trigger_template&#39; or &#39;github&#39; must be provided.
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
            <td class="align-top">Build</td>
            <td class="align-top">
                
                <code><a href="#triggerbuild">*Trigger<wbr>Build</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contents of the build template. Either a filename or build template must be provided.
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
Human-readable description of the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the trigger is disabled or not. If true, the trigger will never result in a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filename</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Path, from the source root, to a file whose contents is used for the template. Either a filename or build template must
be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Github</td>
            <td class="align-top">
                
                <code><a href="#triggergithub">*Trigger<wbr>Github</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the configuration of a trigger that creates a build whenever a GitHub event is received. One of
&#39;trigger_template&#39; or &#39;github&#39; must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ignored<wbr>Files</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If ignoredFiles and changed files are both empty, then they are not used to determine whether or not
to trigger a build. If ignoredFiles is not empty, then we ignore any files that match any of the ignored_file globs. If
the change has no files that are outside of the ignoredFiles globs, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Included<wbr>Files</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If any of the files altered in the commit pass the ignoredFiles filter and includedFiles is empty,
then as far as this filter is concerned, we should trigger the build. If any of the files altered in the commit pass the
ignoredFiles filter and includedFiles is not empty, then we make sure that at least one of those files matches a
includedFiles glob. If not, then we do not trigger a build.
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
Name of the trigger. Must be unique within the project.
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
            <td class="align-top">Substitutions</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Substitutions data for Build resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trigger<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#triggertriggertemplate">*Trigger<wbr>Trigger<wbr>Template</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Template describing the types of source changes to trigger a build. Branch and tag names in trigger templates are
interpreted as regular expressions. Any branch or tag change that matches that regular expression will trigger a build.
One of &#39;trigger_template&#39; or &#39;github&#39; must be provided.
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
            <td class="align-top">build</td>
            <td class="align-top">
                
                <code><a href="#triggerbuild">Trigger<wbr>Build?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contents of the build template. Either a filename or build template must be provided.
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
Human-readable description of the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the trigger is disabled or not. If true, the trigger will never result in a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filename</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Path, from the source root, to a file whose contents is used for the template. Either a filename or build template must
be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">github</td>
            <td class="align-top">
                
                <code><a href="#triggergithub">Trigger<wbr>Github?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the configuration of a trigger that creates a build whenever a GitHub event is received. One of
&#39;trigger_template&#39; or &#39;github&#39; must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ignored<wbr>Files</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If ignoredFiles and changed files are both empty, then they are not used to determine whether or not
to trigger a build. If ignoredFiles is not empty, then we ignore any files that match any of the ignored_file globs. If
the change has no files that are outside of the ignoredFiles globs, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">included<wbr>Files</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If any of the files altered in the commit pass the ignoredFiles filter and includedFiles is empty,
then as far as this filter is concerned, we should trigger the build. If any of the files altered in the commit pass the
ignoredFiles filter and includedFiles is not empty, then we make sure that at least one of those files matches a
includedFiles glob. If not, then we do not trigger a build.
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
Name of the trigger. Must be unique within the project.
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
            <td class="align-top">substitutions</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Substitutions data for Build resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trigger<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#triggertriggertemplate">Trigger<wbr>Trigger<wbr>Template?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Template describing the types of source changes to trigger a build. Branch and tag names in trigger templates are
interpreted as regular expressions. Any branch or tag change that matches that regular expression will trigger a build.
One of &#39;trigger_template&#39; or &#39;github&#39; must be provided.
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
            <td class="align-top">build</td>
            <td class="align-top">
                
                <code><a href="#triggerbuild">Dict[Trigger<wbr>Build]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contents of the build template. Either a filename or build template must be provided.
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
Human-readable description of the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the trigger is disabled or not. If true, the trigger will never result in a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filename</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Path, from the source root, to a file whose contents is used for the template. Either a filename or build template must
be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">github</td>
            <td class="align-top">
                
                <code><a href="#triggergithub">Dict[Trigger<wbr>Github]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the configuration of a trigger that creates a build whenever a GitHub event is received. One of
&#39;trigger_template&#39; or &#39;github&#39; must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ignored_<wbr>files</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If ignoredFiles and changed files are both empty, then they are not used to determine whether or not
to trigger a build. If ignoredFiles is not empty, then we ignore any files that match any of the ignored_file globs. If
the change has no files that are outside of the ignoredFiles globs, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">included_<wbr>files</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If any of the files altered in the commit pass the ignoredFiles filter and includedFiles is empty,
then as far as this filter is concerned, we should trigger the build. If any of the files altered in the commit pass the
ignoredFiles filter and includedFiles is not empty, then we make sure that at least one of those files matches a
includedFiles glob. If not, then we do not trigger a build.
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
Name of the trigger. Must be unique within the project.
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
            <td class="align-top">substitutions</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Substitutions data for Build resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trigger_<wbr>template</td>
            <td class="align-top">
                
                <code><a href="#triggertriggertemplate">Dict[Trigger<wbr>Trigger<wbr>Template]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Template describing the types of source changes to trigger a build. Branch and tag names in trigger templates are
interpreted as regular expressions. Any branch or tag change that matches that regular expression will trigger a build.
One of &#39;trigger_template&#39; or &#39;github&#39; must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Trigger Output Properties

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
            <td class="align-top">Build</td>
            <td class="align-top">
                
                <code><a href="#triggerbuild">Trigger<wbr>Build?</a></code>
            </td>
            <td class="align-top">{{% md %}} Contents of the build template. Either a filename or build template must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Time when the trigger was created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Human-readable description of the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether the trigger is disabled or not. If true, the trigger will never result in a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filename</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Path, from the source root, to a file whose contents is used for the template. Either a filename or build template must
be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Github</td>
            <td class="align-top">
                
                <code><a href="#triggergithub">Trigger<wbr>Github?</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes the configuration of a trigger that creates a build whenever a GitHub event is received. One of
&#39;trigger_template&#39; or &#39;github&#39; must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ignored<wbr>Files</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If ignoredFiles and changed files are both empty, then they are not used to determine whether or not
to trigger a build. If ignoredFiles is not empty, then we ignore any files that match any of the ignored_file globs. If
the change has no files that are outside of the ignoredFiles globs, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Included<wbr>Files</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If any of the files altered in the commit pass the ignoredFiles filter and includedFiles is empty,
then as far as this filter is concerned, we should trigger the build. If any of the files altered in the commit pass the
ignoredFiles filter and includedFiles is not empty, then we make sure that at least one of those files matches a
includedFiles glob. If not, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the trigger. Must be unique within the project.
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
            <td class="align-top">Substitutions</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} Substitutions data for Build resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trigger<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique identifier for the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trigger<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#triggertriggertemplate">Trigger<wbr>Trigger<wbr>Template?</a></code>
            </td>
            <td class="align-top">{{% md %}} Template describing the types of source changes to trigger a build. Branch and tag names in trigger templates are
interpreted as regular expressions. Any branch or tag change that matches that regular expression will trigger a build.
One of &#39;trigger_template&#39; or &#39;github&#39; must be provided.
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
            <td class="align-top">Build</td>
            <td class="align-top">
                
                <code><a href="#triggerbuild">*Trigger<wbr>Build</a></code>
            </td>
            <td class="align-top">{{% md %}} Contents of the build template. Either a filename or build template must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Time when the trigger was created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Human-readable description of the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether the trigger is disabled or not. If true, the trigger will never result in a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filename</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Path, from the source root, to a file whose contents is used for the template. Either a filename or build template must
be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Github</td>
            <td class="align-top">
                
                <code><a href="#triggergithub">*Trigger<wbr>Github</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes the configuration of a trigger that creates a build whenever a GitHub event is received. One of
&#39;trigger_template&#39; or &#39;github&#39; must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ignored<wbr>Files</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If ignoredFiles and changed files are both empty, then they are not used to determine whether or not
to trigger a build. If ignoredFiles is not empty, then we ignore any files that match any of the ignored_file globs. If
the change has no files that are outside of the ignoredFiles globs, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Included<wbr>Files</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If any of the files altered in the commit pass the ignoredFiles filter and includedFiles is empty,
then as far as this filter is concerned, we should trigger the build. If any of the files altered in the commit pass the
ignoredFiles filter and includedFiles is not empty, then we make sure that at least one of those files matches a
includedFiles glob. If not, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the trigger. Must be unique within the project.
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
            <td class="align-top">Substitutions</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} Substitutions data for Build resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trigger<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique identifier for the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trigger<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#triggertriggertemplate">*Trigger<wbr>Trigger<wbr>Template</a></code>
            </td>
            <td class="align-top">{{% md %}} Template describing the types of source changes to trigger a build. Branch and tag names in trigger templates are
interpreted as regular expressions. Any branch or tag change that matches that regular expression will trigger a build.
One of &#39;trigger_template&#39; or &#39;github&#39; must be provided.
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
            <td class="align-top">build</td>
            <td class="align-top">
                
                <code><a href="#triggerbuild">Trigger<wbr>Build?</a></code>
            </td>
            <td class="align-top">{{% md %}} Contents of the build template. Either a filename or build template must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">create<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Time when the trigger was created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Human-readable description of the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether the trigger is disabled or not. If true, the trigger will never result in a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filename</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Path, from the source root, to a file whose contents is used for the template. Either a filename or build template must
be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">github</td>
            <td class="align-top">
                
                <code><a href="#triggergithub">Trigger<wbr>Github?</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes the configuration of a trigger that creates a build whenever a GitHub event is received. One of
&#39;trigger_template&#39; or &#39;github&#39; must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ignored<wbr>Files</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If ignoredFiles and changed files are both empty, then they are not used to determine whether or not
to trigger a build. If ignoredFiles is not empty, then we ignore any files that match any of the ignored_file globs. If
the change has no files that are outside of the ignoredFiles globs, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">included<wbr>Files</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If any of the files altered in the commit pass the ignoredFiles filter and includedFiles is empty,
then as far as this filter is concerned, we should trigger the build. If any of the files altered in the commit pass the
ignoredFiles filter and includedFiles is not empty, then we make sure that at least one of those files matches a
includedFiles glob. If not, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the trigger. Must be unique within the project.
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
            <td class="align-top">substitutions</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} Substitutions data for Build resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trigger<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique identifier for the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trigger<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#triggertriggertemplate">Trigger<wbr>Trigger<wbr>Template?</a></code>
            </td>
            <td class="align-top">{{% md %}} Template describing the types of source changes to trigger a build. Branch and tag names in trigger templates are
interpreted as regular expressions. Any branch or tag change that matches that regular expression will trigger a build.
One of &#39;trigger_template&#39; or &#39;github&#39; must be provided.
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
            <td class="align-top">build</td>
            <td class="align-top">
                
                <code><a href="#triggerbuild">Dict[Trigger<wbr>Build]</a></code>
            </td>
            <td class="align-top">{{% md %}} Contents of the build template. Either a filename or build template must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">create_<wbr>time</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Time when the trigger was created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Human-readable description of the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether the trigger is disabled or not. If true, the trigger will never result in a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filename</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Path, from the source root, to a file whose contents is used for the template. Either a filename or build template must
be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">github</td>
            <td class="align-top">
                
                <code><a href="#triggergithub">Dict[Trigger<wbr>Github]</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes the configuration of a trigger that creates a build whenever a GitHub event is received. One of
&#39;trigger_template&#39; or &#39;github&#39; must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ignored_<wbr>files</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If ignoredFiles and changed files are both empty, then they are not used to determine whether or not
to trigger a build. If ignoredFiles is not empty, then we ignore any files that match any of the ignored_file globs. If
the change has no files that are outside of the ignoredFiles globs, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">included_<wbr>files</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If any of the files altered in the commit pass the ignoredFiles filter and includedFiles is empty,
then as far as this filter is concerned, we should trigger the build. If any of the files altered in the commit pass the
ignoredFiles filter and includedFiles is not empty, then we make sure that at least one of those files matches a
includedFiles glob. If not, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Name of the trigger. Must be unique within the project.
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
            <td class="align-top">substitutions</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} Substitutions data for Build resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trigger_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The unique identifier for the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trigger_<wbr>template</td>
            <td class="align-top">
                
                <code><a href="#triggertriggertemplate">Dict[Trigger<wbr>Trigger<wbr>Template]</a></code>
            </td>
            <td class="align-top">{{% md %}} Template describing the types of source changes to trigger a build. Branch and tag names in trigger templates are
interpreted as regular expressions. Any branch or tag change that matches that regular expression will trigger a build.
One of &#39;trigger_template&#39; or &#39;github&#39; must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Trigger Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/cloudbuild/#TriggerState">TriggerState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/cloudbuild/#Trigger">Trigger</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>build=None<span class="p">, </span>create_time=None<span class="p">, </span>description=None<span class="p">, </span>disabled=None<span class="p">, </span>filename=None<span class="p">, </span>github=None<span class="p">, </span>ignored_files=None<span class="p">, </span>included_files=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>substitutions=None<span class="p">, </span>trigger_id=None<span class="p">, </span>trigger_template=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetTrigger<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerState">TriggerState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#Trigger">Trigger</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.Trigger.html">Trigger</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerState.html">TriggerState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Trigger resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Build</td>
            <td class="align-top">
                
                <code><a href="#triggerbuild">Trigger<wbr>Build<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contents of the build template. Either a filename or build template must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time when the trigger was created.
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
Human-readable description of the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the trigger is disabled or not. If true, the trigger will never result in a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filename</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Path, from the source root, to a file whose contents is used for the template. Either a filename or build template must
be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Github</td>
            <td class="align-top">
                
                <code><a href="#triggergithub">Trigger<wbr>Github<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the configuration of a trigger that creates a build whenever a GitHub event is received. One of
&#39;trigger_template&#39; or &#39;github&#39; must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ignored<wbr>Files</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If ignoredFiles and changed files are both empty, then they are not used to determine whether or not
to trigger a build. If ignoredFiles is not empty, then we ignore any files that match any of the ignored_file globs. If
the change has no files that are outside of the ignoredFiles globs, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Included<wbr>Files</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If any of the files altered in the commit pass the ignoredFiles filter and includedFiles is empty,
then as far as this filter is concerned, we should trigger the build. If any of the files altered in the commit pass the
ignoredFiles filter and includedFiles is not empty, then we make sure that at least one of those files matches a
includedFiles glob. If not, then we do not trigger a build.
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
Name of the trigger. Must be unique within the project.
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
            <td class="align-top">Substitutions</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Substitutions data for Build resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trigger<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique identifier for the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trigger<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#triggertriggertemplate">Trigger<wbr>Trigger<wbr>Template<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Template describing the types of source changes to trigger a build. Branch and tag names in trigger templates are
interpreted as regular expressions. Any branch or tag change that matches that regular expression will trigger a build.
One of &#39;trigger_template&#39; or &#39;github&#39; must be provided.
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
            <td class="align-top">Build</td>
            <td class="align-top">
                
                <code><a href="#triggerbuild">*Trigger<wbr>Build</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contents of the build template. Either a filename or build template must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time when the trigger was created.
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
Human-readable description of the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the trigger is disabled or not. If true, the trigger will never result in a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filename</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Path, from the source root, to a file whose contents is used for the template. Either a filename or build template must
be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Github</td>
            <td class="align-top">
                
                <code><a href="#triggergithub">*Trigger<wbr>Github</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the configuration of a trigger that creates a build whenever a GitHub event is received. One of
&#39;trigger_template&#39; or &#39;github&#39; must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ignored<wbr>Files</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If ignoredFiles and changed files are both empty, then they are not used to determine whether or not
to trigger a build. If ignoredFiles is not empty, then we ignore any files that match any of the ignored_file globs. If
the change has no files that are outside of the ignoredFiles globs, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Included<wbr>Files</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If any of the files altered in the commit pass the ignoredFiles filter and includedFiles is empty,
then as far as this filter is concerned, we should trigger the build. If any of the files altered in the commit pass the
ignoredFiles filter and includedFiles is not empty, then we make sure that at least one of those files matches a
includedFiles glob. If not, then we do not trigger a build.
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
Name of the trigger. Must be unique within the project.
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
            <td class="align-top">Substitutions</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Substitutions data for Build resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trigger<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique identifier for the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trigger<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#triggertriggertemplate">*Trigger<wbr>Trigger<wbr>Template</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Template describing the types of source changes to trigger a build. Branch and tag names in trigger templates are
interpreted as regular expressions. Any branch or tag change that matches that regular expression will trigger a build.
One of &#39;trigger_template&#39; or &#39;github&#39; must be provided.
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
            <td class="align-top">build</td>
            <td class="align-top">
                
                <code><a href="#triggerbuild">Trigger<wbr>Build?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contents of the build template. Either a filename or build template must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">create<wbr>Time</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time when the trigger was created.
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
Human-readable description of the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the trigger is disabled or not. If true, the trigger will never result in a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filename</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Path, from the source root, to a file whose contents is used for the template. Either a filename or build template must
be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">github</td>
            <td class="align-top">
                
                <code><a href="#triggergithub">Trigger<wbr>Github?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the configuration of a trigger that creates a build whenever a GitHub event is received. One of
&#39;trigger_template&#39; or &#39;github&#39; must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ignored<wbr>Files</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If ignoredFiles and changed files are both empty, then they are not used to determine whether or not
to trigger a build. If ignoredFiles is not empty, then we ignore any files that match any of the ignored_file globs. If
the change has no files that are outside of the ignoredFiles globs, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">included<wbr>Files</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If any of the files altered in the commit pass the ignoredFiles filter and includedFiles is empty,
then as far as this filter is concerned, we should trigger the build. If any of the files altered in the commit pass the
ignoredFiles filter and includedFiles is not empty, then we make sure that at least one of those files matches a
includedFiles glob. If not, then we do not trigger a build.
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
Name of the trigger. Must be unique within the project.
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
            <td class="align-top">substitutions</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Substitutions data for Build resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trigger<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique identifier for the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trigger<wbr>Template</td>
            <td class="align-top">
                
                <code><a href="#triggertriggertemplate">Trigger<wbr>Trigger<wbr>Template?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Template describing the types of source changes to trigger a build. Branch and tag names in trigger templates are
interpreted as regular expressions. Any branch or tag change that matches that regular expression will trigger a build.
One of &#39;trigger_template&#39; or &#39;github&#39; must be provided.
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
            <td class="align-top">build</td>
            <td class="align-top">
                
                <code><a href="#triggerbuild">Dict[Trigger<wbr>Build]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Contents of the build template. Either a filename or build template must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">create_<wbr>time</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time when the trigger was created.
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
Human-readable description of the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the trigger is disabled or not. If true, the trigger will never result in a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filename</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Path, from the source root, to a file whose contents is used for the template. Either a filename or build template must
be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">github</td>
            <td class="align-top">
                
                <code><a href="#triggergithub">Dict[Trigger<wbr>Github]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the configuration of a trigger that creates a build whenever a GitHub event is received. One of
&#39;trigger_template&#39; or &#39;github&#39; must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ignored_<wbr>files</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If ignoredFiles and changed files are both empty, then they are not used to determine whether or not
to trigger a build. If ignoredFiles is not empty, then we ignore any files that match any of the ignored_file globs. If
the change has no files that are outside of the ignoredFiles globs, then we do not trigger a build.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">included_<wbr>files</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ignoredFiles and includedFiles are file glob matches using https://golang.org/pkg/path/filepath/#Match extended with
support for &#39;**&#39;. If any of the files altered in the commit pass the ignoredFiles filter and includedFiles is empty,
then as far as this filter is concerned, we should trigger the build. If any of the files altered in the commit pass the
ignoredFiles filter and includedFiles is not empty, then we make sure that at least one of those files matches a
includedFiles glob. If not, then we do not trigger a build.
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
Name of the trigger. Must be unique within the project.
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
            <td class="align-top">substitutions</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Substitutions data for Build resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trigger_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique identifier for the trigger.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trigger_<wbr>template</td>
            <td class="align-top">
                
                <code><a href="#triggertriggertemplate">Dict[Trigger<wbr>Trigger<wbr>Template]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Template describing the types of source changes to trigger a build. Branch and tag names in trigger templates are
interpreted as regular expressions. Any branch or tag change that matches that regular expression will trigger a build.
One of &#39;trigger_template&#39; or &#39;github&#39; must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### TriggerBuild
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TriggerBuild">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TriggerBuild">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerBuildArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerBuildOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerBuildArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerBuild.html">output</a> API doc for this type.
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
            <td class="align-top">Images</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Steps</td>
            <td class="align-top">
                
                <code><a href="#triggerbuildstep">List&lt;Trigger<wbr>Build<wbr>Step<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Images</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Steps</td>
            <td class="align-top">
                
                <code><a href="#triggerbuildstep">[]Trigger<wbr>Build<wbr>Step</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">images</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">steps</td>
            <td class="align-top">
                
                <code><a href="#triggerbuildstep">Trigger<wbr>Build<wbr>Step[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">images</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">steps</td>
            <td class="align-top">
                
                <code><a href="#triggerbuildstep">List[Trigger<wbr>Build<wbr>Step]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### TriggerBuildStep
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TriggerBuildStep">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TriggerBuildStep">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerBuildStepArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerBuildStepOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerBuildStepArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerBuildStep.html">output</a> API doc for this type.
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
            <td class="align-top">Args</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dir</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entrypoint</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Envs</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
an identifier for the resource with format `projects/{{project}}/triggers/{{trigger_id}}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secret<wbr>Envs</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timing</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Volumes</td>
            <td class="align-top">
                
                <code><a href="#triggerbuildstepvolume">List&lt;Trigger<wbr>Build<wbr>Step<wbr>Volume<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Wait<wbr>Fors</td>
            <td class="align-top">
                
                <code>List<string>?</code>
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
            <td class="align-top">Args</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dir</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entrypoint</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Envs</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
an identifier for the resource with format `projects/{{project}}/triggers/{{trigger_id}}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secret<wbr>Envs</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timing</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Volumes</td>
            <td class="align-top">
                
                <code><a href="#triggerbuildstepvolume">[]Trigger<wbr>Build<wbr>Step<wbr>Volume</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Wait<wbr>Fors</td>
            <td class="align-top">
                
                <code>[]string</code>
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
            <td class="align-top">args</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dir</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entrypoint</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">envs</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
an identifier for the resource with format `projects/{{project}}/triggers/{{trigger_id}}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secret<wbr>Envs</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timing</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">volumes</td>
            <td class="align-top">
                
                <code><a href="#triggerbuildstepvolume">Trigger<wbr>Build<wbr>Step<wbr>Volume[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">wait<wbr>Fors</td>
            <td class="align-top">
                
                <code>string[]?</code>
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
            <td class="align-top">args</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dir</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entrypoint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">envs</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
an identifier for the resource with format `projects/{{project}}/triggers/{{trigger_id}}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secret<wbr>Envs</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timing</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">volumes</td>
            <td class="align-top">
                
                <code><a href="#triggerbuildstepvolume">List[Trigger<wbr>Build<wbr>Step<wbr>Volume]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">wait<wbr>Fors</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### TriggerBuildStepVolume
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TriggerBuildStepVolume">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TriggerBuildStepVolume">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerBuildStepVolumeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerBuildStepVolumeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerBuildStepVolumeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerBuildStepVolume.html">output</a> API doc for this type.
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
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Path</td>
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
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Path</td>
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
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">path</td>
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
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">path</td>
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





#### TriggerGithub
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TriggerGithub">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TriggerGithub">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerGithubArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerGithubOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerGithubArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerGithub.html">output</a> API doc for this type.
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
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Owner</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pull<wbr>Request</td>
            <td class="align-top">
                
                <code><a href="#triggergithubpullrequest">Trigger<wbr>Github<wbr>Pull<wbr>Request<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Push</td>
            <td class="align-top">
                
                <code><a href="#triggergithubpush">Trigger<wbr>Github<wbr>Push<wbr>Args?</a></code>
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
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Owner</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pull<wbr>Request</td>
            <td class="align-top">
                
                <code><a href="#triggergithubpullrequest">*Trigger<wbr>Github<wbr>Pull<wbr>Request</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Push</td>
            <td class="align-top">
                
                <code><a href="#triggergithubpush">*Trigger<wbr>Github<wbr>Push</a></code>
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
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">owner</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pull<wbr>Request</td>
            <td class="align-top">
                
                <code><a href="#triggergithubpullrequest">Trigger<wbr>Github<wbr>Pull<wbr>Request?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">push</td>
            <td class="align-top">
                
                <code><a href="#triggergithubpush">Trigger<wbr>Github<wbr>Push?</a></code>
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
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">owner</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pull<wbr>Request</td>
            <td class="align-top">
                
                <code><a href="#triggergithubpullrequest">Dict[Trigger<wbr>Github<wbr>Pull<wbr>Request]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">push</td>
            <td class="align-top">
                
                <code><a href="#triggergithubpush">Dict[Trigger<wbr>Github<wbr>Push]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### TriggerGithubPullRequest
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TriggerGithubPullRequest">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TriggerGithubPullRequest">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerGithubPullRequestArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerGithubPullRequestOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerGithubPullRequestArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerGithubPullRequest.html">output</a> API doc for this type.
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
            <td class="align-top">Branch</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Comment<wbr>Control</td>
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
            <td class="align-top">Branch</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Comment<wbr>Control</td>
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
            <td class="align-top">branch</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">comment<wbr>Control</td>
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
            <td class="align-top">branch</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">comment<wbr>Control</td>
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





#### TriggerGithubPush
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TriggerGithubPush">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TriggerGithubPush">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerGithubPushArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerGithubPushOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerGithubPushArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerGithubPush.html">output</a> API doc for this type.
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
            <td class="align-top">Branch</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tag</td>
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
            <td class="align-top">Branch</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tag</td>
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
            <td class="align-top">branch</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tag</td>
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
            <td class="align-top">branch</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tag</td>
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





#### TriggerTriggerTemplate
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TriggerTriggerTemplate">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TriggerTriggerTemplate">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerTriggerTemplateArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/cloudbuild?tab=doc#TriggerTriggerTemplateOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerTriggerTemplateArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Cloudbuild.TriggerTriggerTemplate.html">output</a> API doc for this type.
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
            <td class="align-top">Branch<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Commit<wbr>Sha</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dir</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Repo<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tag<wbr>Name</td>
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
            <td class="align-top">Branch<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Commit<wbr>Sha</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dir</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Repo<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tag<wbr>Name</td>
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
            <td class="align-top">branch<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">commit<wbr>Sha</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dir</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">repo<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tag<wbr>Name</td>
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
            <td class="align-top">branch<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">commit<wbr>Sha</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dir</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">repo<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tag<wbr>Name</td>
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








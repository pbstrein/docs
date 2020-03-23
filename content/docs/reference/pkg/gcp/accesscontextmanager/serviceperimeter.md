
---
title: "ServicePerimeter"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

ServicePerimeter describes a set of GCP resources which can freely import
and export data amongst themselves, but not export outside of the
ServicePerimeter. If a request with a source within this ServicePerimeter
has a target outside of the ServicePerimeter, the request will be blocked.
Otherwise the request is allowed. There are two types of Service Perimeter
- Regular and Bridge. Regular Service Perimeters cannot overlap, a single
GCP project can only belong to a single regular Service Perimeter. Service
Perimeter Bridges can contain only GCP projects as members, a single GCP
project may belong to multiple Service Perimeter Bridges.


To get more information about ServicePerimeter, see:

* [API documentation](https://cloud.google.com/access-context-manager/docs/reference/rest/v1/accessPolicies.servicePerimeters)
* How-to Guides
    * [Service Perimeter Quickstart](https://cloud.google.com/vpc-service-controls/docs/quickstart)

## Example Usage - Access Context Manager Service Perimeter Basic


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const access_policy = new gcp.accesscontextmanager.AccessPolicy("access-policy", {
    parent: "organizations/123456789",
    title: "my policy",
});
const service_perimeter = new gcp.accesscontextmanager.ServicePerimeter("service-perimeter", {
    parent: pulumi.interpolate`accessPolicies/${access_policy.name}`,
    status: {
        restrictedServices: ["storage.googleapis.com"],
    },
    title: "restrict_all",
});
const access_level = new gcp.accesscontextmanager.AccessLevel("access-level", {
    basic: {
        conditions: [{
            devicePolicy: {
                osConstraints: [{
                    osType: "DESKTOP_CHROME_OS",
                }],
                requireScreenLock: false,
            },
        }],
    },
    parent: pulumi.interpolate`accessPolicies/${access_policy.name}`,
    title: "chromeos_no_lock",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/access_context_manager_service_perimeter.html.markdown.



## Create a ServicePerimeter Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/accesscontextmanager/#ServicePerimeter">ServicePerimeter</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/accesscontextmanager/#ServicePerimeterArgs">ServicePerimeterArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">ServicePerimeter</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>name=None<span class="p">, </span>parent=None<span class="p">, </span>perimeter_type=None<span class="p">, </span>status=None<span class="p">, </span>title=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewServicePerimeter<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/accesscontextmanager?tab=doc#ServicePerimeterArgs">ServicePerimeterArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/accesscontextmanager?tab=doc#ServicePerimeter">ServicePerimeter</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Accesscontextmanager.ServicePerimeter.html">ServicePerimeter</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Accesscontextmanager.ServicePerimeterArgs.html">ServicePerimeterArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a ServicePerimeter resource with the given unique name, arguments, and options.

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
Description of the ServicePerimeter and its use. Does not affect behavior.
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
Resource name for the ServicePerimeter. The short_name component must begin with a letter and only include alphanumeric
and &#39;_&#39;. Format: accessPolicies/{policy_id}/servicePerimeters/{short_name}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parent</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The AccessPolicy this ServicePerimeter lives in. Format: accessPolicies/{policy_id}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Perimeter<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of the Perimeter. There are two types: regular and bridge. Regular Service Perimeter contains
resources, access levels, and restricted services. Every resource can be in at most ONE regular Service Perimeter. In
addition to being in a regular service perimeter, a resource can also be in zero or more perimeter bridges. A perimeter
bridge only contains resources. Cross project operations are permitted if all effected resources share some perimeter
(whether bridge or regular). Perimeter Bridge does not contain access levels or services: those are governed entirely by
the regular perimeter that resource is in. Perimeter Bridges are typically useful when building more complex topologies
with many independent perimeters that need to share some data with a common perimeter, but should not be able to share
data among themselves.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Status</td>
            <td class="align-top">
                
                <code><a href="#serviceperimeterstatus">Service<wbr>Perimeter<wbr>Status<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ServicePerimeter configuration. Specifies sets of resources, restricted services and access levels that determine
perimeter content and boundaries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Title</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Human readable title. Must be unique within the Policy.
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
Description of the ServicePerimeter and its use. Does not affect behavior.
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
Resource name for the ServicePerimeter. The short_name component must begin with a letter and only include alphanumeric
and &#39;_&#39;. Format: accessPolicies/{policy_id}/servicePerimeters/{short_name}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parent</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The AccessPolicy this ServicePerimeter lives in. Format: accessPolicies/{policy_id}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Perimeter<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of the Perimeter. There are two types: regular and bridge. Regular Service Perimeter contains
resources, access levels, and restricted services. Every resource can be in at most ONE regular Service Perimeter. In
addition to being in a regular service perimeter, a resource can also be in zero or more perimeter bridges. A perimeter
bridge only contains resources. Cross project operations are permitted if all effected resources share some perimeter
(whether bridge or regular). Perimeter Bridge does not contain access levels or services: those are governed entirely by
the regular perimeter that resource is in. Perimeter Bridges are typically useful when building more complex topologies
with many independent perimeters that need to share some data with a common perimeter, but should not be able to share
data among themselves.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Status</td>
            <td class="align-top">
                
                <code><a href="#serviceperimeterstatus">*Service<wbr>Perimeter<wbr>Status</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ServicePerimeter configuration. Specifies sets of resources, restricted services and access levels that determine
perimeter content and boundaries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Title</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Human readable title. Must be unique within the Policy.
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
Description of the ServicePerimeter and its use. Does not affect behavior.
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
Resource name for the ServicePerimeter. The short_name component must begin with a letter and only include alphanumeric
and &#39;_&#39;. Format: accessPolicies/{policy_id}/servicePerimeters/{short_name}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parent</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The AccessPolicy this ServicePerimeter lives in. Format: accessPolicies/{policy_id}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">perimeter<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of the Perimeter. There are two types: regular and bridge. Regular Service Perimeter contains
resources, access levels, and restricted services. Every resource can be in at most ONE regular Service Perimeter. In
addition to being in a regular service perimeter, a resource can also be in zero or more perimeter bridges. A perimeter
bridge only contains resources. Cross project operations are permitted if all effected resources share some perimeter
(whether bridge or regular). Perimeter Bridge does not contain access levels or services: those are governed entirely by
the regular perimeter that resource is in. Perimeter Bridges are typically useful when building more complex topologies
with many independent perimeters that need to share some data with a common perimeter, but should not be able to share
data among themselves.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">status</td>
            <td class="align-top">
                
                <code><a href="#serviceperimeterstatus">Service<wbr>Perimeter<wbr>Status?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ServicePerimeter configuration. Specifies sets of resources, restricted services and access levels that determine
perimeter content and boundaries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">title</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Human readable title. Must be unique within the Policy.
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
Description of the ServicePerimeter and its use. Does not affect behavior.
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
Resource name for the ServicePerimeter. The short_name component must begin with a letter and only include alphanumeric
and &#39;_&#39;. Format: accessPolicies/{policy_id}/servicePerimeters/{short_name}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parent</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The AccessPolicy this ServicePerimeter lives in. Format: accessPolicies/{policy_id}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">perimeter_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of the Perimeter. There are two types: regular and bridge. Regular Service Perimeter contains
resources, access levels, and restricted services. Every resource can be in at most ONE regular Service Perimeter. In
addition to being in a regular service perimeter, a resource can also be in zero or more perimeter bridges. A perimeter
bridge only contains resources. Cross project operations are permitted if all effected resources share some perimeter
(whether bridge or regular). Perimeter Bridge does not contain access levels or services: those are governed entirely by
the regular perimeter that resource is in. Perimeter Bridges are typically useful when building more complex topologies
with many independent perimeters that need to share some data with a common perimeter, but should not be able to share
data among themselves.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">status</td>
            <td class="align-top">
                
                <code><a href="#serviceperimeterstatus">Dict[Service<wbr>Perimeter<wbr>Status]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ServicePerimeter configuration. Specifies sets of resources, restricted services and access levels that determine
perimeter content and boundaries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">title</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Human readable title. Must be unique within the Policy.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## ServicePerimeter Output Properties

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
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Time the AccessPolicy was created in UTC.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Description of the ServicePerimeter and its use. Does not affect behavior.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Resource name for the ServicePerimeter. The short_name component must begin with a letter and only include alphanumeric
and &#39;_&#39;. Format: accessPolicies/{policy_id}/servicePerimeters/{short_name}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parent</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The AccessPolicy this ServicePerimeter lives in. Format: accessPolicies/{policy_id}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Perimeter<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the type of the Perimeter. There are two types: regular and bridge. Regular Service Perimeter contains
resources, access levels, and restricted services. Every resource can be in at most ONE regular Service Perimeter. In
addition to being in a regular service perimeter, a resource can also be in zero or more perimeter bridges. A perimeter
bridge only contains resources. Cross project operations are permitted if all effected resources share some perimeter
(whether bridge or regular). Perimeter Bridge does not contain access levels or services: those are governed entirely by
the regular perimeter that resource is in. Perimeter Bridges are typically useful when building more complex topologies
with many independent perimeters that need to share some data with a common perimeter, but should not be able to share
data among themselves.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Status</td>
            <td class="align-top">
                
                <code><a href="#serviceperimeterstatus">Service<wbr>Perimeter<wbr>Status?</a></code>
            </td>
            <td class="align-top">{{% md %}} ServicePerimeter configuration. Specifies sets of resources, restricted services and access levels that determine
perimeter content and boundaries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Title</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Human readable title. Must be unique within the Policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Update<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Time the AccessPolicy was updated in UTC.
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
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Time the AccessPolicy was created in UTC.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Description of the ServicePerimeter and its use. Does not affect behavior.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Resource name for the ServicePerimeter. The short_name component must begin with a letter and only include alphanumeric
and &#39;_&#39;. Format: accessPolicies/{policy_id}/servicePerimeters/{short_name}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parent</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The AccessPolicy this ServicePerimeter lives in. Format: accessPolicies/{policy_id}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Perimeter<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the type of the Perimeter. There are two types: regular and bridge. Regular Service Perimeter contains
resources, access levels, and restricted services. Every resource can be in at most ONE regular Service Perimeter. In
addition to being in a regular service perimeter, a resource can also be in zero or more perimeter bridges. A perimeter
bridge only contains resources. Cross project operations are permitted if all effected resources share some perimeter
(whether bridge or regular). Perimeter Bridge does not contain access levels or services: those are governed entirely by
the regular perimeter that resource is in. Perimeter Bridges are typically useful when building more complex topologies
with many independent perimeters that need to share some data with a common perimeter, but should not be able to share
data among themselves.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Status</td>
            <td class="align-top">
                
                <code><a href="#serviceperimeterstatus">*Service<wbr>Perimeter<wbr>Status</a></code>
            </td>
            <td class="align-top">{{% md %}} ServicePerimeter configuration. Specifies sets of resources, restricted services and access levels that determine
perimeter content and boundaries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Title</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Human readable title. Must be unique within the Policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Update<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Time the AccessPolicy was updated in UTC.
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
            <td class="align-top">create<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Time the AccessPolicy was created in UTC.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Description of the ServicePerimeter and its use. Does not affect behavior.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Resource name for the ServicePerimeter. The short_name component must begin with a letter and only include alphanumeric
and &#39;_&#39;. Format: accessPolicies/{policy_id}/servicePerimeters/{short_name}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parent</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The AccessPolicy this ServicePerimeter lives in. Format: accessPolicies/{policy_id}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">perimeter<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the type of the Perimeter. There are two types: regular and bridge. Regular Service Perimeter contains
resources, access levels, and restricted services. Every resource can be in at most ONE regular Service Perimeter. In
addition to being in a regular service perimeter, a resource can also be in zero or more perimeter bridges. A perimeter
bridge only contains resources. Cross project operations are permitted if all effected resources share some perimeter
(whether bridge or regular). Perimeter Bridge does not contain access levels or services: those are governed entirely by
the regular perimeter that resource is in. Perimeter Bridges are typically useful when building more complex topologies
with many independent perimeters that need to share some data with a common perimeter, but should not be able to share
data among themselves.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">status</td>
            <td class="align-top">
                
                <code><a href="#serviceperimeterstatus">Service<wbr>Perimeter<wbr>Status?</a></code>
            </td>
            <td class="align-top">{{% md %}} ServicePerimeter configuration. Specifies sets of resources, restricted services and access levels that determine
perimeter content and boundaries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">title</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Human readable title. Must be unique within the Policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">update<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Time the AccessPolicy was updated in UTC.
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
            <td class="align-top">create_<wbr>time</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Time the AccessPolicy was created in UTC.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Description of the ServicePerimeter and its use. Does not affect behavior.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Resource name for the ServicePerimeter. The short_name component must begin with a letter and only include alphanumeric
and &#39;_&#39;. Format: accessPolicies/{policy_id}/servicePerimeters/{short_name}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parent</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The AccessPolicy this ServicePerimeter lives in. Format: accessPolicies/{policy_id}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">perimeter_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the type of the Perimeter. There are two types: regular and bridge. Regular Service Perimeter contains
resources, access levels, and restricted services. Every resource can be in at most ONE regular Service Perimeter. In
addition to being in a regular service perimeter, a resource can also be in zero or more perimeter bridges. A perimeter
bridge only contains resources. Cross project operations are permitted if all effected resources share some perimeter
(whether bridge or regular). Perimeter Bridge does not contain access levels or services: those are governed entirely by
the regular perimeter that resource is in. Perimeter Bridges are typically useful when building more complex topologies
with many independent perimeters that need to share some data with a common perimeter, but should not be able to share
data among themselves.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">status</td>
            <td class="align-top">
                
                <code><a href="#serviceperimeterstatus">Dict[Service<wbr>Perimeter<wbr>Status]</a></code>
            </td>
            <td class="align-top">{{% md %}} ServicePerimeter configuration. Specifies sets of resources, restricted services and access levels that determine
perimeter content and boundaries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">title</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Human readable title. Must be unique within the Policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">update_<wbr>time</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Time the AccessPolicy was updated in UTC.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing ServicePerimeter Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/accesscontextmanager/#ServicePerimeterState">ServicePerimeterState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/accesscontextmanager/#ServicePerimeter">ServicePerimeter</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>create_time=None<span class="p">, </span>description=None<span class="p">, </span>name=None<span class="p">, </span>parent=None<span class="p">, </span>perimeter_type=None<span class="p">, </span>status=None<span class="p">, </span>title=None<span class="p">, </span>update_time=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetServicePerimeter<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/accesscontextmanager?tab=doc#ServicePerimeterState">ServicePerimeterState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/accesscontextmanager?tab=doc#ServicePerimeter">ServicePerimeter</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Accesscontextmanager.ServicePerimeter.html">ServicePerimeter</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Accesscontextmanager.ServicePerimeterState.html">ServicePerimeterState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing ServicePerimeter resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time the AccessPolicy was created in UTC.
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
Description of the ServicePerimeter and its use. Does not affect behavior.
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
Resource name for the ServicePerimeter. The short_name component must begin with a letter and only include alphanumeric
and &#39;_&#39;. Format: accessPolicies/{policy_id}/servicePerimeters/{short_name}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parent</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The AccessPolicy this ServicePerimeter lives in. Format: accessPolicies/{policy_id}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Perimeter<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of the Perimeter. There are two types: regular and bridge. Regular Service Perimeter contains
resources, access levels, and restricted services. Every resource can be in at most ONE regular Service Perimeter. In
addition to being in a regular service perimeter, a resource can also be in zero or more perimeter bridges. A perimeter
bridge only contains resources. Cross project operations are permitted if all effected resources share some perimeter
(whether bridge or regular). Perimeter Bridge does not contain access levels or services: those are governed entirely by
the regular perimeter that resource is in. Perimeter Bridges are typically useful when building more complex topologies
with many independent perimeters that need to share some data with a common perimeter, but should not be able to share
data among themselves.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Status</td>
            <td class="align-top">
                
                <code><a href="#serviceperimeterstatus">Service<wbr>Perimeter<wbr>Status<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ServicePerimeter configuration. Specifies sets of resources, restricted services and access levels that determine
perimeter content and boundaries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Title</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Human readable title. Must be unique within the Policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Update<wbr>Time</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time the AccessPolicy was updated in UTC.
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
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time the AccessPolicy was created in UTC.
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
Description of the ServicePerimeter and its use. Does not affect behavior.
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
Resource name for the ServicePerimeter. The short_name component must begin with a letter and only include alphanumeric
and &#39;_&#39;. Format: accessPolicies/{policy_id}/servicePerimeters/{short_name}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parent</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The AccessPolicy this ServicePerimeter lives in. Format: accessPolicies/{policy_id}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Perimeter<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of the Perimeter. There are two types: regular and bridge. Regular Service Perimeter contains
resources, access levels, and restricted services. Every resource can be in at most ONE regular Service Perimeter. In
addition to being in a regular service perimeter, a resource can also be in zero or more perimeter bridges. A perimeter
bridge only contains resources. Cross project operations are permitted if all effected resources share some perimeter
(whether bridge or regular). Perimeter Bridge does not contain access levels or services: those are governed entirely by
the regular perimeter that resource is in. Perimeter Bridges are typically useful when building more complex topologies
with many independent perimeters that need to share some data with a common perimeter, but should not be able to share
data among themselves.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Status</td>
            <td class="align-top">
                
                <code><a href="#serviceperimeterstatus">*Service<wbr>Perimeter<wbr>Status</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ServicePerimeter configuration. Specifies sets of resources, restricted services and access levels that determine
perimeter content and boundaries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Title</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Human readable title. Must be unique within the Policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Update<wbr>Time</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time the AccessPolicy was updated in UTC.
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
            <td class="align-top">create<wbr>Time</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time the AccessPolicy was created in UTC.
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
Description of the ServicePerimeter and its use. Does not affect behavior.
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
Resource name for the ServicePerimeter. The short_name component must begin with a letter and only include alphanumeric
and &#39;_&#39;. Format: accessPolicies/{policy_id}/servicePerimeters/{short_name}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parent</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The AccessPolicy this ServicePerimeter lives in. Format: accessPolicies/{policy_id}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">perimeter<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of the Perimeter. There are two types: regular and bridge. Regular Service Perimeter contains
resources, access levels, and restricted services. Every resource can be in at most ONE regular Service Perimeter. In
addition to being in a regular service perimeter, a resource can also be in zero or more perimeter bridges. A perimeter
bridge only contains resources. Cross project operations are permitted if all effected resources share some perimeter
(whether bridge or regular). Perimeter Bridge does not contain access levels or services: those are governed entirely by
the regular perimeter that resource is in. Perimeter Bridges are typically useful when building more complex topologies
with many independent perimeters that need to share some data with a common perimeter, but should not be able to share
data among themselves.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">status</td>
            <td class="align-top">
                
                <code><a href="#serviceperimeterstatus">Service<wbr>Perimeter<wbr>Status?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ServicePerimeter configuration. Specifies sets of resources, restricted services and access levels that determine
perimeter content and boundaries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">title</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Human readable title. Must be unique within the Policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">update<wbr>Time</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time the AccessPolicy was updated in UTC.
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
            <td class="align-top">create_<wbr>time</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time the AccessPolicy was created in UTC.
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
Description of the ServicePerimeter and its use. Does not affect behavior.
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
Resource name for the ServicePerimeter. The short_name component must begin with a letter and only include alphanumeric
and &#39;_&#39;. Format: accessPolicies/{policy_id}/servicePerimeters/{short_name}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parent</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The AccessPolicy this ServicePerimeter lives in. Format: accessPolicies/{policy_id}
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">perimeter_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of the Perimeter. There are two types: regular and bridge. Regular Service Perimeter contains
resources, access levels, and restricted services. Every resource can be in at most ONE regular Service Perimeter. In
addition to being in a regular service perimeter, a resource can also be in zero or more perimeter bridges. A perimeter
bridge only contains resources. Cross project operations are permitted if all effected resources share some perimeter
(whether bridge or regular). Perimeter Bridge does not contain access levels or services: those are governed entirely by
the regular perimeter that resource is in. Perimeter Bridges are typically useful when building more complex topologies
with many independent perimeters that need to share some data with a common perimeter, but should not be able to share
data among themselves.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">status</td>
            <td class="align-top">
                
                <code><a href="#serviceperimeterstatus">Dict[Service<wbr>Perimeter<wbr>Status]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
ServicePerimeter configuration. Specifies sets of resources, restricted services and access levels that determine
perimeter content and boundaries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">title</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Human readable title. Must be unique within the Policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">update_<wbr>time</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time the AccessPolicy was updated in UTC.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### ServicePerimeterStatus
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ServicePerimeterStatus">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ServicePerimeterStatus">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/accesscontextmanager?tab=doc#ServicePerimeterStatusArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/accesscontextmanager?tab=doc#ServicePerimeterStatusOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Accesscontextmanager.ServicePerimeterStatusArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Accesscontextmanager.ServicePerimeterStatus.html">output</a> API doc for this type.
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
            <td class="align-top">Access<wbr>Levels</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resources</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Restricted<wbr>Services</td>
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
            <td class="align-top">Access<wbr>Levels</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resources</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Restricted<wbr>Services</td>
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
            <td class="align-top">access<wbr>Levels</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resources</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">restricted<wbr>Services</td>
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
            <td class="align-top">access<wbr>Levels</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resources</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">restricted<wbr>Services</td>
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









---
title: "Firewall"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Each network has its own firewall controlling access to and from the
instances.

All traffic to instances, even from other instances, is blocked by the
firewall unless firewall rules are created to allow it.

The default network has automatically created firewall rules that are
shown in default firewall rules. No manually created network has
automatically created firewall rules except for a default "allow" rule for
outgoing traffic and a default "deny" for incoming traffic. For all
networks except the default network, you must create any firewall rules
you need.


To get more information about Firewall, see:

* [API documentation](https://cloud.google.com/compute/docs/reference/v1/firewalls)
* How-to Guides
    * [Official Documentation](https://cloud.google.com/vpc/docs/firewalls)

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/compute_firewall.html.markdown.



## Create a Firewall Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#Firewall">Firewall</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#FirewallArgs">FirewallArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Firewall</span><span class="p">(resource_name, opts=None, </span>allows=None<span class="p">, </span>denies=None<span class="p">, </span>description=None<span class="p">, </span>destination_ranges=None<span class="p">, </span>direction=None<span class="p">, </span>disabled=None<span class="p">, </span>enable_logging=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>priority=None<span class="p">, </span>project=None<span class="p">, </span>source_ranges=None<span class="p">, </span>source_service_accounts=None<span class="p">, </span>source_tags=None<span class="p">, </span>target_service_accounts=None<span class="p">, </span>target_tags=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewFirewall<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#FirewallArgs">FirewallArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#Firewall">Firewall</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.Firewall.html">Firewall</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.FirewallArgs.html">FirewallArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Firewall resource with the given unique name, arguments, and options.

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
            <td class="align-top">Allows</td>
            <td class="align-top">
                
                <code><a href="#firewallallow">List&lt;Firewall<wbr>Allow<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of ALLOW rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
permitted connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Denies</td>
            <td class="align-top">
                
                <code><a href="#firewalldeny">List&lt;Firewall<wbr>Deny<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of DENY rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
denied connection.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination<wbr>Ranges</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If destination ranges are specified, the firewall will apply only to traffic that has destination IP address in these
ranges. These ranges must be expressed in CIDR format. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Direction</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Direction of traffic to which this firewall applies; default is INGRESS. Note: For INGRESS traffic, it is NOT supported
to specify destinationRanges; For EGRESS traffic, it is NOT supported to specify sourceRanges OR sourceTags.
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
Denotes whether the firewall rule is disabled, i.e not applied to the network it is associated with. When set to true,
the firewall rule is not enforced and the network behaves as if it did not exist. If this is unspecified, the firewall
rule will be enabled.
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
This field denotes whether to enable logging for a particular firewall rule. If logging is enabled, logs will be
exported to Stackdriver.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the network to attach this firewall to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Priority for this rule. This is an integer between 0 and 65535, both inclusive. When not specified, the value assumed is
1000. Relative priorities determine precedence of conflicting rules. Lower value of priority implies higher precedence
(eg, a rule with priority 0 has higher precedence than a rule with priority 1). DENY rules take precedence over ALLOW
rules having equal priority.
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
            <td class="align-top">Source<wbr>Ranges</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source ranges are specified, the firewall will apply only to traffic that has source IP address in these ranges.
These ranges must be expressed in CIDR format. One or both of sourceRanges and sourceTags may be set. If both properties
are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP that belongs
to a tag listed in the sourceTags property. The connection does not need to match both properties for the firewall to
apply. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source service accounts are specified, the firewall will apply only to traffic originating from an instance with a
service account in this list. Source service accounts cannot be used to control traffic to an instance&#39;s external IP
address because service accounts are associated with an instance, not an IP address. sourceRanges can be set at the same
time as sourceServiceAccounts. If both are set, the firewall will apply to traffic that has source IP address within
sourceRanges OR the source IP belongs to an instance with service account listed in sourceServiceAccount. The connection
does not need to match both properties for the firewall to apply. sourceServiceAccounts cannot be used at the same time
as sourceTags or targetTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Tags</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source tags are specified, the firewall will apply only to traffic with source IP that belongs to a tag listed in
source tags. Source tags cannot be used to control traffic to an instance&#39;s external IP address. Because tags are
associated with an instance, not an IP address. One or both of sourceRanges and sourceTags may be set. If both
properties are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP
that belongs to a tag listed in the sourceTags property. The connection does not need to match both properties for the
firewall to apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of service accounts indicating sets of instances located in the network that may make network connections as
specified in allowed[]. targetServiceAccounts cannot be used at the same time as targetTags or sourceTags. If neither
targetServiceAccounts nor targetTags are specified, the firewall rule applies to all instances on the specified network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Tags</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags indicating sets of instances located in the network that may make network connections as
specified in allowed[]. If no targetTags are specified, the firewall rule applies to all instances on the specified
network.
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
            <td class="align-top">Allows</td>
            <td class="align-top">
                
                <code><a href="#firewallallow">[]Firewall<wbr>Allow</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of ALLOW rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
permitted connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Denies</td>
            <td class="align-top">
                
                <code><a href="#firewalldeny">[]Firewall<wbr>Deny</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of DENY rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
denied connection.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination<wbr>Ranges</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If destination ranges are specified, the firewall will apply only to traffic that has destination IP address in these
ranges. These ranges must be expressed in CIDR format. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Direction</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Direction of traffic to which this firewall applies; default is INGRESS. Note: For INGRESS traffic, it is NOT supported
to specify destinationRanges; For EGRESS traffic, it is NOT supported to specify sourceRanges OR sourceTags.
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
Denotes whether the firewall rule is disabled, i.e not applied to the network it is associated with. When set to true,
the firewall rule is not enforced and the network behaves as if it did not exist. If this is unspecified, the firewall
rule will be enabled.
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
This field denotes whether to enable logging for a particular firewall rule. If logging is enabled, logs will be
exported to Stackdriver.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the network to attach this firewall to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Priority for this rule. This is an integer between 0 and 65535, both inclusive. When not specified, the value assumed is
1000. Relative priorities determine precedence of conflicting rules. Lower value of priority implies higher precedence
(eg, a rule with priority 0 has higher precedence than a rule with priority 1). DENY rules take precedence over ALLOW
rules having equal priority.
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
            <td class="align-top">Source<wbr>Ranges</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source ranges are specified, the firewall will apply only to traffic that has source IP address in these ranges.
These ranges must be expressed in CIDR format. One or both of sourceRanges and sourceTags may be set. If both properties
are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP that belongs
to a tag listed in the sourceTags property. The connection does not need to match both properties for the firewall to
apply. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source service accounts are specified, the firewall will apply only to traffic originating from an instance with a
service account in this list. Source service accounts cannot be used to control traffic to an instance&#39;s external IP
address because service accounts are associated with an instance, not an IP address. sourceRanges can be set at the same
time as sourceServiceAccounts. If both are set, the firewall will apply to traffic that has source IP address within
sourceRanges OR the source IP belongs to an instance with service account listed in sourceServiceAccount. The connection
does not need to match both properties for the firewall to apply. sourceServiceAccounts cannot be used at the same time
as sourceTags or targetTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Tags</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source tags are specified, the firewall will apply only to traffic with source IP that belongs to a tag listed in
source tags. Source tags cannot be used to control traffic to an instance&#39;s external IP address. Because tags are
associated with an instance, not an IP address. One or both of sourceRanges and sourceTags may be set. If both
properties are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP
that belongs to a tag listed in the sourceTags property. The connection does not need to match both properties for the
firewall to apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of service accounts indicating sets of instances located in the network that may make network connections as
specified in allowed[]. targetServiceAccounts cannot be used at the same time as targetTags or sourceTags. If neither
targetServiceAccounts nor targetTags are specified, the firewall rule applies to all instances on the specified network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Tags</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags indicating sets of instances located in the network that may make network connections as
specified in allowed[]. If no targetTags are specified, the firewall rule applies to all instances on the specified
network.
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
            <td class="align-top">allows</td>
            <td class="align-top">
                
                <code><a href="#firewallallow">Firewall<wbr>Allow[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of ALLOW rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
permitted connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">denies</td>
            <td class="align-top">
                
                <code><a href="#firewalldeny">Firewall<wbr>Deny[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of DENY rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
denied connection.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination<wbr>Ranges</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If destination ranges are specified, the firewall will apply only to traffic that has destination IP address in these
ranges. These ranges must be expressed in CIDR format. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">direction</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Direction of traffic to which this firewall applies; default is INGRESS. Note: For INGRESS traffic, it is NOT supported
to specify destinationRanges; For EGRESS traffic, it is NOT supported to specify sourceRanges OR sourceTags.
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
Denotes whether the firewall rule is disabled, i.e not applied to the network it is associated with. When set to true,
the firewall rule is not enforced and the network behaves as if it did not exist. If this is unspecified, the firewall
rule will be enabled.
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
This field denotes whether to enable logging for a particular firewall rule. If logging is enabled, logs will be
exported to Stackdriver.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the network to attach this firewall to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Priority for this rule. This is an integer between 0 and 65535, both inclusive. When not specified, the value assumed is
1000. Relative priorities determine precedence of conflicting rules. Lower value of priority implies higher precedence
(eg, a rule with priority 0 has higher precedence than a rule with priority 1). DENY rules take precedence over ALLOW
rules having equal priority.
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
            <td class="align-top">source<wbr>Ranges</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source ranges are specified, the firewall will apply only to traffic that has source IP address in these ranges.
These ranges must be expressed in CIDR format. One or both of sourceRanges and sourceTags may be set. If both properties
are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP that belongs
to a tag listed in the sourceTags property. The connection does not need to match both properties for the firewall to
apply. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source service accounts are specified, the firewall will apply only to traffic originating from an instance with a
service account in this list. Source service accounts cannot be used to control traffic to an instance&#39;s external IP
address because service accounts are associated with an instance, not an IP address. sourceRanges can be set at the same
time as sourceServiceAccounts. If both are set, the firewall will apply to traffic that has source IP address within
sourceRanges OR the source IP belongs to an instance with service account listed in sourceServiceAccount. The connection
does not need to match both properties for the firewall to apply. sourceServiceAccounts cannot be used at the same time
as sourceTags or targetTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Tags</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source tags are specified, the firewall will apply only to traffic with source IP that belongs to a tag listed in
source tags. Source tags cannot be used to control traffic to an instance&#39;s external IP address. Because tags are
associated with an instance, not an IP address. One or both of sourceRanges and sourceTags may be set. If both
properties are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP
that belongs to a tag listed in the sourceTags property. The connection does not need to match both properties for the
firewall to apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of service accounts indicating sets of instances located in the network that may make network connections as
specified in allowed[]. targetServiceAccounts cannot be used at the same time as targetTags or sourceTags. If neither
targetServiceAccounts nor targetTags are specified, the firewall rule applies to all instances on the specified network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Tags</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags indicating sets of instances located in the network that may make network connections as
specified in allowed[]. If no targetTags are specified, the firewall rule applies to all instances on the specified
network.
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
            <td class="align-top">allows</td>
            <td class="align-top">
                
                <code><a href="#firewallallow">List[Firewall<wbr>Allow]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of ALLOW rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
permitted connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">denies</td>
            <td class="align-top">
                
                <code><a href="#firewalldeny">List[Firewall<wbr>Deny]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of DENY rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
denied connection.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination_<wbr>ranges</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If destination ranges are specified, the firewall will apply only to traffic that has destination IP address in these
ranges. These ranges must be expressed in CIDR format. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">direction</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Direction of traffic to which this firewall applies; default is INGRESS. Note: For INGRESS traffic, it is NOT supported
to specify destinationRanges; For EGRESS traffic, it is NOT supported to specify sourceRanges OR sourceTags.
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
Denotes whether the firewall rule is disabled, i.e not applied to the network it is associated with. When set to true,
the firewall rule is not enforced and the network behaves as if it did not exist. If this is unspecified, the firewall
rule will be enabled.
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
This field denotes whether to enable logging for a particular firewall rule. If logging is enabled, logs will be
exported to Stackdriver.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the network to attach this firewall to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Priority for this rule. This is an integer between 0 and 65535, both inclusive. When not specified, the value assumed is
1000. Relative priorities determine precedence of conflicting rules. Lower value of priority implies higher precedence
(eg, a rule with priority 0 has higher precedence than a rule with priority 1). DENY rules take precedence over ALLOW
rules having equal priority.
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
            <td class="align-top">source_<wbr>ranges</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source ranges are specified, the firewall will apply only to traffic that has source IP address in these ranges.
These ranges must be expressed in CIDR format. One or both of sourceRanges and sourceTags may be set. If both properties
are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP that belongs
to a tag listed in the sourceTags property. The connection does not need to match both properties for the firewall to
apply. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>service_<wbr>accounts</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source service accounts are specified, the firewall will apply only to traffic originating from an instance with a
service account in this list. Source service accounts cannot be used to control traffic to an instance&#39;s external IP
address because service accounts are associated with an instance, not an IP address. sourceRanges can be set at the same
time as sourceServiceAccounts. If both are set, the firewall will apply to traffic that has source IP address within
sourceRanges OR the source IP belongs to an instance with service account listed in sourceServiceAccount. The connection
does not need to match both properties for the firewall to apply. sourceServiceAccounts cannot be used at the same time
as sourceTags or targetTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>tags</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source tags are specified, the firewall will apply only to traffic with source IP that belongs to a tag listed in
source tags. Source tags cannot be used to control traffic to an instance&#39;s external IP address. Because tags are
associated with an instance, not an IP address. One or both of sourceRanges and sourceTags may be set. If both
properties are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP
that belongs to a tag listed in the sourceTags property. The connection does not need to match both properties for the
firewall to apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>service_<wbr>accounts</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of service accounts indicating sets of instances located in the network that may make network connections as
specified in allowed[]. targetServiceAccounts cannot be used at the same time as targetTags or sourceTags. If neither
targetServiceAccounts nor targetTags are specified, the firewall rule applies to all instances on the specified network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>tags</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags indicating sets of instances located in the network that may make network connections as
specified in allowed[]. If no targetTags are specified, the firewall rule applies to all instances on the specified
network.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Firewall Output Properties

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
            <td class="align-top">Allows</td>
            <td class="align-top">
                
                <code><a href="#firewallallow">List&lt;Firewall<wbr>Allow&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} The list of ALLOW rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
permitted connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Denies</td>
            <td class="align-top">
                
                <code><a href="#firewalldeny">List&lt;Firewall<wbr>Deny&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} The list of DENY rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
denied connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination<wbr>Ranges</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} If destination ranges are specified, the firewall will apply only to traffic that has destination IP address in these
ranges. These ranges must be expressed in CIDR format. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Direction</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Direction of traffic to which this firewall applies; default is INGRESS. Note: For INGRESS traffic, it is NOT supported
to specify destinationRanges; For EGRESS traffic, it is NOT supported to specify sourceRanges OR sourceTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Denotes whether the firewall rule is disabled, i.e not applied to the network it is associated with. When set to true,
the firewall rule is not enforced and the network behaves as if it did not exist. If this is unspecified, the firewall
rule will be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Logging</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} This field denotes whether to enable logging for a particular firewall rule. If logging is enabled, logs will be
exported to Stackdriver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name or self_link of the network to attach this firewall to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} Priority for this rule. This is an integer between 0 and 65535, both inclusive. When not specified, the value assumed is
1000. Relative priorities determine precedence of conflicting rules. Lower value of priority implies higher precedence
(eg, a rule with priority 0 has higher precedence than a rule with priority 1). DENY rules take precedence over ALLOW
rules having equal priority.
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
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Ranges</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} If source ranges are specified, the firewall will apply only to traffic that has source IP address in these ranges.
These ranges must be expressed in CIDR format. One or both of sourceRanges and sourceTags may be set. If both properties
are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP that belongs
to a tag listed in the sourceTags property. The connection does not need to match both properties for the firewall to
apply. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} If source service accounts are specified, the firewall will apply only to traffic originating from an instance with a
service account in this list. Source service accounts cannot be used to control traffic to an instance&#39;s external IP
address because service accounts are associated with an instance, not an IP address. sourceRanges can be set at the same
time as sourceServiceAccounts. If both are set, the firewall will apply to traffic that has source IP address within
sourceRanges OR the source IP belongs to an instance with service account listed in sourceServiceAccount. The connection
does not need to match both properties for the firewall to apply. sourceServiceAccounts cannot be used at the same time
as sourceTags or targetTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Tags</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} If source tags are specified, the firewall will apply only to traffic with source IP that belongs to a tag listed in
source tags. Source tags cannot be used to control traffic to an instance&#39;s external IP address. Because tags are
associated with an instance, not an IP address. One or both of sourceRanges and sourceTags may be set. If both
properties are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP
that belongs to a tag listed in the sourceTags property. The connection does not need to match both properties for the
firewall to apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} A list of service accounts indicating sets of instances located in the network that may make network connections as
specified in allowed[]. targetServiceAccounts cannot be used at the same time as targetTags or sourceTags. If neither
targetServiceAccounts nor targetTags are specified, the firewall rule applies to all instances on the specified network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Tags</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} A list of instance tags indicating sets of instances located in the network that may make network connections as
specified in allowed[]. If no targetTags are specified, the firewall rule applies to all instances on the specified
network.
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
            <td class="align-top">Allows</td>
            <td class="align-top">
                
                <code><a href="#firewallallow">[]Firewall<wbr>Allow</a></code>
            </td>
            <td class="align-top">{{% md %}} The list of ALLOW rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
permitted connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Denies</td>
            <td class="align-top">
                
                <code><a href="#firewalldeny">[]Firewall<wbr>Deny</a></code>
            </td>
            <td class="align-top">{{% md %}} The list of DENY rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
denied connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination<wbr>Ranges</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} If destination ranges are specified, the firewall will apply only to traffic that has destination IP address in these
ranges. These ranges must be expressed in CIDR format. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Direction</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Direction of traffic to which this firewall applies; default is INGRESS. Note: For INGRESS traffic, it is NOT supported
to specify destinationRanges; For EGRESS traffic, it is NOT supported to specify sourceRanges OR sourceTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Denotes whether the firewall rule is disabled, i.e not applied to the network it is associated with. When set to true,
the firewall rule is not enforced and the network behaves as if it did not exist. If this is unspecified, the firewall
rule will be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Logging</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} This field denotes whether to enable logging for a particular firewall rule. If logging is enabled, logs will be
exported to Stackdriver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name or self_link of the network to attach this firewall to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} Priority for this rule. This is an integer between 0 and 65535, both inclusive. When not specified, the value assumed is
1000. Relative priorities determine precedence of conflicting rules. Lower value of priority implies higher precedence
(eg, a rule with priority 0 has higher precedence than a rule with priority 1). DENY rules take precedence over ALLOW
rules having equal priority.
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
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Ranges</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} If source ranges are specified, the firewall will apply only to traffic that has source IP address in these ranges.
These ranges must be expressed in CIDR format. One or both of sourceRanges and sourceTags may be set. If both properties
are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP that belongs
to a tag listed in the sourceTags property. The connection does not need to match both properties for the firewall to
apply. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} If source service accounts are specified, the firewall will apply only to traffic originating from an instance with a
service account in this list. Source service accounts cannot be used to control traffic to an instance&#39;s external IP
address because service accounts are associated with an instance, not an IP address. sourceRanges can be set at the same
time as sourceServiceAccounts. If both are set, the firewall will apply to traffic that has source IP address within
sourceRanges OR the source IP belongs to an instance with service account listed in sourceServiceAccount. The connection
does not need to match both properties for the firewall to apply. sourceServiceAccounts cannot be used at the same time
as sourceTags or targetTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Tags</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} If source tags are specified, the firewall will apply only to traffic with source IP that belongs to a tag listed in
source tags. Source tags cannot be used to control traffic to an instance&#39;s external IP address. Because tags are
associated with an instance, not an IP address. One or both of sourceRanges and sourceTags may be set. If both
properties are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP
that belongs to a tag listed in the sourceTags property. The connection does not need to match both properties for the
firewall to apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} A list of service accounts indicating sets of instances located in the network that may make network connections as
specified in allowed[]. targetServiceAccounts cannot be used at the same time as targetTags or sourceTags. If neither
targetServiceAccounts nor targetTags are specified, the firewall rule applies to all instances on the specified network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Tags</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} A list of instance tags indicating sets of instances located in the network that may make network connections as
specified in allowed[]. If no targetTags are specified, the firewall rule applies to all instances on the specified
network.
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
            <td class="align-top">allows</td>
            <td class="align-top">
                
                <code><a href="#firewallallow">Firewall<wbr>Allow[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} The list of ALLOW rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
permitted connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">denies</td>
            <td class="align-top">
                
                <code><a href="#firewalldeny">Firewall<wbr>Deny[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} The list of DENY rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
denied connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination<wbr>Ranges</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} If destination ranges are specified, the firewall will apply only to traffic that has destination IP address in these
ranges. These ranges must be expressed in CIDR format. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">direction</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Direction of traffic to which this firewall applies; default is INGRESS. Note: For INGRESS traffic, it is NOT supported
to specify destinationRanges; For EGRESS traffic, it is NOT supported to specify sourceRanges OR sourceTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Denotes whether the firewall rule is disabled, i.e not applied to the network it is associated with. When set to true,
the firewall rule is not enforced and the network behaves as if it did not exist. If this is unspecified, the firewall
rule will be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Logging</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} This field denotes whether to enable logging for a particular firewall rule. If logging is enabled, logs will be
exported to Stackdriver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name or self_link of the network to attach this firewall to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} Priority for this rule. This is an integer between 0 and 65535, both inclusive. When not specified, the value assumed is
1000. Relative priorities determine precedence of conflicting rules. Lower value of priority implies higher precedence
(eg, a rule with priority 0 has higher precedence than a rule with priority 1). DENY rules take precedence over ALLOW
rules having equal priority.
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
            <td class="align-top">self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Ranges</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} If source ranges are specified, the firewall will apply only to traffic that has source IP address in these ranges.
These ranges must be expressed in CIDR format. One or both of sourceRanges and sourceTags may be set. If both properties
are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP that belongs
to a tag listed in the sourceTags property. The connection does not need to match both properties for the firewall to
apply. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} If source service accounts are specified, the firewall will apply only to traffic originating from an instance with a
service account in this list. Source service accounts cannot be used to control traffic to an instance&#39;s external IP
address because service accounts are associated with an instance, not an IP address. sourceRanges can be set at the same
time as sourceServiceAccounts. If both are set, the firewall will apply to traffic that has source IP address within
sourceRanges OR the source IP belongs to an instance with service account listed in sourceServiceAccount. The connection
does not need to match both properties for the firewall to apply. sourceServiceAccounts cannot be used at the same time
as sourceTags or targetTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Tags</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} If source tags are specified, the firewall will apply only to traffic with source IP that belongs to a tag listed in
source tags. Source tags cannot be used to control traffic to an instance&#39;s external IP address. Because tags are
associated with an instance, not an IP address. One or both of sourceRanges and sourceTags may be set. If both
properties are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP
that belongs to a tag listed in the sourceTags property. The connection does not need to match both properties for the
firewall to apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} A list of service accounts indicating sets of instances located in the network that may make network connections as
specified in allowed[]. targetServiceAccounts cannot be used at the same time as targetTags or sourceTags. If neither
targetServiceAccounts nor targetTags are specified, the firewall rule applies to all instances on the specified network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Tags</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} A list of instance tags indicating sets of instances located in the network that may make network connections as
specified in allowed[]. If no targetTags are specified, the firewall rule applies to all instances on the specified
network.
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
            <td class="align-top">allows</td>
            <td class="align-top">
                
                <code><a href="#firewallallow">List[Firewall<wbr>Allow]</a></code>
            </td>
            <td class="align-top">{{% md %}} The list of ALLOW rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
permitted connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation_<wbr>timestamp</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">denies</td>
            <td class="align-top">
                
                <code><a href="#firewalldeny">List[Firewall<wbr>Deny]</a></code>
            </td>
            <td class="align-top">{{% md %}} The list of DENY rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
denied connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination_<wbr>ranges</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} If destination ranges are specified, the firewall will apply only to traffic that has destination IP address in these
ranges. These ranges must be expressed in CIDR format. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">direction</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Direction of traffic to which this firewall applies; default is INGRESS. Note: For INGRESS traffic, it is NOT supported
to specify destinationRanges; For EGRESS traffic, it is NOT supported to specify sourceRanges OR sourceTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Denotes whether the firewall rule is disabled, i.e not applied to the network it is associated with. When set to true,
the firewall rule is not enforced and the network behaves as if it did not exist. If this is unspecified, the firewall
rule will be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>logging</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} This field denotes whether to enable logging for a particular firewall rule. If logging is enabled, logs will be
exported to Stackdriver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name or self_link of the network to attach this firewall to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} Priority for this rule. This is an integer between 0 and 65535, both inclusive. When not specified, the value assumed is
1000. Relative priorities determine precedence of conflicting rules. Lower value of priority implies higher precedence
(eg, a rule with priority 0 has higher precedence than a rule with priority 1). DENY rules take precedence over ALLOW
rules having equal priority.
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
            <td class="align-top">self_<wbr>link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>ranges</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} If source ranges are specified, the firewall will apply only to traffic that has source IP address in these ranges.
These ranges must be expressed in CIDR format. One or both of sourceRanges and sourceTags may be set. If both properties
are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP that belongs
to a tag listed in the sourceTags property. The connection does not need to match both properties for the firewall to
apply. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>service_<wbr>accounts</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} If source service accounts are specified, the firewall will apply only to traffic originating from an instance with a
service account in this list. Source service accounts cannot be used to control traffic to an instance&#39;s external IP
address because service accounts are associated with an instance, not an IP address. sourceRanges can be set at the same
time as sourceServiceAccounts. If both are set, the firewall will apply to traffic that has source IP address within
sourceRanges OR the source IP belongs to an instance with service account listed in sourceServiceAccount. The connection
does not need to match both properties for the firewall to apply. sourceServiceAccounts cannot be used at the same time
as sourceTags or targetTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>tags</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} If source tags are specified, the firewall will apply only to traffic with source IP that belongs to a tag listed in
source tags. Source tags cannot be used to control traffic to an instance&#39;s external IP address. Because tags are
associated with an instance, not an IP address. One or both of sourceRanges and sourceTags may be set. If both
properties are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP
that belongs to a tag listed in the sourceTags property. The connection does not need to match both properties for the
firewall to apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>service_<wbr>accounts</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} A list of service accounts indicating sets of instances located in the network that may make network connections as
specified in allowed[]. targetServiceAccounts cannot be used at the same time as targetTags or sourceTags. If neither
targetServiceAccounts nor targetTags are specified, the firewall rule applies to all instances on the specified network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>tags</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} A list of instance tags indicating sets of instances located in the network that may make network connections as
specified in allowed[]. If no targetTags are specified, the firewall rule applies to all instances on the specified
network.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Firewall Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#FirewallState">FirewallState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#Firewall">Firewall</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>allows=None<span class="p">, </span>creation_timestamp=None<span class="p">, </span>denies=None<span class="p">, </span>description=None<span class="p">, </span>destination_ranges=None<span class="p">, </span>direction=None<span class="p">, </span>disabled=None<span class="p">, </span>enable_logging=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>priority=None<span class="p">, </span>project=None<span class="p">, </span>self_link=None<span class="p">, </span>source_ranges=None<span class="p">, </span>source_service_accounts=None<span class="p">, </span>source_tags=None<span class="p">, </span>target_service_accounts=None<span class="p">, </span>target_tags=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetFirewall<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#FirewallState">FirewallState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#Firewall">Firewall</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.Firewall.html">Firewall</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.FirewallState.html">FirewallState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Firewall resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Allows</td>
            <td class="align-top">
                
                <code><a href="#firewallallow">List&lt;Firewall<wbr>Allow<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of ALLOW rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
permitted connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Denies</td>
            <td class="align-top">
                
                <code><a href="#firewalldeny">List&lt;Firewall<wbr>Deny<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of DENY rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
denied connection.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination<wbr>Ranges</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If destination ranges are specified, the firewall will apply only to traffic that has destination IP address in these
ranges. These ranges must be expressed in CIDR format. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Direction</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Direction of traffic to which this firewall applies; default is INGRESS. Note: For INGRESS traffic, it is NOT supported
to specify destinationRanges; For EGRESS traffic, it is NOT supported to specify sourceRanges OR sourceTags.
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
Denotes whether the firewall rule is disabled, i.e not applied to the network it is associated with. When set to true,
the firewall rule is not enforced and the network behaves as if it did not exist. If this is unspecified, the firewall
rule will be enabled.
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
This field denotes whether to enable logging for a particular firewall rule. If logging is enabled, logs will be
exported to Stackdriver.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name or self_link of the network to attach this firewall to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Priority for this rule. This is an integer between 0 and 65535, both inclusive. When not specified, the value assumed is
1000. Relative priorities determine precedence of conflicting rules. Lower value of priority implies higher precedence
(eg, a rule with priority 0 has higher precedence than a rule with priority 1). DENY rules take precedence over ALLOW
rules having equal priority.
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
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Ranges</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source ranges are specified, the firewall will apply only to traffic that has source IP address in these ranges.
These ranges must be expressed in CIDR format. One or both of sourceRanges and sourceTags may be set. If both properties
are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP that belongs
to a tag listed in the sourceTags property. The connection does not need to match both properties for the firewall to
apply. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source service accounts are specified, the firewall will apply only to traffic originating from an instance with a
service account in this list. Source service accounts cannot be used to control traffic to an instance&#39;s external IP
address because service accounts are associated with an instance, not an IP address. sourceRanges can be set at the same
time as sourceServiceAccounts. If both are set, the firewall will apply to traffic that has source IP address within
sourceRanges OR the source IP belongs to an instance with service account listed in sourceServiceAccount. The connection
does not need to match both properties for the firewall to apply. sourceServiceAccounts cannot be used at the same time
as sourceTags or targetTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Tags</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source tags are specified, the firewall will apply only to traffic with source IP that belongs to a tag listed in
source tags. Source tags cannot be used to control traffic to an instance&#39;s external IP address. Because tags are
associated with an instance, not an IP address. One or both of sourceRanges and sourceTags may be set. If both
properties are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP
that belongs to a tag listed in the sourceTags property. The connection does not need to match both properties for the
firewall to apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of service accounts indicating sets of instances located in the network that may make network connections as
specified in allowed[]. targetServiceAccounts cannot be used at the same time as targetTags or sourceTags. If neither
targetServiceAccounts nor targetTags are specified, the firewall rule applies to all instances on the specified network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Tags</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags indicating sets of instances located in the network that may make network connections as
specified in allowed[]. If no targetTags are specified, the firewall rule applies to all instances on the specified
network.
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
            <td class="align-top">Allows</td>
            <td class="align-top">
                
                <code><a href="#firewallallow">[]Firewall<wbr>Allow</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of ALLOW rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
permitted connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Denies</td>
            <td class="align-top">
                
                <code><a href="#firewalldeny">[]Firewall<wbr>Deny</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of DENY rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
denied connection.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination<wbr>Ranges</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If destination ranges are specified, the firewall will apply only to traffic that has destination IP address in these
ranges. These ranges must be expressed in CIDR format. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Direction</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Direction of traffic to which this firewall applies; default is INGRESS. Note: For INGRESS traffic, it is NOT supported
to specify destinationRanges; For EGRESS traffic, it is NOT supported to specify sourceRanges OR sourceTags.
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
Denotes whether the firewall rule is disabled, i.e not applied to the network it is associated with. When set to true,
the firewall rule is not enforced and the network behaves as if it did not exist. If this is unspecified, the firewall
rule will be enabled.
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
This field denotes whether to enable logging for a particular firewall rule. If logging is enabled, logs will be
exported to Stackdriver.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name or self_link of the network to attach this firewall to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Priority for this rule. This is an integer between 0 and 65535, both inclusive. When not specified, the value assumed is
1000. Relative priorities determine precedence of conflicting rules. Lower value of priority implies higher precedence
(eg, a rule with priority 0 has higher precedence than a rule with priority 1). DENY rules take precedence over ALLOW
rules having equal priority.
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
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Ranges</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source ranges are specified, the firewall will apply only to traffic that has source IP address in these ranges.
These ranges must be expressed in CIDR format. One or both of sourceRanges and sourceTags may be set. If both properties
are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP that belongs
to a tag listed in the sourceTags property. The connection does not need to match both properties for the firewall to
apply. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source service accounts are specified, the firewall will apply only to traffic originating from an instance with a
service account in this list. Source service accounts cannot be used to control traffic to an instance&#39;s external IP
address because service accounts are associated with an instance, not an IP address. sourceRanges can be set at the same
time as sourceServiceAccounts. If both are set, the firewall will apply to traffic that has source IP address within
sourceRanges OR the source IP belongs to an instance with service account listed in sourceServiceAccount. The connection
does not need to match both properties for the firewall to apply. sourceServiceAccounts cannot be used at the same time
as sourceTags or targetTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Tags</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source tags are specified, the firewall will apply only to traffic with source IP that belongs to a tag listed in
source tags. Source tags cannot be used to control traffic to an instance&#39;s external IP address. Because tags are
associated with an instance, not an IP address. One or both of sourceRanges and sourceTags may be set. If both
properties are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP
that belongs to a tag listed in the sourceTags property. The connection does not need to match both properties for the
firewall to apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of service accounts indicating sets of instances located in the network that may make network connections as
specified in allowed[]. targetServiceAccounts cannot be used at the same time as targetTags or sourceTags. If neither
targetServiceAccounts nor targetTags are specified, the firewall rule applies to all instances on the specified network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Tags</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags indicating sets of instances located in the network that may make network connections as
specified in allowed[]. If no targetTags are specified, the firewall rule applies to all instances on the specified
network.
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
            <td class="align-top">allows</td>
            <td class="align-top">
                
                <code><a href="#firewallallow">Firewall<wbr>Allow[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of ALLOW rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
permitted connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">denies</td>
            <td class="align-top">
                
                <code><a href="#firewalldeny">Firewall<wbr>Deny[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of DENY rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
denied connection.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination<wbr>Ranges</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If destination ranges are specified, the firewall will apply only to traffic that has destination IP address in these
ranges. These ranges must be expressed in CIDR format. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">direction</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Direction of traffic to which this firewall applies; default is INGRESS. Note: For INGRESS traffic, it is NOT supported
to specify destinationRanges; For EGRESS traffic, it is NOT supported to specify sourceRanges OR sourceTags.
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
Denotes whether the firewall rule is disabled, i.e not applied to the network it is associated with. When set to true,
the firewall rule is not enforced and the network behaves as if it did not exist. If this is unspecified, the firewall
rule will be enabled.
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
This field denotes whether to enable logging for a particular firewall rule. If logging is enabled, logs will be
exported to Stackdriver.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name or self_link of the network to attach this firewall to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Priority for this rule. This is an integer between 0 and 65535, both inclusive. When not specified, the value assumed is
1000. Relative priorities determine precedence of conflicting rules. Lower value of priority implies higher precedence
(eg, a rule with priority 0 has higher precedence than a rule with priority 1). DENY rules take precedence over ALLOW
rules having equal priority.
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
            <td class="align-top">self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Ranges</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source ranges are specified, the firewall will apply only to traffic that has source IP address in these ranges.
These ranges must be expressed in CIDR format. One or both of sourceRanges and sourceTags may be set. If both properties
are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP that belongs
to a tag listed in the sourceTags property. The connection does not need to match both properties for the firewall to
apply. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source service accounts are specified, the firewall will apply only to traffic originating from an instance with a
service account in this list. Source service accounts cannot be used to control traffic to an instance&#39;s external IP
address because service accounts are associated with an instance, not an IP address. sourceRanges can be set at the same
time as sourceServiceAccounts. If both are set, the firewall will apply to traffic that has source IP address within
sourceRanges OR the source IP belongs to an instance with service account listed in sourceServiceAccount. The connection
does not need to match both properties for the firewall to apply. sourceServiceAccounts cannot be used at the same time
as sourceTags or targetTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Tags</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source tags are specified, the firewall will apply only to traffic with source IP that belongs to a tag listed in
source tags. Source tags cannot be used to control traffic to an instance&#39;s external IP address. Because tags are
associated with an instance, not an IP address. One or both of sourceRanges and sourceTags may be set. If both
properties are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP
that belongs to a tag listed in the sourceTags property. The connection does not need to match both properties for the
firewall to apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of service accounts indicating sets of instances located in the network that may make network connections as
specified in allowed[]. targetServiceAccounts cannot be used at the same time as targetTags or sourceTags. If neither
targetServiceAccounts nor targetTags are specified, the firewall rule applies to all instances on the specified network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Tags</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags indicating sets of instances located in the network that may make network connections as
specified in allowed[]. If no targetTags are specified, the firewall rule applies to all instances on the specified
network.
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
            <td class="align-top">allows</td>
            <td class="align-top">
                
                <code><a href="#firewallallow">List[Firewall<wbr>Allow]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of ALLOW rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
permitted connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation_<wbr>timestamp</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">denies</td>
            <td class="align-top">
                
                <code><a href="#firewalldeny">List[Firewall<wbr>Deny]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of DENY rules specified by this firewall. Each rule specifies a protocol and port-range tuple that describes a
denied connection.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination_<wbr>ranges</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If destination ranges are specified, the firewall will apply only to traffic that has destination IP address in these
ranges. These ranges must be expressed in CIDR format. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">direction</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Direction of traffic to which this firewall applies; default is INGRESS. Note: For INGRESS traffic, it is NOT supported
to specify destinationRanges; For EGRESS traffic, it is NOT supported to specify sourceRanges OR sourceTags.
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
Denotes whether the firewall rule is disabled, i.e not applied to the network it is associated with. When set to true,
the firewall rule is not enforced and the network behaves as if it did not exist. If this is unspecified, the firewall
rule will be enabled.
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
This field denotes whether to enable logging for a particular firewall rule. If logging is enabled, logs will be
exported to Stackdriver.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name or self_link of the network to attach this firewall to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Priority for this rule. This is an integer between 0 and 65535, both inclusive. When not specified, the value assumed is
1000. Relative priorities determine precedence of conflicting rules. Lower value of priority implies higher precedence
(eg, a rule with priority 0 has higher precedence than a rule with priority 1). DENY rules take precedence over ALLOW
rules having equal priority.
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
            <td class="align-top">self_<wbr>link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>ranges</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source ranges are specified, the firewall will apply only to traffic that has source IP address in these ranges.
These ranges must be expressed in CIDR format. One or both of sourceRanges and sourceTags may be set. If both properties
are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP that belongs
to a tag listed in the sourceTags property. The connection does not need to match both properties for the firewall to
apply. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>service_<wbr>accounts</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source service accounts are specified, the firewall will apply only to traffic originating from an instance with a
service account in this list. Source service accounts cannot be used to control traffic to an instance&#39;s external IP
address because service accounts are associated with an instance, not an IP address. sourceRanges can be set at the same
time as sourceServiceAccounts. If both are set, the firewall will apply to traffic that has source IP address within
sourceRanges OR the source IP belongs to an instance with service account listed in sourceServiceAccount. The connection
does not need to match both properties for the firewall to apply. sourceServiceAccounts cannot be used at the same time
as sourceTags or targetTags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>tags</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If source tags are specified, the firewall will apply only to traffic with source IP that belongs to a tag listed in
source tags. Source tags cannot be used to control traffic to an instance&#39;s external IP address. Because tags are
associated with an instance, not an IP address. One or both of sourceRanges and sourceTags may be set. If both
properties are set, the firewall will apply to traffic that has source IP address within sourceRanges OR the source IP
that belongs to a tag listed in the sourceTags property. The connection does not need to match both properties for the
firewall to apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>service_<wbr>accounts</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of service accounts indicating sets of instances located in the network that may make network connections as
specified in allowed[]. targetServiceAccounts cannot be used at the same time as targetTags or sourceTags. If neither
targetServiceAccounts nor targetTags are specified, the firewall rule applies to all instances on the specified network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>tags</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags indicating sets of instances located in the network that may make network connections as
specified in allowed[]. If no targetTags are specified, the firewall rule applies to all instances on the specified
network.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### FirewallAllow
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#FirewallAllow">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#FirewallAllow">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#FirewallAllowArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#FirewallAllowOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.FirewallAllowArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.FirewallAllow.html">output</a> API doc for this type.
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
            <td class="align-top">Ports</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Protocol</td>
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
            <td class="align-top">Ports</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Protocol</td>
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
            <td class="align-top">ports</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">protocol</td>
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
            <td class="align-top">ports</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">protocol</td>
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





#### FirewallDeny
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#FirewallDeny">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#FirewallDeny">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#FirewallDenyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#FirewallDenyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.FirewallDenyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.FirewallDeny.html">output</a> API doc for this type.
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
            <td class="align-top">Ports</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Protocol</td>
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
            <td class="align-top">Ports</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Protocol</td>
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
            <td class="align-top">ports</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">protocol</td>
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
            <td class="align-top">ports</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">protocol</td>
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








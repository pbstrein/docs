
---
title: "LinuxVirtualMachineScaleSet"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Manages a Linux Virtual Machine Scale Set.

## Disclaimers

> **Note** This provider will automatically update & reimage the nodes in the Scale Set (if Required) during an Update - this behaviour can be configured using the `features` configuration within the Provider configuration block.

> **Note:** This resource does not support Unmanaged Disks. If you need to use Unmanaged Disks you can continue to use the `azure.compute.ScaleSet` resource instead

> This content is derived from https://github.com/terraform-providers/terraform-provider-azurerm/blob/master/website/docs/r/linux_virtual_machine_scale_set.html.markdown.



## Create a LinuxVirtualMachineScaleSet Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/compute/#LinuxVirtualMachineScaleSet">LinuxVirtualMachineScaleSet</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/compute/#LinuxVirtualMachineScaleSetArgs">LinuxVirtualMachineScaleSetArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">LinuxVirtualMachineScaleSet</span><span class="p">(resource_name, opts=None, </span>additional_capabilities=None<span class="p">, </span>admin_password=None<span class="p">, </span>admin_ssh_keys=None<span class="p">, </span>admin_username=None<span class="p">, </span>automatic_os_upgrade_policy=None<span class="p">, </span>boot_diagnostics=None<span class="p">, </span>computer_name_prefix=None<span class="p">, </span>custom_data=None<span class="p">, </span>data_disks=None<span class="p">, </span>disable_password_authentication=None<span class="p">, </span>do_not_run_extensions_on_overprovisioned_machines=None<span class="p">, </span>eviction_policy=None<span class="p">, </span>health_probe_id=None<span class="p">, </span>identity=None<span class="p">, </span>instances=None<span class="p">, </span>location=None<span class="p">, </span>max_bid_price=None<span class="p">, </span>name=None<span class="p">, </span>network_interfaces=None<span class="p">, </span>os_disk=None<span class="p">, </span>overprovision=None<span class="p">, </span>plan=None<span class="p">, </span>priority=None<span class="p">, </span>provision_vm_agent=None<span class="p">, </span>proximity_placement_group_id=None<span class="p">, </span>resource_group_name=None<span class="p">, </span>rolling_upgrade_policy=None<span class="p">, </span>scale_in_policy=None<span class="p">, </span>secrets=None<span class="p">, </span>single_placement_group=None<span class="p">, </span>sku=None<span class="p">, </span>source_image_id=None<span class="p">, </span>source_image_reference=None<span class="p">, </span>tags=None<span class="p">, </span>terminate_notification=None<span class="p">, </span>upgrade_mode=None<span class="p">, </span>zone_balance=None<span class="p">, </span>zones=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewLinuxVirtualMachineScaleSet<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetArgs">LinuxVirtualMachineScaleSetArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSet">LinuxVirtualMachineScaleSet</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSet.html">LinuxVirtualMachineScaleSet</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetArgs.html">LinuxVirtualMachineScaleSetArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a LinuxVirtualMachineScaleSet resource with the given unique name, arguments, and options.

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
            <td class="align-top">Additional<wbr>Capabilities</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadditionalcapabilities">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Password</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Ssh<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadminsshkey">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Admin<wbr>Ssh<wbr>Key<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `admin_ssh_key` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Username</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The username of the local administrator on each Virtual Machine Scale Set instance. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Automatic<wbr>Os<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetautomaticosupgradepolicy">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Boot<wbr>Diagnostics</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetbootdiagnostics">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `boot_diagnostics` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Computer<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The prefix which should be used for the name of the Virtual Machines in this Scale Set. If unspecified this defaults to the value for the `name` field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Data</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Base64-Encoded Custom Data which should be used for this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Data<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetdatadisk">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disable<wbr>Password<wbr>Authentication</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Password Authentication be disabled on this Virtual Machine Scale Set? Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Do<wbr>Not<wbr>Run<wbr>Extensions<wbr>On<wbr>Overprovisioned<wbr>Machines</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Virtual Machine Extensions be run on Overprovisioned Virtual Machines in the Scale Set? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Eviction<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Policy which should be used Virtual Machines are Evicted from the Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Health<wbr>Probe<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of a Load Balancer Probe which should be used to determine the health of an instance. Changing this forces a new resource to be created. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetidentity">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instances</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The number of Virtual Machines in the Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Azure location where the Linux Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Bid<wbr>Price</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in this Scale Set should not be evicted for price reasons.
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterface">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Os<wbr>Disk</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdisk">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An `os_disk` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Overprovision</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Azure over-provision Virtual Machines in this Scale Set? This means that multiple Virtual Machines will be provisioned and Azure will keep the instances which become available first - which improves provisioning success rates and improves deployment time. You&#39;re not billed for these over-provisioned VM&#39;s and they don&#39;t count towards the Subscription Quota. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Plan</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetplan">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Priority of this Virtual Machine Scale Set. Possible values are `Regular` and `Spot`. Defaults to `Regular`. Changing this value forces a new resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Provision<wbr>Vm<wbr>Agent</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Azure VM Agent be provisioned on each Virtual Machine in the Scale Set? Defaults to `true`. Changing this value forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proximity<wbr>Placement<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Proximity Placement Group in which the Virtual Machine Scale Set should be assigned to. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Resource Group in which the Linux Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetrollingupgradepolicy">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `rolling_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale<wbr>In<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The scale-in policy rule that decides which virtual machines are chosen for removal when a Virtual Machine Scale Set is scaled in. Possible values for the scale-in policy rules are `Default`, `NewestVM` and `OldestVM`, defaults to `Default`. For more information about scale in policy, please [refer to this doc](https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-scale-in-policy).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secrets</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecret">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `secret` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Single<wbr>Placement<wbr>Group</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should this Virtual Machine Scale Set be limited to a Single Placement Group, which means the number of instances will be capped at 100 Virtual Machines. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sku</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of an Image which each Virtual Machine in this Scale Set should be based on.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Reference</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsourceimagereference">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `source_image_reference` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags which should be assigned to this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Terminate<wbr>Notification</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetterminatenotification">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upgrade<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how Upgrades (e.g. changing the Image/SKU) should be performed to Virtual Machine Instances. Possible values are `Automatic`, `Manual` and `Rolling`. Defaults to `Manual`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone<wbr>Balance</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Virtual Machines in this Scale Set be strictly evenly distributed across Availability Zones? Defaults to `false`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zones</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Availability Zones in which the Virtual Machines in this Scale Set should be created in. Changing this forces a new resource to be created.
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
            <td class="align-top">Additional<wbr>Capabilities</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadditionalcapabilities">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Password</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Ssh<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadminsshkey">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Admin<wbr>Ssh<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `admin_ssh_key` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Username</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The username of the local administrator on each Virtual Machine Scale Set instance. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Automatic<wbr>Os<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetautomaticosupgradepolicy">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Boot<wbr>Diagnostics</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetbootdiagnostics">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `boot_diagnostics` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Computer<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The prefix which should be used for the name of the Virtual Machines in this Scale Set. If unspecified this defaults to the value for the `name` field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Data</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Base64-Encoded Custom Data which should be used for this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Data<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetdatadisk">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disable<wbr>Password<wbr>Authentication</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Password Authentication be disabled on this Virtual Machine Scale Set? Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Do<wbr>Not<wbr>Run<wbr>Extensions<wbr>On<wbr>Overprovisioned<wbr>Machines</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Virtual Machine Extensions be run on Overprovisioned Virtual Machines in the Scale Set? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Eviction<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Policy which should be used Virtual Machines are Evicted from the Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Health<wbr>Probe<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of a Load Balancer Probe which should be used to determine the health of an instance. Changing this forces a new resource to be created. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetidentity">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instances</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The number of Virtual Machines in the Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Azure location where the Linux Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Bid<wbr>Price</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in this Scale Set should not be evicted for price reasons.
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterface">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Os<wbr>Disk</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdisk">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An `os_disk` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Overprovision</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Azure over-provision Virtual Machines in this Scale Set? This means that multiple Virtual Machines will be provisioned and Azure will keep the instances which become available first - which improves provisioning success rates and improves deployment time. You&#39;re not billed for these over-provisioned VM&#39;s and they don&#39;t count towards the Subscription Quota. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Plan</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetplan">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Priority of this Virtual Machine Scale Set. Possible values are `Regular` and `Spot`. Defaults to `Regular`. Changing this value forces a new resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Provision<wbr>Vm<wbr>Agent</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Azure VM Agent be provisioned on each Virtual Machine in the Scale Set? Defaults to `true`. Changing this value forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proximity<wbr>Placement<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Proximity Placement Group in which the Virtual Machine Scale Set should be assigned to. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Resource Group in which the Linux Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetrollingupgradepolicy">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `rolling_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale<wbr>In<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The scale-in policy rule that decides which virtual machines are chosen for removal when a Virtual Machine Scale Set is scaled in. Possible values for the scale-in policy rules are `Default`, `NewestVM` and `OldestVM`, defaults to `Default`. For more information about scale in policy, please [refer to this doc](https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-scale-in-policy).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secrets</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecret">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `secret` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Single<wbr>Placement<wbr>Group</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should this Virtual Machine Scale Set be limited to a Single Placement Group, which means the number of instances will be capped at 100 Virtual Machines. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sku</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of an Image which each Virtual Machine in this Scale Set should be based on.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Reference</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsourceimagereference">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `source_image_reference` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags which should be assigned to this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Terminate<wbr>Notification</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetterminatenotification">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upgrade<wbr>Mode</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how Upgrades (e.g. changing the Image/SKU) should be performed to Virtual Machine Instances. Possible values are `Automatic`, `Manual` and `Rolling`. Defaults to `Manual`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone<wbr>Balance</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Virtual Machines in this Scale Set be strictly evenly distributed across Availability Zones? Defaults to `false`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zones</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Availability Zones in which the Virtual Machines in this Scale Set should be created in. Changing this forces a new resource to be created.
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
            <td class="align-top">additional<wbr>Capabilities</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadditionalcapabilities">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Password</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Ssh<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadminsshkey">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Admin<wbr>Ssh<wbr>Key[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `admin_ssh_key` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Username</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The username of the local administrator on each Virtual Machine Scale Set instance. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">automatic<wbr>Os<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetautomaticosupgradepolicy">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">boot<wbr>Diagnostics</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetbootdiagnostics">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `boot_diagnostics` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">computer<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The prefix which should be used for the name of the Virtual Machines in this Scale Set. If unspecified this defaults to the value for the `name` field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom<wbr>Data</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Base64-Encoded Custom Data which should be used for this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">data<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetdatadisk">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disable<wbr>Password<wbr>Authentication</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Password Authentication be disabled on this Virtual Machine Scale Set? Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">do<wbr>Not<wbr>Run<wbr>Extensions<wbr>On<wbr>Overprovisioned<wbr>Machines</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Virtual Machine Extensions be run on Overprovisioned Virtual Machines in the Scale Set? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">eviction<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Policy which should be used Virtual Machines are Evicted from the Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">health<wbr>Probe<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of a Load Balancer Probe which should be used to determine the health of an instance. Changing this forces a new resource to be created. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetidentity">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instances</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The number of Virtual Machines in the Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Azure location where the Linux Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Bid<wbr>Price</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in this Scale Set should not be evicted for price reasons.
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterface">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">os<wbr>Disk</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdisk">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An `os_disk` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">overprovision</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Azure over-provision Virtual Machines in this Scale Set? This means that multiple Virtual Machines will be provisioned and Azure will keep the instances which become available first - which improves provisioning success rates and improves deployment time. You&#39;re not billed for these over-provisioned VM&#39;s and they don&#39;t count towards the Subscription Quota. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">plan</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetplan">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Priority of this Virtual Machine Scale Set. Possible values are `Regular` and `Spot`. Defaults to `Regular`. Changing this value forces a new resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">provision<wbr>Vm<wbr>Agent</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Azure VM Agent be provisioned on each Virtual Machine in the Scale Set? Defaults to `true`. Changing this value forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proximity<wbr>Placement<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Proximity Placement Group in which the Virtual Machine Scale Set should be assigned to. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Resource Group in which the Linux Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetrollingupgradepolicy">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `rolling_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale<wbr>In<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The scale-in policy rule that decides which virtual machines are chosen for removal when a Virtual Machine Scale Set is scaled in. Possible values for the scale-in policy rules are `Default`, `NewestVM` and `OldestVM`, defaults to `Default`. For more information about scale in policy, please [refer to this doc](https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-scale-in-policy).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secrets</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecret">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `secret` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">single<wbr>Placement<wbr>Group</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should this Virtual Machine Scale Set be limited to a Single Placement Group, which means the number of instances will be capped at 100 Virtual Machines. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sku</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Image<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of an Image which each Virtual Machine in this Scale Set should be based on.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Image<wbr>Reference</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsourceimagereference">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `source_image_reference` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags which should be assigned to this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">terminate<wbr>Notification</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetterminatenotification">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upgrade<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how Upgrades (e.g. changing the Image/SKU) should be performed to Virtual Machine Instances. Possible values are `Automatic`, `Manual` and `Rolling`. Defaults to `Manual`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone<wbr>Balance</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Virtual Machines in this Scale Set be strictly evenly distributed across Availability Zones? Defaults to `false`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zones</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Availability Zones in which the Virtual Machines in this Scale Set should be created in. Changing this forces a new resource to be created.
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
            <td class="align-top">additional_<wbr>capabilities</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadditionalcapabilities">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin_<wbr>password</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin_<wbr>ssh_<wbr>keys</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadminsshkey">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Admin<wbr>Ssh<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `admin_ssh_key` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin_<wbr>username</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The username of the local administrator on each Virtual Machine Scale Set instance. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">automatic_<wbr>os_<wbr>upgrade_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetautomaticosupgradepolicy">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">boot_<wbr>diagnostics</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetbootdiagnostics">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `boot_diagnostics` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">computer_<wbr>name_<wbr>prefix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The prefix which should be used for the name of the Virtual Machines in this Scale Set. If unspecified this defaults to the value for the `name` field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom_<wbr>data</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Base64-Encoded Custom Data which should be used for this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">data_<wbr>disks</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetdatadisk">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disable_<wbr>password_<wbr>authentication</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Password Authentication be disabled on this Virtual Machine Scale Set? Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">do_<wbr>not_<wbr>run_<wbr>extensions_<wbr>on_<wbr>overprovisioned_<wbr>machines</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Virtual Machine Extensions be run on Overprovisioned Virtual Machines in the Scale Set? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">eviction_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Policy which should be used Virtual Machines are Evicted from the Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">health_<wbr>probe_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of a Load Balancer Probe which should be used to determine the health of an instance. Changing this forces a new resource to be created. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetidentity">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instances</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The number of Virtual Machines in the Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Azure location where the Linux Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max_<wbr>bid_<wbr>price</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in this Scale Set should not be evicted for price reasons.
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>interfaces</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterface">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">os_<wbr>disk</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdisk">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An `os_disk` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">overprovision</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Azure over-provision Virtual Machines in this Scale Set? This means that multiple Virtual Machines will be provisioned and Azure will keep the instances which become available first - which improves provisioning success rates and improves deployment time. You&#39;re not billed for these over-provisioned VM&#39;s and they don&#39;t count towards the Subscription Quota. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">plan</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetplan">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Priority of this Virtual Machine Scale Set. Possible values are `Regular` and `Spot`. Defaults to `Regular`. Changing this value forces a new resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">provision_<wbr>vm_<wbr>agent</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Azure VM Agent be provisioned on each Virtual Machine in the Scale Set? Defaults to `true`. Changing this value forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proximity_<wbr>placement_<wbr>group_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Proximity Placement Group in which the Virtual Machine Scale Set should be assigned to. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>group_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Resource Group in which the Linux Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rolling_<wbr>upgrade_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetrollingupgradepolicy">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `rolling_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale_<wbr>in_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The scale-in policy rule that decides which virtual machines are chosen for removal when a Virtual Machine Scale Set is scaled in. Possible values for the scale-in policy rules are `Default`, `NewestVM` and `OldestVM`, defaults to `Default`. For more information about scale in policy, please [refer to this doc](https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-scale-in-policy).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secrets</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecret">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `secret` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">single_<wbr>placement_<wbr>group</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should this Virtual Machine Scale Set be limited to a Single Placement Group, which means the number of instances will be capped at 100 Virtual Machines. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sku</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>image_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of an Image which each Virtual Machine in this Scale Set should be based on.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>image_<wbr>reference</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsourceimagereference">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `source_image_reference` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags which should be assigned to this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">terminate_<wbr>notification</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetterminatenotification">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upgrade_<wbr>mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how Upgrades (e.g. changing the Image/SKU) should be performed to Virtual Machine Instances. Possible values are `Automatic`, `Manual` and `Rolling`. Defaults to `Manual`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone_<wbr>balance</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Virtual Machines in this Scale Set be strictly evenly distributed across Availability Zones? Defaults to `false`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zones</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Availability Zones in which the Virtual Machines in this Scale Set should be created in. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## LinuxVirtualMachineScaleSet Output Properties

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
            <td class="align-top">Additional<wbr>Capabilities</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadditionalcapabilities">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Password</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Ssh<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadminsshkey">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Admin<wbr>Ssh<wbr>Key&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `admin_ssh_key` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Username</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The username of the local administrator on each Virtual Machine Scale Set instance. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Automatic<wbr>Os<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetautomaticosupgradepolicy">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Boot<wbr>Diagnostics</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetbootdiagnostics">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `boot_diagnostics` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Computer<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The prefix which should be used for the name of the Virtual Machines in this Scale Set. If unspecified this defaults to the value for the `name` field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Data</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The Base64-Encoded Custom Data which should be used for this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Data<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetdatadisk">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `data_disk` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disable<wbr>Password<wbr>Authentication</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Should Password Authentication be disabled on this Virtual Machine Scale Set? Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Do<wbr>Not<wbr>Run<wbr>Extensions<wbr>On<wbr>Overprovisioned<wbr>Machines</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Should Virtual Machine Extensions be run on Overprovisioned Virtual Machines in the Scale Set? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Eviction<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The Policy which should be used Virtual Machines are Evicted from the Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Health<wbr>Probe<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The ID of a Load Balancer Probe which should be used to determine the health of an instance. Changing this forces a new resource to be created. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetidentity">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `identity` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instances</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The number of Virtual Machines in the Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Azure location where the Linux Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Bid<wbr>Price</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in this Scale Set should not be evicted for price reasons.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterface">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Os<wbr>Disk</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdisk">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk</a></code>
            </td>
            <td class="align-top">{{% md %}} An `os_disk` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Overprovision</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Should Azure over-provision Virtual Machines in this Scale Set? This means that multiple Virtual Machines will be provisioned and Azure will keep the instances which become available first - which improves provisioning success rates and improves deployment time. You&#39;re not billed for these over-provisioned VM&#39;s and they don&#39;t count towards the Subscription Quota. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Plan</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetplan">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan?</a></code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The Priority of this Virtual Machine Scale Set. Possible values are `Regular` and `Spot`. Defaults to `Regular`. Changing this value forces a new resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Provision<wbr>Vm<wbr>Agent</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Should the Azure VM Agent be provisioned on each Virtual Machine in the Scale Set? Defaults to `true`. Changing this value forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proximity<wbr>Placement<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the Proximity Placement Group in which the Virtual Machine Scale Set should be assigned to. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Resource Group in which the Linux Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetrollingupgradepolicy">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `rolling_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale<wbr>In<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The scale-in policy rule that decides which virtual machines are chosen for removal when a Virtual Machine Scale Set is scaled in. Possible values for the scale-in policy rules are `Default`, `NewestVM` and `OldestVM`, defaults to `Default`. For more information about scale in policy, please [refer to this doc](https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-scale-in-policy).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secrets</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecret">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `secret` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Single<wbr>Placement<wbr>Group</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Should this Virtual Machine Scale Set be limited to a Single Placement Group, which means the number of instances will be capped at 100 Virtual Machines. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sku</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The ID of an Image which each Virtual Machine in this Scale Set should be based on.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Reference</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsourceimagereference">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `source_image_reference` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of tags which should be assigned to this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Terminate<wbr>Notification</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetterminatenotification">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification</a></code>
            </td>
            <td class="align-top">{{% md %}} A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unique<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Unique ID for this Linux Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upgrade<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies how Upgrades (e.g. changing the Image/SKU) should be performed to Virtual Machine Instances. Possible values are `Automatic`, `Manual` and `Rolling`. Defaults to `Manual`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone<wbr>Balance</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Should the Virtual Machines in this Scale Set be strictly evenly distributed across Availability Zones? Defaults to `false`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zones</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} A list of Availability Zones in which the Virtual Machines in this Scale Set should be created in. Changing this forces a new resource to be created.
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
            <td class="align-top">Additional<wbr>Capabilities</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadditionalcapabilities">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities</a></code>
            </td>
            <td class="align-top">{{% md %}} A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Password</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Ssh<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadminsshkey">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Admin<wbr>Ssh<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `admin_ssh_key` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Username</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The username of the local administrator on each Virtual Machine Scale Set instance. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Automatic<wbr>Os<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetautomaticosupgradepolicy">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Boot<wbr>Diagnostics</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetbootdiagnostics">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics</a></code>
            </td>
            <td class="align-top">{{% md %}} A `boot_diagnostics` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Computer<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The prefix which should be used for the name of the Virtual Machines in this Scale Set. If unspecified this defaults to the value for the `name` field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Data</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The Base64-Encoded Custom Data which should be used for this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Data<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetdatadisk">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `data_disk` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disable<wbr>Password<wbr>Authentication</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Should Password Authentication be disabled on this Virtual Machine Scale Set? Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Do<wbr>Not<wbr>Run<wbr>Extensions<wbr>On<wbr>Overprovisioned<wbr>Machines</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Should Virtual Machine Extensions be run on Overprovisioned Virtual Machines in the Scale Set? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Eviction<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The Policy which should be used Virtual Machines are Evicted from the Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Health<wbr>Probe<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of a Load Balancer Probe which should be used to determine the health of an instance. Changing this forces a new resource to be created. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetidentity">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity</a></code>
            </td>
            <td class="align-top">{{% md %}} A `identity` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instances</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The number of Virtual Machines in the Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Azure location where the Linux Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Bid<wbr>Price</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in this Scale Set should not be evicted for price reasons.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterface">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Os<wbr>Disk</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdisk">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk</a></code>
            </td>
            <td class="align-top">{{% md %}} An `os_disk` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Overprovision</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Should Azure over-provision Virtual Machines in this Scale Set? This means that multiple Virtual Machines will be provisioned and Azure will keep the instances which become available first - which improves provisioning success rates and improves deployment time. You&#39;re not billed for these over-provisioned VM&#39;s and they don&#39;t count towards the Subscription Quota. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Plan</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetplan">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan</a></code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The Priority of this Virtual Machine Scale Set. Possible values are `Regular` and `Spot`. Defaults to `Regular`. Changing this value forces a new resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Provision<wbr>Vm<wbr>Agent</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Should the Azure VM Agent be provisioned on each Virtual Machine in the Scale Set? Defaults to `true`. Changing this value forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proximity<wbr>Placement<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the Proximity Placement Group in which the Virtual Machine Scale Set should be assigned to. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Resource Group in which the Linux Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetrollingupgradepolicy">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} A `rolling_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale<wbr>In<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The scale-in policy rule that decides which virtual machines are chosen for removal when a Virtual Machine Scale Set is scaled in. Possible values for the scale-in policy rules are `Default`, `NewestVM` and `OldestVM`, defaults to `Default`. For more information about scale in policy, please [refer to this doc](https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-scale-in-policy).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secrets</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecret">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `secret` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Single<wbr>Placement<wbr>Group</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Should this Virtual Machine Scale Set be limited to a Single Placement Group, which means the number of instances will be capped at 100 Virtual Machines. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sku</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of an Image which each Virtual Machine in this Scale Set should be based on.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Reference</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsourceimagereference">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference</a></code>
            </td>
            <td class="align-top">{{% md %}} A `source_image_reference` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of tags which should be assigned to this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Terminate<wbr>Notification</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetterminatenotification">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification</a></code>
            </td>
            <td class="align-top">{{% md %}} A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unique<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Unique ID for this Linux Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upgrade<wbr>Mode</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies how Upgrades (e.g. changing the Image/SKU) should be performed to Virtual Machine Instances. Possible values are `Automatic`, `Manual` and `Rolling`. Defaults to `Manual`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone<wbr>Balance</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Should the Virtual Machines in this Scale Set be strictly evenly distributed across Availability Zones? Defaults to `false`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zones</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} A list of Availability Zones in which the Virtual Machines in this Scale Set should be created in. Changing this forces a new resource to be created.
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
            <td class="align-top">additional<wbr>Capabilities</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadditionalcapabilities">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Password</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Ssh<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadminsshkey">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Admin<wbr>Ssh<wbr>Key[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `admin_ssh_key` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Username</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The username of the local administrator on each Virtual Machine Scale Set instance. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">automatic<wbr>Os<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetautomaticosupgradepolicy">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">boot<wbr>Diagnostics</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetbootdiagnostics">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `boot_diagnostics` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">computer<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The prefix which should be used for the name of the Virtual Machines in this Scale Set. If unspecified this defaults to the value for the `name` field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom<wbr>Data</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The Base64-Encoded Custom Data which should be used for this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">data<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetdatadisk">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `data_disk` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disable<wbr>Password<wbr>Authentication</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Should Password Authentication be disabled on this Virtual Machine Scale Set? Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">do<wbr>Not<wbr>Run<wbr>Extensions<wbr>On<wbr>Overprovisioned<wbr>Machines</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Should Virtual Machine Extensions be run on Overprovisioned Virtual Machines in the Scale Set? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">eviction<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The Policy which should be used Virtual Machines are Evicted from the Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">health<wbr>Probe<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The ID of a Load Balancer Probe which should be used to determine the health of an instance. Changing this forces a new resource to be created. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetidentity">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `identity` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instances</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The number of Virtual Machines in the Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Azure location where the Linux Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Bid<wbr>Price</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in this Scale Set should not be evicted for price reasons.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterface">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface[]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">os<wbr>Disk</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdisk">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk</a></code>
            </td>
            <td class="align-top">{{% md %}} An `os_disk` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">overprovision</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Should Azure over-provision Virtual Machines in this Scale Set? This means that multiple Virtual Machines will be provisioned and Azure will keep the instances which become available first - which improves provisioning success rates and improves deployment time. You&#39;re not billed for these over-provisioned VM&#39;s and they don&#39;t count towards the Subscription Quota. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">plan</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetplan">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan?</a></code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The Priority of this Virtual Machine Scale Set. Possible values are `Regular` and `Spot`. Defaults to `Regular`. Changing this value forces a new resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">provision<wbr>Vm<wbr>Agent</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Should the Azure VM Agent be provisioned on each Virtual Machine in the Scale Set? Defaults to `true`. Changing this value forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proximity<wbr>Placement<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the Proximity Placement Group in which the Virtual Machine Scale Set should be assigned to. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Resource Group in which the Linux Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetrollingupgradepolicy">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `rolling_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale<wbr>In<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The scale-in policy rule that decides which virtual machines are chosen for removal when a Virtual Machine Scale Set is scaled in. Possible values for the scale-in policy rules are `Default`, `NewestVM` and `OldestVM`, defaults to `Default`. For more information about scale in policy, please [refer to this doc](https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-scale-in-policy).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secrets</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecret">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `secret` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">single<wbr>Placement<wbr>Group</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Should this Virtual Machine Scale Set be limited to a Single Placement Group, which means the number of instances will be capped at 100 Virtual Machines. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sku</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Image<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The ID of an Image which each Virtual Machine in this Scale Set should be based on.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Image<wbr>Reference</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsourceimagereference">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `source_image_reference` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of tags which should be assigned to this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">terminate<wbr>Notification</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetterminatenotification">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification</a></code>
            </td>
            <td class="align-top">{{% md %}} A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unique<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Unique ID for this Linux Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upgrade<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies how Upgrades (e.g. changing the Image/SKU) should be performed to Virtual Machine Instances. Possible values are `Automatic`, `Manual` and `Rolling`. Defaults to `Manual`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone<wbr>Balance</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Should the Virtual Machines in this Scale Set be strictly evenly distributed across Availability Zones? Defaults to `false`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zones</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} A list of Availability Zones in which the Virtual Machines in this Scale Set should be created in. Changing this forces a new resource to be created.
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
            <td class="align-top">additional_<wbr>capabilities</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadditionalcapabilities">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin_<wbr>password</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin_<wbr>ssh_<wbr>keys</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadminsshkey">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Admin<wbr>Ssh<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `admin_ssh_key` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin_<wbr>username</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The username of the local administrator on each Virtual Machine Scale Set instance. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">automatic_<wbr>os_<wbr>upgrade_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetautomaticosupgradepolicy">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">boot_<wbr>diagnostics</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetbootdiagnostics">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `boot_diagnostics` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">computer_<wbr>name_<wbr>prefix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The prefix which should be used for the name of the Virtual Machines in this Scale Set. If unspecified this defaults to the value for the `name` field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom_<wbr>data</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Base64-Encoded Custom Data which should be used for this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">data_<wbr>disks</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetdatadisk">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `data_disk` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disable_<wbr>password_<wbr>authentication</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Should Password Authentication be disabled on this Virtual Machine Scale Set? Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">do_<wbr>not_<wbr>run_<wbr>extensions_<wbr>on_<wbr>overprovisioned_<wbr>machines</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Should Virtual Machine Extensions be run on Overprovisioned Virtual Machines in the Scale Set? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">eviction_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Policy which should be used Virtual Machines are Evicted from the Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">health_<wbr>probe_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The ID of a Load Balancer Probe which should be used to determine the health of an instance. Changing this forces a new resource to be created. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetidentity">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `identity` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instances</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The number of Virtual Machines in the Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Azure location where the Linux Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max_<wbr>bid_<wbr>price</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in this Scale Set should not be evicted for price reasons.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>interfaces</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterface">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">os_<wbr>disk</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdisk">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk]</a></code>
            </td>
            <td class="align-top">{{% md %}} An `os_disk` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">overprovision</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Should Azure over-provision Virtual Machines in this Scale Set? This means that multiple Virtual Machines will be provisioned and Azure will keep the instances which become available first - which improves provisioning success rates and improves deployment time. You&#39;re not billed for these over-provisioned VM&#39;s and they don&#39;t count towards the Subscription Quota. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">plan</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetplan">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan]</a></code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Priority of this Virtual Machine Scale Set. Possible values are `Regular` and `Spot`. Defaults to `Regular`. Changing this value forces a new resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">provision_<wbr>vm_<wbr>agent</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Should the Azure VM Agent be provisioned on each Virtual Machine in the Scale Set? Defaults to `true`. Changing this value forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proximity_<wbr>placement_<wbr>group_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the Proximity Placement Group in which the Virtual Machine Scale Set should be assigned to. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>group_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Resource Group in which the Linux Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rolling_<wbr>upgrade_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetrollingupgradepolicy">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `rolling_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale_<wbr>in_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The scale-in policy rule that decides which virtual machines are chosen for removal when a Virtual Machine Scale Set is scaled in. Possible values for the scale-in policy rules are `Default`, `NewestVM` and `OldestVM`, defaults to `Default`. For more information about scale in policy, please [refer to this doc](https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-scale-in-policy).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secrets</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecret">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `secret` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">single_<wbr>placement_<wbr>group</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Should this Virtual Machine Scale Set be limited to a Single Placement Group, which means the number of instances will be capped at 100 Virtual Machines. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sku</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>image_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The ID of an Image which each Virtual Machine in this Scale Set should be based on.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>image_<wbr>reference</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsourceimagereference">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `source_image_reference` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of tags which should be assigned to this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">terminate_<wbr>notification</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetterminatenotification">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unique_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Unique ID for this Linux Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upgrade_<wbr>mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Specifies how Upgrades (e.g. changing the Image/SKU) should be performed to Virtual Machine Instances. Possible values are `Automatic`, `Manual` and `Rolling`. Defaults to `Manual`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone_<wbr>balance</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Should the Virtual Machines in this Scale Set be strictly evenly distributed across Availability Zones? Defaults to `false`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zones</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} A list of Availability Zones in which the Virtual Machines in this Scale Set should be created in. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing LinuxVirtualMachineScaleSet Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/compute/#LinuxVirtualMachineScaleSetState">LinuxVirtualMachineScaleSetState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/compute/#LinuxVirtualMachineScaleSet">LinuxVirtualMachineScaleSet</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>additional_capabilities=None<span class="p">, </span>admin_password=None<span class="p">, </span>admin_ssh_keys=None<span class="p">, </span>admin_username=None<span class="p">, </span>automatic_os_upgrade_policy=None<span class="p">, </span>boot_diagnostics=None<span class="p">, </span>computer_name_prefix=None<span class="p">, </span>custom_data=None<span class="p">, </span>data_disks=None<span class="p">, </span>disable_password_authentication=None<span class="p">, </span>do_not_run_extensions_on_overprovisioned_machines=None<span class="p">, </span>eviction_policy=None<span class="p">, </span>health_probe_id=None<span class="p">, </span>identity=None<span class="p">, </span>instances=None<span class="p">, </span>location=None<span class="p">, </span>max_bid_price=None<span class="p">, </span>name=None<span class="p">, </span>network_interfaces=None<span class="p">, </span>os_disk=None<span class="p">, </span>overprovision=None<span class="p">, </span>plan=None<span class="p">, </span>priority=None<span class="p">, </span>provision_vm_agent=None<span class="p">, </span>proximity_placement_group_id=None<span class="p">, </span>resource_group_name=None<span class="p">, </span>rolling_upgrade_policy=None<span class="p">, </span>scale_in_policy=None<span class="p">, </span>secrets=None<span class="p">, </span>single_placement_group=None<span class="p">, </span>sku=None<span class="p">, </span>source_image_id=None<span class="p">, </span>source_image_reference=None<span class="p">, </span>tags=None<span class="p">, </span>terminate_notification=None<span class="p">, </span>unique_id=None<span class="p">, </span>upgrade_mode=None<span class="p">, </span>zone_balance=None<span class="p">, </span>zones=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetLinuxVirtualMachineScaleSet<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetState">LinuxVirtualMachineScaleSetState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSet">LinuxVirtualMachineScaleSet</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSet.html">LinuxVirtualMachineScaleSet</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetState.html">LinuxVirtualMachineScaleSetState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing LinuxVirtualMachineScaleSet resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Additional<wbr>Capabilities</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadditionalcapabilities">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Password</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Ssh<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadminsshkey">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Admin<wbr>Ssh<wbr>Key<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `admin_ssh_key` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Username</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The username of the local administrator on each Virtual Machine Scale Set instance. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Automatic<wbr>Os<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetautomaticosupgradepolicy">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Boot<wbr>Diagnostics</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetbootdiagnostics">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `boot_diagnostics` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Computer<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The prefix which should be used for the name of the Virtual Machines in this Scale Set. If unspecified this defaults to the value for the `name` field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Data</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Base64-Encoded Custom Data which should be used for this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Data<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetdatadisk">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disable<wbr>Password<wbr>Authentication</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Password Authentication be disabled on this Virtual Machine Scale Set? Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Do<wbr>Not<wbr>Run<wbr>Extensions<wbr>On<wbr>Overprovisioned<wbr>Machines</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Virtual Machine Extensions be run on Overprovisioned Virtual Machines in the Scale Set? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Eviction<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Policy which should be used Virtual Machines are Evicted from the Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Health<wbr>Probe<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of a Load Balancer Probe which should be used to determine the health of an instance. Changing this forces a new resource to be created. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetidentity">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instances</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of Virtual Machines in the Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Azure location where the Linux Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Bid<wbr>Price</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in this Scale Set should not be evicted for price reasons.
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterface">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Os<wbr>Disk</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdisk">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An `os_disk` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Overprovision</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Azure over-provision Virtual Machines in this Scale Set? This means that multiple Virtual Machines will be provisioned and Azure will keep the instances which become available first - which improves provisioning success rates and improves deployment time. You&#39;re not billed for these over-provisioned VM&#39;s and they don&#39;t count towards the Subscription Quota. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Plan</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetplan">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Priority of this Virtual Machine Scale Set. Possible values are `Regular` and `Spot`. Defaults to `Regular`. Changing this value forces a new resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Provision<wbr>Vm<wbr>Agent</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Azure VM Agent be provisioned on each Virtual Machine in the Scale Set? Defaults to `true`. Changing this value forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proximity<wbr>Placement<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Proximity Placement Group in which the Virtual Machine Scale Set should be assigned to. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Resource Group in which the Linux Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetrollingupgradepolicy">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `rolling_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale<wbr>In<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The scale-in policy rule that decides which virtual machines are chosen for removal when a Virtual Machine Scale Set is scaled in. Possible values for the scale-in policy rules are `Default`, `NewestVM` and `OldestVM`, defaults to `Default`. For more information about scale in policy, please [refer to this doc](https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-scale-in-policy).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secrets</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecret">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `secret` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Single<wbr>Placement<wbr>Group</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should this Virtual Machine Scale Set be limited to a Single Placement Group, which means the number of instances will be capped at 100 Virtual Machines. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sku</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of an Image which each Virtual Machine in this Scale Set should be based on.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Reference</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsourceimagereference">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `source_image_reference` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags which should be assigned to this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Terminate<wbr>Notification</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetterminatenotification">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unique<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Unique ID for this Linux Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upgrade<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how Upgrades (e.g. changing the Image/SKU) should be performed to Virtual Machine Instances. Possible values are `Automatic`, `Manual` and `Rolling`. Defaults to `Manual`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone<wbr>Balance</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Virtual Machines in this Scale Set be strictly evenly distributed across Availability Zones? Defaults to `false`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zones</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Availability Zones in which the Virtual Machines in this Scale Set should be created in. Changing this forces a new resource to be created.
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
            <td class="align-top">Additional<wbr>Capabilities</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadditionalcapabilities">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Password</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Ssh<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadminsshkey">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Admin<wbr>Ssh<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `admin_ssh_key` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Username</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The username of the local administrator on each Virtual Machine Scale Set instance. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Automatic<wbr>Os<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetautomaticosupgradepolicy">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Boot<wbr>Diagnostics</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetbootdiagnostics">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `boot_diagnostics` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Computer<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The prefix which should be used for the name of the Virtual Machines in this Scale Set. If unspecified this defaults to the value for the `name` field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Data</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Base64-Encoded Custom Data which should be used for this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Data<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetdatadisk">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disable<wbr>Password<wbr>Authentication</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Password Authentication be disabled on this Virtual Machine Scale Set? Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Do<wbr>Not<wbr>Run<wbr>Extensions<wbr>On<wbr>Overprovisioned<wbr>Machines</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Virtual Machine Extensions be run on Overprovisioned Virtual Machines in the Scale Set? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Eviction<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Policy which should be used Virtual Machines are Evicted from the Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Health<wbr>Probe<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of a Load Balancer Probe which should be used to determine the health of an instance. Changing this forces a new resource to be created. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetidentity">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instances</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of Virtual Machines in the Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Azure location where the Linux Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Bid<wbr>Price</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in this Scale Set should not be evicted for price reasons.
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterface">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Os<wbr>Disk</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdisk">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An `os_disk` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Overprovision</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Azure over-provision Virtual Machines in this Scale Set? This means that multiple Virtual Machines will be provisioned and Azure will keep the instances which become available first - which improves provisioning success rates and improves deployment time. You&#39;re not billed for these over-provisioned VM&#39;s and they don&#39;t count towards the Subscription Quota. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Plan</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetplan">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Priority of this Virtual Machine Scale Set. Possible values are `Regular` and `Spot`. Defaults to `Regular`. Changing this value forces a new resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Provision<wbr>Vm<wbr>Agent</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Azure VM Agent be provisioned on each Virtual Machine in the Scale Set? Defaults to `true`. Changing this value forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proximity<wbr>Placement<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Proximity Placement Group in which the Virtual Machine Scale Set should be assigned to. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Resource Group in which the Linux Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetrollingupgradepolicy">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `rolling_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale<wbr>In<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The scale-in policy rule that decides which virtual machines are chosen for removal when a Virtual Machine Scale Set is scaled in. Possible values for the scale-in policy rules are `Default`, `NewestVM` and `OldestVM`, defaults to `Default`. For more information about scale in policy, please [refer to this doc](https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-scale-in-policy).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secrets</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecret">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `secret` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Single<wbr>Placement<wbr>Group</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should this Virtual Machine Scale Set be limited to a Single Placement Group, which means the number of instances will be capped at 100 Virtual Machines. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sku</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of an Image which each Virtual Machine in this Scale Set should be based on.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Image<wbr>Reference</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsourceimagereference">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `source_image_reference` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags which should be assigned to this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Terminate<wbr>Notification</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetterminatenotification">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unique<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Unique ID for this Linux Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upgrade<wbr>Mode</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how Upgrades (e.g. changing the Image/SKU) should be performed to Virtual Machine Instances. Possible values are `Automatic`, `Manual` and `Rolling`. Defaults to `Manual`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone<wbr>Balance</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Virtual Machines in this Scale Set be strictly evenly distributed across Availability Zones? Defaults to `false`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zones</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Availability Zones in which the Virtual Machines in this Scale Set should be created in. Changing this forces a new resource to be created.
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
            <td class="align-top">additional<wbr>Capabilities</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadditionalcapabilities">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Password</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Ssh<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadminsshkey">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Admin<wbr>Ssh<wbr>Key[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `admin_ssh_key` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Username</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The username of the local administrator on each Virtual Machine Scale Set instance. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">automatic<wbr>Os<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetautomaticosupgradepolicy">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">boot<wbr>Diagnostics</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetbootdiagnostics">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `boot_diagnostics` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">computer<wbr>Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The prefix which should be used for the name of the Virtual Machines in this Scale Set. If unspecified this defaults to the value for the `name` field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom<wbr>Data</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Base64-Encoded Custom Data which should be used for this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">data<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetdatadisk">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disable<wbr>Password<wbr>Authentication</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Password Authentication be disabled on this Virtual Machine Scale Set? Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">do<wbr>Not<wbr>Run<wbr>Extensions<wbr>On<wbr>Overprovisioned<wbr>Machines</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Virtual Machine Extensions be run on Overprovisioned Virtual Machines in the Scale Set? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">eviction<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Policy which should be used Virtual Machines are Evicted from the Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">health<wbr>Probe<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of a Load Balancer Probe which should be used to determine the health of an instance. Changing this forces a new resource to be created. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetidentity">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instances</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of Virtual Machines in the Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Azure location where the Linux Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Bid<wbr>Price</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in this Scale Set should not be evicted for price reasons.
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterface">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">os<wbr>Disk</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdisk">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An `os_disk` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">overprovision</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Azure over-provision Virtual Machines in this Scale Set? This means that multiple Virtual Machines will be provisioned and Azure will keep the instances which become available first - which improves provisioning success rates and improves deployment time. You&#39;re not billed for these over-provisioned VM&#39;s and they don&#39;t count towards the Subscription Quota. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">plan</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetplan">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Priority of this Virtual Machine Scale Set. Possible values are `Regular` and `Spot`. Defaults to `Regular`. Changing this value forces a new resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">provision<wbr>Vm<wbr>Agent</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Azure VM Agent be provisioned on each Virtual Machine in the Scale Set? Defaults to `true`. Changing this value forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proximity<wbr>Placement<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Proximity Placement Group in which the Virtual Machine Scale Set should be assigned to. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Resource Group in which the Linux Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetrollingupgradepolicy">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `rolling_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale<wbr>In<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The scale-in policy rule that decides which virtual machines are chosen for removal when a Virtual Machine Scale Set is scaled in. Possible values for the scale-in policy rules are `Default`, `NewestVM` and `OldestVM`, defaults to `Default`. For more information about scale in policy, please [refer to this doc](https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-scale-in-policy).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secrets</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecret">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `secret` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">single<wbr>Placement<wbr>Group</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should this Virtual Machine Scale Set be limited to a Single Placement Group, which means the number of instances will be capped at 100 Virtual Machines. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sku</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Image<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of an Image which each Virtual Machine in this Scale Set should be based on.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Image<wbr>Reference</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsourceimagereference">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `source_image_reference` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags which should be assigned to this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">terminate<wbr>Notification</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetterminatenotification">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unique<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Unique ID for this Linux Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upgrade<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how Upgrades (e.g. changing the Image/SKU) should be performed to Virtual Machine Instances. Possible values are `Automatic`, `Manual` and `Rolling`. Defaults to `Manual`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone<wbr>Balance</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Virtual Machines in this Scale Set be strictly evenly distributed across Availability Zones? Defaults to `false`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zones</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Availability Zones in which the Virtual Machines in this Scale Set should be created in. Changing this forces a new resource to be created.
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
            <td class="align-top">additional_<wbr>capabilities</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadditionalcapabilities">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin_<wbr>password</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin_<wbr>ssh_<wbr>keys</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetadminsshkey">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Admin<wbr>Ssh<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `admin_ssh_key` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin_<wbr>username</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The username of the local administrator on each Virtual Machine Scale Set instance. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">automatic_<wbr>os_<wbr>upgrade_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetautomaticosupgradepolicy">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">boot_<wbr>diagnostics</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetbootdiagnostics">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `boot_diagnostics` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">computer_<wbr>name_<wbr>prefix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The prefix which should be used for the name of the Virtual Machines in this Scale Set. If unspecified this defaults to the value for the `name` field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom_<wbr>data</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Base64-Encoded Custom Data which should be used for this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">data_<wbr>disks</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetdatadisk">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disable_<wbr>password_<wbr>authentication</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Password Authentication be disabled on this Virtual Machine Scale Set? Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">do_<wbr>not_<wbr>run_<wbr>extensions_<wbr>on_<wbr>overprovisioned_<wbr>machines</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Virtual Machine Extensions be run on Overprovisioned Virtual Machines in the Scale Set? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">eviction_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Policy which should be used Virtual Machines are Evicted from the Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">health_<wbr>probe_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of a Load Balancer Probe which should be used to determine the health of an instance. Changing this forces a new resource to be created. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetidentity">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instances</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of Virtual Machines in the Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Azure location where the Linux Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max_<wbr>bid_<wbr>price</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in this Scale Set should not be evicted for price reasons.
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>interfaces</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterface">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">os_<wbr>disk</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdisk">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An `os_disk` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">overprovision</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should Azure over-provision Virtual Machines in this Scale Set? This means that multiple Virtual Machines will be provisioned and Azure will keep the instances which become available first - which improves provisioning success rates and improves deployment time. You&#39;re not billed for these over-provisioned VM&#39;s and they don&#39;t count towards the Subscription Quota. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">plan</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetplan">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Priority of this Virtual Machine Scale Set. Possible values are `Regular` and `Spot`. Defaults to `Regular`. Changing this value forces a new resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">provision_<wbr>vm_<wbr>agent</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Azure VM Agent be provisioned on each Virtual Machine in the Scale Set? Defaults to `true`. Changing this value forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proximity_<wbr>placement_<wbr>group_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Proximity Placement Group in which the Virtual Machine Scale Set should be assigned to. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>group_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Resource Group in which the Linux Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rolling_<wbr>upgrade_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetrollingupgradepolicy">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `rolling_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic` or `Rolling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale_<wbr>in_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The scale-in policy rule that decides which virtual machines are chosen for removal when a Virtual Machine Scale Set is scaled in. Possible values for the scale-in policy rules are `Default`, `NewestVM` and `OldestVM`, defaults to `Default`. For more information about scale in policy, please [refer to this doc](https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-scale-in-policy).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secrets</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecret">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `secret` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">single_<wbr>placement_<wbr>group</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should this Virtual Machine Scale Set be limited to a Single Placement Group, which means the number of instances will be capped at 100 Virtual Machines. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sku</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>image_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of an Image which each Virtual Machine in this Scale Set should be based on.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>image_<wbr>reference</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsourceimagereference">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `source_image_reference` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags which should be assigned to this Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">terminate_<wbr>notification</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetterminatenotification">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unique_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Unique ID for this Linux Virtual Machine Scale Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upgrade_<wbr>mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how Upgrades (e.g. changing the Image/SKU) should be performed to Virtual Machine Instances. Possible values are `Automatic`, `Manual` and `Rolling`. Defaults to `Manual`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone_<wbr>balance</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Should the Virtual Machines in this Scale Set be strictly evenly distributed across Availability Zones? Defaults to `false`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zones</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Availability Zones in which the Virtual Machines in this Scale Set should be created in. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### LinuxVirtualMachineScaleSetAdditionalCapabilities
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetAdditionalCapabilities">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetAdditionalCapabilities">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetAdditionalCapabilitiesArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetAdditionalCapabilitiesOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetAdditionalCapabilitiesArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetAdditionalCapabilities.html">output</a> API doc for this type.
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
            <td class="align-top">Ultra<wbr>Ssd<wbr>Enabled</td>
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
            <td class="align-top">Ultra<wbr>Ssd<wbr>Enabled</td>
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
            <td class="align-top">ultra<wbr>Ssd<wbr>Enabled</td>
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
            <td class="align-top">ultra<wbr>Ssd<wbr>Enabled</td>
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





#### LinuxVirtualMachineScaleSetAdminSshKey
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetAdminSshKey">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetAdminSshKey">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetAdminSshKeyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetAdminSshKeyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetAdminSshKeyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetAdminSshKey.html">output</a> API doc for this type.
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
            <td class="align-top">Public<wbr>Key</td>
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
            <td class="align-top">Public<wbr>Key</td>
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
            <td class="align-top">public<wbr>Key</td>
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
            <td class="align-top">public<wbr>Key</td>
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





#### LinuxVirtualMachineScaleSetAutomaticOsUpgradePolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetAutomaticOsUpgradePolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetAutomaticOsUpgradePolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetAutomaticOsUpgradePolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetAutomaticOsUpgradePolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetAutomaticOsUpgradePolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetAutomaticOsUpgradePolicy.html">output</a> API doc for this type.
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
            <td class="align-top">Disable<wbr>Automatic<wbr>Rollback</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Automatic<wbr>Os<wbr>Upgrade</td>
            <td class="align-top">
                
                <code>bool</code>
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
            <td class="align-top">Disable<wbr>Automatic<wbr>Rollback</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Automatic<wbr>Os<wbr>Upgrade</td>
            <td class="align-top">
                
                <code>bool</code>
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
            <td class="align-top">disable<wbr>Automatic<wbr>Rollback</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Automatic<wbr>Os<wbr>Upgrade</td>
            <td class="align-top">
                
                <code>boolean</code>
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
            <td class="align-top">disable<wbr>Automatic<wbr>Rollback</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Automatic<wbr>Os<wbr>Upgrade</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### LinuxVirtualMachineScaleSetBootDiagnostics
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetBootDiagnostics">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetBootDiagnostics">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetBootDiagnosticsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetBootDiagnosticsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetBootDiagnosticsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetBootDiagnostics.html">output</a> API doc for this type.
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
            <td class="align-top">Storage<wbr>Account<wbr>Uri</td>
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
            <td class="align-top">Storage<wbr>Account<wbr>Uri</td>
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
            <td class="align-top">storage<wbr>Account<wbr>Uri</td>
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
            <td class="align-top">storage<wbr>Account<wbr>Uri</td>
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





#### LinuxVirtualMachineScaleSetDataDisk
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetDataDisk">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetDataDisk">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetDataDiskArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetDataDiskOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetDataDiskArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetDataDisk.html">output</a> API doc for this type.
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
            <td class="align-top">Caching</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Lun</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Account<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Write<wbr>Accelerator<wbr>Enabled</td>
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
            <td class="align-top">Caching</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Lun</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Account<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Write<wbr>Accelerator<wbr>Enabled</td>
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
            <td class="align-top">caching</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Encryption<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">lun</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Account<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">write<wbr>Accelerator<wbr>Enabled</td>
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
            <td class="align-top">caching</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk_<wbr>encryption_<wbr>set_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk_<wbr>size_<wbr>gb</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">lun</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage_<wbr>account_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">write_<wbr>accelerator_<wbr>enabled</td>
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





#### LinuxVirtualMachineScaleSetIdentity
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetIdentity">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetIdentity">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetIdentityArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetIdentityOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetIdentityArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetIdentity.html">output</a> API doc for this type.
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
            <td class="align-top">Identity<wbr>Ids</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Principal<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the System Managed Service Principal.
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
            <td class="align-top">Identity<wbr>Ids</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Principal<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the System Managed Service Principal.
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
            <td class="align-top">identity<wbr>Ids</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">principal<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the System Managed Service Principal.
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
            <td class="align-top">identity<wbr>Ids</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">principal_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the System Managed Service Principal.
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





#### LinuxVirtualMachineScaleSetNetworkInterface
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetNetworkInterface">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetNetworkInterface">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetNetworkInterfaceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetNetworkInterfaceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetNetworkInterfaceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetNetworkInterface.html">output</a> API doc for this type.
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
            <td class="align-top">Dns<wbr>Servers</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Accelerated<wbr>Networking</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Ip<wbr>Forwarding</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterfaceipconfiguration">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Security<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Primary</td>
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
            <td class="align-top">Dns<wbr>Servers</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Accelerated<wbr>Networking</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Ip<wbr>Forwarding</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterfaceipconfiguration">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Security<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Primary</td>
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
            <td class="align-top">dns<wbr>Servers</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Accelerated<wbr>Networking</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Ip<wbr>Forwarding</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterfaceipconfiguration">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Security<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">primary</td>
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
            <td class="align-top">dns_<wbr>servers</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>accelerated_<wbr>networking</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>ip_<wbr>forwarding</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>configurations</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterfaceipconfiguration">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>security_<wbr>group_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">primary</td>
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





#### LinuxVirtualMachineScaleSetNetworkInterfaceIpConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetNetworkInterfaceIpConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetNetworkInterfaceIpConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetNetworkInterfaceIpConfiguration.html">output</a> API doc for this type.
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
            <td class="align-top">Application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool<wbr>Ids</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Application<wbr>Security<wbr>Group<wbr>Ids</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancer<wbr>Backend<wbr>Address<wbr>Pool<wbr>Ids</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancer<wbr>Inbound<wbr>Nat<wbr>Rules<wbr>Ids</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Primary</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Ip<wbr>Addresses</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddress">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnet<wbr>Id</td>
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
            <td class="align-top">Application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool<wbr>Ids</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Application<wbr>Security<wbr>Group<wbr>Ids</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancer<wbr>Backend<wbr>Address<wbr>Pool<wbr>Ids</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancer<wbr>Inbound<wbr>Nat<wbr>Rules<wbr>Ids</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Primary</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Ip<wbr>Addresses</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddress">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnet<wbr>Id</td>
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
            <td class="align-top">application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool<wbr>Ids</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">application<wbr>Security<wbr>Group<wbr>Ids</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load<wbr>Balancer<wbr>Backend<wbr>Address<wbr>Pool<wbr>Ids</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load<wbr>Balancer<wbr>Inbound<wbr>Nat<wbr>Rules<wbr>Ids</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">primary</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public<wbr>Ip<wbr>Addresses</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddress">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnet<wbr>Id</td>
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
            <td class="align-top">application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool<wbr>Ids</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">application<wbr>Security<wbr>Group<wbr>Ids</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load<wbr>Balancer<wbr>Backend<wbr>Address<wbr>Pool<wbr>Ids</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load<wbr>Balancer<wbr>Inbound<wbr>Nat<wbr>Rules<wbr>Ids</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">primary</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public_<wbr>ip_<wbr>addresses</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddress">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnet_<wbr>id</td>
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





#### LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddress
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddress">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddress">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddress.html">output</a> API doc for this type.
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
            <td class="align-top">Domain<wbr>Name<wbr>Label</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Idle<wbr>Timeout<wbr>In<wbr>Minutes</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Tags</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddressiptag">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address<wbr>Ip<wbr>Tag<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Ip<wbr>Prefix<wbr>Id</td>
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
            <td class="align-top">Domain<wbr>Name<wbr>Label</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Idle<wbr>Timeout<wbr>In<wbr>Minutes</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Tags</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddressiptag">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address<wbr>Ip<wbr>Tag</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Ip<wbr>Prefix<wbr>Id</td>
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
            <td class="align-top">domain<wbr>Name<wbr>Label</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">idle<wbr>Timeout<wbr>In<wbr>Minutes</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Tags</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddressiptag">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address<wbr>Ip<wbr>Tag[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public<wbr>Ip<wbr>Prefix<wbr>Id</td>
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
            <td class="align-top">domain_<wbr>name_<wbr>label</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">idle_<wbr>timeout_<wbr>in_<wbr>minutes</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Tags</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddressiptag">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address<wbr>Ip<wbr>Tag]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public_<wbr>ip_<wbr>prefix_<wbr>id</td>
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





#### LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressIpTag
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressIpTag">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressIpTag">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressIpTagArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressIpTagOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressIpTagArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressIpTag.html">output</a> API doc for this type.
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
            <td class="align-top">Tag</td>
            <td class="align-top">
                
                <code>string</code>
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
            <td class="align-top">Tag</td>
            <td class="align-top">
                
                <code>string</code>
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
            <td class="align-top">tag</td>
            <td class="align-top">
                
                <code>string</code>
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
            <td class="align-top">tag</td>
            <td class="align-top">
                
                <code>str</code>
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





#### LinuxVirtualMachineScaleSetOsDisk
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetOsDisk">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetOsDisk">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetOsDiskArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetOsDiskOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetOsDiskArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetOsDisk.html">output</a> API doc for this type.
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
            <td class="align-top">Caching</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Diff<wbr>Disk<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdiskdiffdisksettings">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk<wbr>Diff<wbr>Disk<wbr>Settings<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Account<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Write<wbr>Accelerator<wbr>Enabled</td>
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
            <td class="align-top">Caching</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Diff<wbr>Disk<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdiskdiffdisksettings">*Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk<wbr>Diff<wbr>Disk<wbr>Settings</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Account<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Write<wbr>Accelerator<wbr>Enabled</td>
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
            <td class="align-top">caching</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">diff<wbr>Disk<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdiskdiffdisksettings">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk<wbr>Diff<wbr>Disk<wbr>Settings?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Encryption<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Account<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">write<wbr>Accelerator<wbr>Enabled</td>
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
            <td class="align-top">caching</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">diff<wbr>Disk<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetosdiskdiffdisksettings">Dict[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk<wbr>Diff<wbr>Disk<wbr>Settings]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk_<wbr>encryption_<wbr>set_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk_<wbr>size_<wbr>gb</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage_<wbr>account_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">write_<wbr>accelerator_<wbr>enabled</td>
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





#### LinuxVirtualMachineScaleSetOsDiskDiffDiskSettings
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetOsDiskDiffDiskSettings">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetOsDiskDiffDiskSettings">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetOsDiskDiffDiskSettingsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetOsDiskDiffDiskSettingsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetOsDiskDiffDiskSettingsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetOsDiskDiffDiskSettings.html">output</a> API doc for this type.
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
            <td class="align-top">Option</td>
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
            <td class="align-top">Option</td>
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
            <td class="align-top">option</td>
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
            <td class="align-top">option</td>
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





#### LinuxVirtualMachineScaleSetPlan
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetPlan">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetPlan">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetPlanArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetPlanOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetPlanArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetPlan.html">output</a> API doc for this type.
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Product</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Publisher</td>
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Product</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Publisher</td>
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">product</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">publisher</td>
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
The name of the Linux Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">product</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">publisher</td>
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





#### LinuxVirtualMachineScaleSetRollingUpgradePolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetRollingUpgradePolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetRollingUpgradePolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetRollingUpgradePolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetRollingUpgradePolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetRollingUpgradePolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetRollingUpgradePolicy.html">output</a> API doc for this type.
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
            <td class="align-top">Max<wbr>Batch<wbr>Instance<wbr>Percent</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Unhealthy<wbr>Instance<wbr>Percent</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Unhealthy<wbr>Upgraded<wbr>Instance<wbr>Percent</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pause<wbr>Time<wbr>Between<wbr>Batches</td>
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
            <td class="align-top">Max<wbr>Batch<wbr>Instance<wbr>Percent</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Unhealthy<wbr>Instance<wbr>Percent</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Unhealthy<wbr>Upgraded<wbr>Instance<wbr>Percent</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pause<wbr>Time<wbr>Between<wbr>Batches</td>
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
            <td class="align-top">max<wbr>Batch<wbr>Instance<wbr>Percent</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Unhealthy<wbr>Instance<wbr>Percent</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Unhealthy<wbr>Upgraded<wbr>Instance<wbr>Percent</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pause<wbr>Time<wbr>Between<wbr>Batches</td>
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
            <td class="align-top">max<wbr>Batch<wbr>Instance<wbr>Percent</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Unhealthy<wbr>Instance<wbr>Percent</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Unhealthy<wbr>Upgraded<wbr>Instance<wbr>Percent</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pause<wbr>Time<wbr>Between<wbr>Batches</td>
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





#### LinuxVirtualMachineScaleSetSecret
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetSecret">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetSecret">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetSecretArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetSecretOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetSecretArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetSecret.html">output</a> API doc for this type.
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
            <td class="align-top">Certificates</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecretcertificate">List&lt;Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret<wbr>Certificate<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Vault<wbr>Id</td>
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
            <td class="align-top">Certificates</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecretcertificate">[]Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret<wbr>Certificate</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Vault<wbr>Id</td>
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
            <td class="align-top">certificates</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecretcertificate">Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret<wbr>Certificate[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key<wbr>Vault<wbr>Id</td>
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
            <td class="align-top">certificates</td>
            <td class="align-top">
                
                <code><a href="#linuxvirtualmachinescalesetsecretcertificate">List[Linux<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret<wbr>Certificate]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key_<wbr>vault_<wbr>id</td>
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





#### LinuxVirtualMachineScaleSetSecretCertificate
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetSecretCertificate">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetSecretCertificate">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetSecretCertificateArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetSecretCertificateOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetSecretCertificateArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetSecretCertificate.html">output</a> API doc for this type.
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
            <td class="align-top">Url</td>
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
            <td class="align-top">Url</td>
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
            <td class="align-top">url</td>
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
            <td class="align-top">url</td>
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





#### LinuxVirtualMachineScaleSetSourceImageReference
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetSourceImageReference">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetSourceImageReference">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetSourceImageReferenceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetSourceImageReferenceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetSourceImageReferenceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetSourceImageReference.html">output</a> API doc for this type.
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
            <td class="align-top">Offer</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Publisher</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sku</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version</td>
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
            <td class="align-top">Offer</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Publisher</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sku</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version</td>
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
            <td class="align-top">offer</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">publisher</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sku</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version</td>
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
            <td class="align-top">offer</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">publisher</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sku</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Virtual Machine SKU for the Scale Set, such as `Standard_F2`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version</td>
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





#### LinuxVirtualMachineScaleSetTerminateNotification
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#LinuxVirtualMachineScaleSetTerminateNotification">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#LinuxVirtualMachineScaleSetTerminateNotification">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetTerminateNotificationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#LinuxVirtualMachineScaleSetTerminateNotificationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetTerminateNotificationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.LinuxVirtualMachineScaleSetTerminateNotification.html">output</a> API doc for this type.
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
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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








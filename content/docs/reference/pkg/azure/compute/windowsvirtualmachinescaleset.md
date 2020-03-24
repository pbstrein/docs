
---
title: "WindowsVirtualMachineScaleSet"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Manages a Windows Virtual Machine Scale Set.

## Disclaimers

> **Note** This provider will automatically update & reimage the nodes in the Scale Set (if Required) during an Update - this behaviour can be configured using the `features` configuration within the Provider configuration block.

> **Note:** This resource does not support Unmanaged Disks. If you need to use Unmanaged Disks you can continue to use the `azure.compute.ScaleSet` resource instead

> This content is derived from https://github.com/terraform-providers/terraform-provider-azurerm/blob/master/website/docs/r/windows_virtual_machine_scale_set.html.markdown.



## Create a WindowsVirtualMachineScaleSet Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/compute/#WindowsVirtualMachineScaleSet">WindowsVirtualMachineScaleSet</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/compute/#WindowsVirtualMachineScaleSetArgs">WindowsVirtualMachineScaleSetArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">WindowsVirtualMachineScaleSet</span><span class="p">(resource_name, opts=None, </span>additional_capabilities=None<span class="p">, </span>additional_unattend_contents=None<span class="p">, </span>admin_password=None<span class="p">, </span>admin_username=None<span class="p">, </span>automatic_os_upgrade_policy=None<span class="p">, </span>boot_diagnostics=None<span class="p">, </span>computer_name_prefix=None<span class="p">, </span>custom_data=None<span class="p">, </span>data_disks=None<span class="p">, </span>do_not_run_extensions_on_overprovisioned_machines=None<span class="p">, </span>enable_automatic_updates=None<span class="p">, </span>eviction_policy=None<span class="p">, </span>health_probe_id=None<span class="p">, </span>identity=None<span class="p">, </span>instances=None<span class="p">, </span>license_type=None<span class="p">, </span>location=None<span class="p">, </span>max_bid_price=None<span class="p">, </span>name=None<span class="p">, </span>network_interfaces=None<span class="p">, </span>os_disk=None<span class="p">, </span>overprovision=None<span class="p">, </span>plan=None<span class="p">, </span>priority=None<span class="p">, </span>provision_vm_agent=None<span class="p">, </span>proximity_placement_group_id=None<span class="p">, </span>resource_group_name=None<span class="p">, </span>rolling_upgrade_policy=None<span class="p">, </span>scale_in_policy=None<span class="p">, </span>secrets=None<span class="p">, </span>single_placement_group=None<span class="p">, </span>sku=None<span class="p">, </span>source_image_id=None<span class="p">, </span>source_image_reference=None<span class="p">, </span>tags=None<span class="p">, </span>terminate_notification=None<span class="p">, </span>timezone=None<span class="p">, </span>upgrade_mode=None<span class="p">, </span>winrm_listeners=None<span class="p">, </span>zone_balance=None<span class="p">, </span>zones=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewWindowsVirtualMachineScaleSet<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetArgs">WindowsVirtualMachineScaleSetArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSet">WindowsVirtualMachineScaleSet</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSet.html">WindowsVirtualMachineScaleSet</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetArgs.html">WindowsVirtualMachineScaleSetArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a WindowsVirtualMachineScaleSet resource with the given unique name, arguments, and options.

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
                
                <code><a href="#windowsvirtualmachinescalesetadditionalcapabilities">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Additional<wbr>Unattend<wbr>Contents</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetadditionalunattendcontent">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Unattend<wbr>Content<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `additional_unattend_content` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetautomaticosupgradepolicy">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy<wbr>Args?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetbootdiagnostics">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics<wbr>Args?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetdatadisk">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
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
            <td class="align-top">Enable<wbr>Automatic<wbr>Updates</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Are automatic updates enabled for this Virtual Machine? Defaults to `true`.
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
                
                <code><a href="#windowsvirtualmachinescalesetidentity">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity<wbr>Args?</a></code>
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
            <td class="align-top">License<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of on-premise license (also known as [Azure Hybrid Use Benefit](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-hybrid-use-benefit-licensing)) which should be used for this Virtual Machine Scale Set. Possible values are `None`, `Windows_Client` and `Windows_Server`. Changing this forces a new resource to be created.
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
The Azure location where the Windows Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
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
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in the Scale Set should not be evicted for price reasons.
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterface">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Args&gt;</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetosdisk">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk<wbr>Args</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetplan">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan<wbr>Args?</a></code>
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
The name of the Resource Group in which the Windows Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetrollingupgradepolicy">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy<wbr>Args?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsecret">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret<wbr>Args&gt;?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsourceimagereference">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference<wbr>Args?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetterminatenotification">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timezone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone of the virtual machine, [the possible values are defined here](https://jackstromberg.com/2017/01/list-of-time-zones-consumed-by-azure/).
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
            <td class="align-top">Winrm<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetwinrmlistener">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Winrm<wbr>Listener<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `winrm_listener` blocks as defined below.
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
                
                <code><a href="#windowsvirtualmachinescalesetadditionalcapabilities">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Additional<wbr>Unattend<wbr>Contents</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetadditionalunattendcontent">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Unattend<wbr>Content</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `additional_unattend_content` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetautomaticosupgradepolicy">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetbootdiagnostics">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetdatadisk">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
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
            <td class="align-top">Enable<wbr>Automatic<wbr>Updates</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Are automatic updates enabled for this Virtual Machine? Defaults to `true`.
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
                
                <code><a href="#windowsvirtualmachinescalesetidentity">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity</a></code>
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
            <td class="align-top">License<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of on-premise license (also known as [Azure Hybrid Use Benefit](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-hybrid-use-benefit-licensing)) which should be used for this Virtual Machine Scale Set. Possible values are `None`, `Windows_Client` and `Windows_Server`. Changing this forces a new resource to be created.
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
The Azure location where the Windows Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
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
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in the Scale Set should not be evicted for price reasons.
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterface">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetosdisk">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetplan">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan</a></code>
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
The name of the Resource Group in which the Windows Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetrollingupgradepolicy">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsecret">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsourceimagereference">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetterminatenotification">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timezone</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone of the virtual machine, [the possible values are defined here](https://jackstromberg.com/2017/01/list-of-time-zones-consumed-by-azure/).
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
            <td class="align-top">Winrm<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetwinrmlistener">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Winrm<wbr>Listener</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `winrm_listener` blocks as defined below.
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
                
                <code><a href="#windowsvirtualmachinescalesetadditionalcapabilities">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">additional<wbr>Unattend<wbr>Contents</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetadditionalunattendcontent">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Unattend<wbr>Content[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `additional_unattend_content` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetautomaticosupgradepolicy">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetbootdiagnostics">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetdatadisk">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
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
            <td class="align-top">enable<wbr>Automatic<wbr>Updates</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Are automatic updates enabled for this Virtual Machine? Defaults to `true`.
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
                
                <code><a href="#windowsvirtualmachinescalesetidentity">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity?</a></code>
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
            <td class="align-top">license<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of on-premise license (also known as [Azure Hybrid Use Benefit](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-hybrid-use-benefit-licensing)) which should be used for this Virtual Machine Scale Set. Possible values are `None`, `Windows_Client` and `Windows_Server`. Changing this forces a new resource to be created.
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
The Azure location where the Windows Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
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
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in the Scale Set should not be evicted for price reasons.
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterface">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface[]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetosdisk">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetplan">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan?</a></code>
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
The name of the Resource Group in which the Windows Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetrollingupgradepolicy">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsecret">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret[]?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsourceimagereference">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetterminatenotification">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timezone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone of the virtual machine, [the possible values are defined here](https://jackstromberg.com/2017/01/list-of-time-zones-consumed-by-azure/).
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
            <td class="align-top">winrm<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetwinrmlistener">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Winrm<wbr>Listener[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `winrm_listener` blocks as defined below.
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
                
                <code><a href="#windowsvirtualmachinescalesetadditionalcapabilities">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">additional_<wbr>unattend_<wbr>contents</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetadditionalunattendcontent">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Unattend<wbr>Content]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `additional_unattend_content` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin_<wbr>password</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetautomaticosupgradepolicy">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetbootdiagnostics">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetdatadisk">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
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
            <td class="align-top">enable_<wbr>automatic_<wbr>updates</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Are automatic updates enabled for this Virtual Machine? Defaults to `true`.
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
                
                <code><a href="#windowsvirtualmachinescalesetidentity">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity]</a></code>
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
            <td class="align-top">license_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of on-premise license (also known as [Azure Hybrid Use Benefit](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-hybrid-use-benefit-licensing)) which should be used for this Virtual Machine Scale Set. Possible values are `None`, `Windows_Client` and `Windows_Server`. Changing this forces a new resource to be created.
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
The Azure location where the Windows Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
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
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in the Scale Set should not be evicted for price reasons.
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>interfaces</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterface">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetosdisk">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetplan">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan]</a></code>
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
The name of the Resource Group in which the Windows Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rolling_<wbr>upgrade_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetrollingupgradepolicy">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsecret">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsourceimagereference">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetterminatenotification">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timezone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone of the virtual machine, [the possible values are defined here](https://jackstromberg.com/2017/01/list-of-time-zones-consumed-by-azure/).
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
            <td class="align-top">winrm_<wbr>listeners</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetwinrmlistener">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Winrm<wbr>Listener]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `winrm_listener` blocks as defined below.
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







## WindowsVirtualMachineScaleSet Output Properties

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
                
                <code><a href="#windowsvirtualmachinescalesetadditionalcapabilities">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Additional<wbr>Unattend<wbr>Contents</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetadditionalunattendcontent">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Unattend<wbr>Content&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `additional_unattend_content` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetautomaticosupgradepolicy">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Boot<wbr>Diagnostics</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetbootdiagnostics">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetdatadisk">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `data_disk` blocks as defined below.
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
            <td class="align-top">Enable<wbr>Automatic<wbr>Updates</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Are automatic updates enabled for this Virtual Machine? Defaults to `true`.
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
                
                <code><a href="#windowsvirtualmachinescalesetidentity">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity?</a></code>
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
            <td class="align-top">License<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the type of on-premise license (also known as [Azure Hybrid Use Benefit](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-hybrid-use-benefit-licensing)) which should be used for this Virtual Machine Scale Set. Possible values are `None`, `Windows_Client` and `Windows_Server`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Azure location where the Windows Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Bid<wbr>Price</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in the Scale Set should not be evicted for price reasons.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterface">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Os<wbr>Disk</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetosdisk">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetplan">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan?</a></code>
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
            <td class="align-top">{{% md %}} The name of the Resource Group in which the Windows Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetrollingupgradepolicy">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsecret">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret&gt;?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsourceimagereference">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetterminatenotification">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification</a></code>
            </td>
            <td class="align-top">{{% md %}} A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timezone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the time zone of the virtual machine, [the possible values are defined here](https://jackstromberg.com/2017/01/list-of-time-zones-consumed-by-azure/).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unique<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Unique ID for this Windows Virtual Machine Scale Set.
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
            <td class="align-top">Winrm<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetwinrmlistener">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Winrm<wbr>Listener&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `winrm_listener` blocks as defined below.
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
                
                <code><a href="#windowsvirtualmachinescalesetadditionalcapabilities">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities</a></code>
            </td>
            <td class="align-top">{{% md %}} A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Additional<wbr>Unattend<wbr>Contents</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetadditionalunattendcontent">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Unattend<wbr>Content</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `additional_unattend_content` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetautomaticosupgradepolicy">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Boot<wbr>Diagnostics</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetbootdiagnostics">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetdatadisk">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `data_disk` blocks as defined below.
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
            <td class="align-top">Enable<wbr>Automatic<wbr>Updates</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Are automatic updates enabled for this Virtual Machine? Defaults to `true`.
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
                
                <code><a href="#windowsvirtualmachinescalesetidentity">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity</a></code>
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
            <td class="align-top">License<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the type of on-premise license (also known as [Azure Hybrid Use Benefit](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-hybrid-use-benefit-licensing)) which should be used for this Virtual Machine Scale Set. Possible values are `None`, `Windows_Client` and `Windows_Server`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Azure location where the Windows Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Bid<wbr>Price</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in the Scale Set should not be evicted for price reasons.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterface">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Os<wbr>Disk</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetosdisk">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetplan">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan</a></code>
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
            <td class="align-top">{{% md %}} The name of the Resource Group in which the Windows Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetrollingupgradepolicy">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsecret">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsourceimagereference">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetterminatenotification">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification</a></code>
            </td>
            <td class="align-top">{{% md %}} A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timezone</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the time zone of the virtual machine, [the possible values are defined here](https://jackstromberg.com/2017/01/list-of-time-zones-consumed-by-azure/).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unique<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Unique ID for this Windows Virtual Machine Scale Set.
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
            <td class="align-top">Winrm<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetwinrmlistener">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Winrm<wbr>Listener</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `winrm_listener` blocks as defined below.
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
                
                <code><a href="#windowsvirtualmachinescalesetadditionalcapabilities">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">additional<wbr>Unattend<wbr>Contents</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetadditionalunattendcontent">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Unattend<wbr>Content[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `additional_unattend_content` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Password which should be used for the local-administrator on this Virtual Machine. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetautomaticosupgradepolicy">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">boot<wbr>Diagnostics</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetbootdiagnostics">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetdatadisk">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `data_disk` blocks as defined below.
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
            <td class="align-top">enable<wbr>Automatic<wbr>Updates</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Are automatic updates enabled for this Virtual Machine? Defaults to `true`.
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
                
                <code><a href="#windowsvirtualmachinescalesetidentity">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity?</a></code>
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
            <td class="align-top">license<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the type of on-premise license (also known as [Azure Hybrid Use Benefit](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-hybrid-use-benefit-licensing)) which should be used for this Virtual Machine Scale Set. Possible values are `None`, `Windows_Client` and `Windows_Server`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Azure location where the Windows Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Bid<wbr>Price</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in the Scale Set should not be evicted for price reasons.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterface">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface[]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">os<wbr>Disk</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetosdisk">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetplan">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan?</a></code>
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
            <td class="align-top">{{% md %}} The name of the Resource Group in which the Windows Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetrollingupgradepolicy">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsecret">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret[]?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsourceimagereference">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetterminatenotification">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification</a></code>
            </td>
            <td class="align-top">{{% md %}} A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timezone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the time zone of the virtual machine, [the possible values are defined here](https://jackstromberg.com/2017/01/list-of-time-zones-consumed-by-azure/).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unique<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Unique ID for this Windows Virtual Machine Scale Set.
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
            <td class="align-top">winrm<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetwinrmlistener">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Winrm<wbr>Listener[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `winrm_listener` blocks as defined below.
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
                
                <code><a href="#windowsvirtualmachinescalesetadditionalcapabilities">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">additional_<wbr>unattend_<wbr>contents</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetadditionalunattendcontent">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Unattend<wbr>Content]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `additional_unattend_content` blocks as defined below.
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
                
                <code><a href="#windowsvirtualmachinescalesetautomaticosupgradepolicy">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `automatic_os_upgrade_policy` block as defined below. This is Required and can only be specified when `upgrade_mode` is set to `Automatic`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">boot_<wbr>diagnostics</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetbootdiagnostics">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetdatadisk">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `data_disk` blocks as defined below.
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
            <td class="align-top">enable_<wbr>automatic_<wbr>updates</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Are automatic updates enabled for this Virtual Machine? Defaults to `true`.
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
                
                <code><a href="#windowsvirtualmachinescalesetidentity">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity]</a></code>
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
            <td class="align-top">license_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the type of on-premise license (also known as [Azure Hybrid Use Benefit](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-hybrid-use-benefit-licensing)) which should be used for this Virtual Machine Scale Set. Possible values are `None`, `Windows_Client` and `Windows_Server`. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Azure location where the Windows Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max_<wbr>bid_<wbr>price</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in the Scale Set should not be evicted for price reasons.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>interfaces</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterface">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `network_interface` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">os_<wbr>disk</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetosdisk">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetplan">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan]</a></code>
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
            <td class="align-top">{{% md %}} The name of the Resource Group in which the Windows Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rolling_<wbr>upgrade_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetrollingupgradepolicy">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsecret">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsourceimagereference">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetterminatenotification">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timezone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the time zone of the virtual machine, [the possible values are defined here](https://jackstromberg.com/2017/01/list-of-time-zones-consumed-by-azure/).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unique_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Unique ID for this Windows Virtual Machine Scale Set.
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
            <td class="align-top">winrm_<wbr>listeners</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetwinrmlistener">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Winrm<wbr>Listener]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `winrm_listener` blocks as defined below.
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








## Look up an Existing WindowsVirtualMachineScaleSet Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/compute/#WindowsVirtualMachineScaleSetState">WindowsVirtualMachineScaleSetState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/compute/#WindowsVirtualMachineScaleSet">WindowsVirtualMachineScaleSet</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>additional_capabilities=None<span class="p">, </span>additional_unattend_contents=None<span class="p">, </span>admin_password=None<span class="p">, </span>admin_username=None<span class="p">, </span>automatic_os_upgrade_policy=None<span class="p">, </span>boot_diagnostics=None<span class="p">, </span>computer_name_prefix=None<span class="p">, </span>custom_data=None<span class="p">, </span>data_disks=None<span class="p">, </span>do_not_run_extensions_on_overprovisioned_machines=None<span class="p">, </span>enable_automatic_updates=None<span class="p">, </span>eviction_policy=None<span class="p">, </span>health_probe_id=None<span class="p">, </span>identity=None<span class="p">, </span>instances=None<span class="p">, </span>license_type=None<span class="p">, </span>location=None<span class="p">, </span>max_bid_price=None<span class="p">, </span>name=None<span class="p">, </span>network_interfaces=None<span class="p">, </span>os_disk=None<span class="p">, </span>overprovision=None<span class="p">, </span>plan=None<span class="p">, </span>priority=None<span class="p">, </span>provision_vm_agent=None<span class="p">, </span>proximity_placement_group_id=None<span class="p">, </span>resource_group_name=None<span class="p">, </span>rolling_upgrade_policy=None<span class="p">, </span>scale_in_policy=None<span class="p">, </span>secrets=None<span class="p">, </span>single_placement_group=None<span class="p">, </span>sku=None<span class="p">, </span>source_image_id=None<span class="p">, </span>source_image_reference=None<span class="p">, </span>tags=None<span class="p">, </span>terminate_notification=None<span class="p">, </span>timezone=None<span class="p">, </span>unique_id=None<span class="p">, </span>upgrade_mode=None<span class="p">, </span>winrm_listeners=None<span class="p">, </span>zone_balance=None<span class="p">, </span>zones=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetWindowsVirtualMachineScaleSet<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetState">WindowsVirtualMachineScaleSetState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSet">WindowsVirtualMachineScaleSet</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSet.html">WindowsVirtualMachineScaleSet</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetState.html">WindowsVirtualMachineScaleSetState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing WindowsVirtualMachineScaleSet resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
                
                <code><a href="#windowsvirtualmachinescalesetadditionalcapabilities">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Additional<wbr>Unattend<wbr>Contents</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetadditionalunattendcontent">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Unattend<wbr>Content<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `additional_unattend_content` blocks as defined below.
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
                
                <code><a href="#windowsvirtualmachinescalesetautomaticosupgradepolicy">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy<wbr>Args?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetbootdiagnostics">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics<wbr>Args?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetdatadisk">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
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
            <td class="align-top">Enable<wbr>Automatic<wbr>Updates</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Are automatic updates enabled for this Virtual Machine? Defaults to `true`.
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
                
                <code><a href="#windowsvirtualmachinescalesetidentity">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity<wbr>Args?</a></code>
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
            <td class="align-top">License<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of on-premise license (also known as [Azure Hybrid Use Benefit](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-hybrid-use-benefit-licensing)) which should be used for this Virtual Machine Scale Set. Possible values are `None`, `Windows_Client` and `Windows_Server`. Changing this forces a new resource to be created.
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
The Azure location where the Windows Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
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
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in the Scale Set should not be evicted for price reasons.
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterface">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Args&gt;?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetosdisk">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk<wbr>Args?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetplan">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan<wbr>Args?</a></code>
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
The name of the Resource Group in which the Windows Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetrollingupgradepolicy">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy<wbr>Args?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsecret">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret<wbr>Args&gt;?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsourceimagereference">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference<wbr>Args?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetterminatenotification">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timezone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone of the virtual machine, [the possible values are defined here](https://jackstromberg.com/2017/01/list-of-time-zones-consumed-by-azure/).
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
The Unique ID for this Windows Virtual Machine Scale Set.
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
            <td class="align-top">Winrm<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetwinrmlistener">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Winrm<wbr>Listener<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `winrm_listener` blocks as defined below.
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
                
                <code><a href="#windowsvirtualmachinescalesetadditionalcapabilities">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Additional<wbr>Unattend<wbr>Contents</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetadditionalunattendcontent">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Unattend<wbr>Content</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `additional_unattend_content` blocks as defined below.
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
                
                <code><a href="#windowsvirtualmachinescalesetautomaticosupgradepolicy">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetbootdiagnostics">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetdatadisk">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
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
            <td class="align-top">Enable<wbr>Automatic<wbr>Updates</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Are automatic updates enabled for this Virtual Machine? Defaults to `true`.
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
                
                <code><a href="#windowsvirtualmachinescalesetidentity">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity</a></code>
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
            <td class="align-top">License<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of on-premise license (also known as [Azure Hybrid Use Benefit](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-hybrid-use-benefit-licensing)) which should be used for this Virtual Machine Scale Set. Possible values are `None`, `Windows_Client` and `Windows_Server`. Changing this forces a new resource to be created.
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
The Azure location where the Windows Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
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
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in the Scale Set should not be evicted for price reasons.
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterface">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetosdisk">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetplan">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan</a></code>
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
The name of the Resource Group in which the Windows Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetrollingupgradepolicy">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsecret">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsourceimagereference">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetterminatenotification">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timezone</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone of the virtual machine, [the possible values are defined here](https://jackstromberg.com/2017/01/list-of-time-zones-consumed-by-azure/).
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
The Unique ID for this Windows Virtual Machine Scale Set.
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
            <td class="align-top">Winrm<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetwinrmlistener">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Winrm<wbr>Listener</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `winrm_listener` blocks as defined below.
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
                
                <code><a href="#windowsvirtualmachinescalesetadditionalcapabilities">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">additional<wbr>Unattend<wbr>Contents</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetadditionalunattendcontent">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Unattend<wbr>Content[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `additional_unattend_content` blocks as defined below.
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
                
                <code><a href="#windowsvirtualmachinescalesetautomaticosupgradepolicy">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetbootdiagnostics">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetdatadisk">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
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
            <td class="align-top">enable<wbr>Automatic<wbr>Updates</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Are automatic updates enabled for this Virtual Machine? Defaults to `true`.
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
                
                <code><a href="#windowsvirtualmachinescalesetidentity">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity?</a></code>
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
            <td class="align-top">license<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of on-premise license (also known as [Azure Hybrid Use Benefit](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-hybrid-use-benefit-licensing)) which should be used for this Virtual Machine Scale Set. Possible values are `None`, `Windows_Client` and `Windows_Server`. Changing this forces a new resource to be created.
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
The Azure location where the Windows Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
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
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in the Scale Set should not be evicted for price reasons.
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterface">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface[]?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetosdisk">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetplan">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan?</a></code>
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
The name of the Resource Group in which the Windows Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rolling<wbr>Upgrade<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetrollingupgradepolicy">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsecret">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret[]?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsourceimagereference">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetterminatenotification">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timezone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone of the virtual machine, [the possible values are defined here](https://jackstromberg.com/2017/01/list-of-time-zones-consumed-by-azure/).
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
The Unique ID for this Windows Virtual Machine Scale Set.
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
            <td class="align-top">winrm<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetwinrmlistener">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Winrm<wbr>Listener[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `winrm_listener` blocks as defined below.
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
                
                <code><a href="#windowsvirtualmachinescalesetadditionalcapabilities">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Capabilities]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `additional_capabilities` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">additional_<wbr>unattend_<wbr>contents</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetadditionalunattendcontent">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Additional<wbr>Unattend<wbr>Content]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `additional_unattend_content` blocks as defined below.
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
                
                <code><a href="#windowsvirtualmachinescalesetautomaticosupgradepolicy">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Automatic<wbr>Os<wbr>Upgrade<wbr>Policy]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetbootdiagnostics">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Boot<wbr>Diagnostics]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetdatadisk">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Data<wbr>Disk]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `data_disk` blocks as defined below.
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
            <td class="align-top">enable_<wbr>automatic_<wbr>updates</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Are automatic updates enabled for this Virtual Machine? Defaults to `true`.
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
                
                <code><a href="#windowsvirtualmachinescalesetidentity">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Identity]</a></code>
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
            <td class="align-top">license_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the type of on-premise license (also known as [Azure Hybrid Use Benefit](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-hybrid-use-benefit-licensing)) which should be used for this Virtual Machine Scale Set. Possible values are `None`, `Windows_Client` and `Windows_Server`. Changing this forces a new resource to be created.
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
The Azure location where the Windows Virtual Machine Scale Set should exist. Changing this forces a new resource to be created.
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
The maximum price you&#39;re willing to pay for each Virtual Machine in this Scale Set, in US Dollars; which must be greater than the current spot price. If this bid price falls below the current spot price the Virtual Machines in the Scale Set will be evicted using the `eviction_policy`. Defaults to `-1`, which means that each Virtual Machine in the Scale Set should not be evicted for price reasons.
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>interfaces</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterface">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetosdisk">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetplan">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Plan]</a></code>
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
The name of the Resource Group in which the Windows Virtual Machine Scale Set should be exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rolling_<wbr>upgrade_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetrollingupgradepolicy">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Rolling<wbr>Upgrade<wbr>Policy]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsecret">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsourceimagereference">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Source<wbr>Image<wbr>Reference]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetterminatenotification">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Terminate<wbr>Notification]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `terminate_notification` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timezone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the time zone of the virtual machine, [the possible values are defined here](https://jackstromberg.com/2017/01/list-of-time-zones-consumed-by-azure/).
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
The Unique ID for this Windows Virtual Machine Scale Set.
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
            <td class="align-top">winrm_<wbr>listeners</td>
            <td class="align-top">
                
                <code><a href="#windowsvirtualmachinescalesetwinrmlistener">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Winrm<wbr>Listener]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `winrm_listener` blocks as defined below.
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

#### WindowsVirtualMachineScaleSetAdditionalCapabilities
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetAdditionalCapabilities">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetAdditionalCapabilities">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetAdditionalCapabilitiesArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetAdditionalCapabilitiesOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetAdditionalCapabilitiesArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetAdditionalCapabilities.html">output</a> API doc for this type.
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





#### WindowsVirtualMachineScaleSetAdditionalUnattendContent
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetAdditionalUnattendContent">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetAdditionalUnattendContent">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetAdditionalUnattendContentArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetAdditionalUnattendContentOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetAdditionalUnattendContentArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetAdditionalUnattendContent.html">output</a> API doc for this type.
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
            <td class="align-top">Content</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Setting</td>
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
            <td class="align-top">Content</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Setting</td>
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
            <td class="align-top">content</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">setting</td>
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
            <td class="align-top">content</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">setting</td>
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





#### WindowsVirtualMachineScaleSetAutomaticOsUpgradePolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetAutomaticOsUpgradePolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetAutomaticOsUpgradePolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetAutomaticOsUpgradePolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetAutomaticOsUpgradePolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetAutomaticOsUpgradePolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetAutomaticOsUpgradePolicy.html">output</a> API doc for this type.
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





#### WindowsVirtualMachineScaleSetBootDiagnostics
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetBootDiagnostics">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetBootDiagnostics">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetBootDiagnosticsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetBootDiagnosticsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetBootDiagnosticsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetBootDiagnostics.html">output</a> API doc for this type.
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





#### WindowsVirtualMachineScaleSetDataDisk
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetDataDisk">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetDataDisk">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetDataDiskArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetDataDiskOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetDataDiskArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetDataDisk.html">output</a> API doc for this type.
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





#### WindowsVirtualMachineScaleSetIdentity
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetIdentity">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetIdentity">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetIdentityArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetIdentityOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetIdentityArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetIdentity.html">output</a> API doc for this type.
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





#### WindowsVirtualMachineScaleSetNetworkInterface
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetNetworkInterface">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetNetworkInterface">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetNetworkInterfaceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetNetworkInterfaceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetNetworkInterfaceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetNetworkInterface.html">output</a> API doc for this type.
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
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterfaceipconfiguration">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Args&gt;</a></code>
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterfaceipconfiguration">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration</a></code>
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterfaceipconfiguration">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration[]</a></code>
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterfaceipconfiguration">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration]</a></code>
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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





#### WindowsVirtualMachineScaleSetNetworkInterfaceIpConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetNetworkInterfaceIpConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetNetworkInterfaceIpConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetNetworkInterfaceIpConfiguration.html">output</a> API doc for this type.
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddress">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address<wbr>Args&gt;?</a></code>
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddress">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address</a></code>
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddress">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address[]?</a></code>
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddress">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address]</a></code>
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





#### WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddress
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddress">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddress">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddress.html">output</a> API doc for this type.
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
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddressiptag">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address<wbr>Ip<wbr>Tag<wbr>Args&gt;?</a></code>
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddressiptag">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address<wbr>Ip<wbr>Tag</a></code>
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddressiptag">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address<wbr>Ip<wbr>Tag[]?</a></code>
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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
                
                <code><a href="#windowsvirtualmachinescalesetnetworkinterfaceipconfigurationpublicipaddressiptag">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Network<wbr>Interface<wbr>Ip<wbr>Configuration<wbr>Public<wbr>Ip<wbr>Address<wbr>Ip<wbr>Tag]</a></code>
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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





#### WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressIpTag
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressIpTag">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressIpTag">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressIpTagArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressIpTagOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressIpTagArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetNetworkInterfaceIpConfigurationPublicIpAddressIpTag.html">output</a> API doc for this type.
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





#### WindowsVirtualMachineScaleSetOsDisk
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetOsDisk">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetOsDisk">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetOsDiskArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetOsDiskOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetOsDiskArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetOsDisk.html">output</a> API doc for this type.
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
                
                <code><a href="#windowsvirtualmachinescalesetosdiskdiffdisksettings">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk<wbr>Diff<wbr>Disk<wbr>Settings<wbr>Args?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetosdiskdiffdisksettings">*Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk<wbr>Diff<wbr>Disk<wbr>Settings</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetosdiskdiffdisksettings">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk<wbr>Diff<wbr>Disk<wbr>Settings?</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetosdiskdiffdisksettings">Dict[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Os<wbr>Disk<wbr>Diff<wbr>Disk<wbr>Settings]</a></code>
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





#### WindowsVirtualMachineScaleSetOsDiskDiffDiskSettings
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetOsDiskDiffDiskSettings">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetOsDiskDiffDiskSettings">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetOsDiskDiffDiskSettingsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetOsDiskDiffDiskSettingsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetOsDiskDiffDiskSettingsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetOsDiskDiffDiskSettings.html">output</a> API doc for this type.
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





#### WindowsVirtualMachineScaleSetPlan
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetPlan">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetPlan">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetPlanArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetPlanOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetPlanArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetPlan.html">output</a> API doc for this type.
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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
The name of the Windows Virtual Machine Scale Set. Changing this forces a new resource to be created.
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





#### WindowsVirtualMachineScaleSetRollingUpgradePolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetRollingUpgradePolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetRollingUpgradePolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetRollingUpgradePolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetRollingUpgradePolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetRollingUpgradePolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetRollingUpgradePolicy.html">output</a> API doc for this type.
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





#### WindowsVirtualMachineScaleSetSecret
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetSecret">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetSecret">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetSecretArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetSecretOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetSecretArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetSecret.html">output</a> API doc for this type.
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
                
                <code><a href="#windowsvirtualmachinescalesetsecretcertificate">List&lt;Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret<wbr>Certificate<wbr>Args&gt;</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsecretcertificate">[]Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret<wbr>Certificate</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsecretcertificate">Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret<wbr>Certificate[]</a></code>
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
                
                <code><a href="#windowsvirtualmachinescalesetsecretcertificate">List[Windows<wbr>Virtual<wbr>Machine<wbr>Scale<wbr>Set<wbr>Secret<wbr>Certificate]</a></code>
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





#### WindowsVirtualMachineScaleSetSecretCertificate
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetSecretCertificate">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetSecretCertificate">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetSecretCertificateArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetSecretCertificateOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetSecretCertificateArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetSecretCertificate.html">output</a> API doc for this type.
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
            <td class="align-top">Store</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
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
            <td class="align-top">Store</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
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
            <td class="align-top">store</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
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
            <td class="align-top">store</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
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





#### WindowsVirtualMachineScaleSetSourceImageReference
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetSourceImageReference">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetSourceImageReference">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetSourceImageReferenceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetSourceImageReferenceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetSourceImageReferenceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetSourceImageReference.html">output</a> API doc for this type.
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





#### WindowsVirtualMachineScaleSetTerminateNotification
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetTerminateNotification">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetTerminateNotification">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetTerminateNotificationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetTerminateNotificationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetTerminateNotificationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetTerminateNotification.html">output</a> API doc for this type.
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





#### WindowsVirtualMachineScaleSetWinrmListener
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#WindowsVirtualMachineScaleSetWinrmListener">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#WindowsVirtualMachineScaleSetWinrmListener">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetWinrmListenerArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/compute?tab=doc#WindowsVirtualMachineScaleSetWinrmListenerOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetWinrmListenerArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Compute.WindowsVirtualMachineScaleSetWinrmListener.html">output</a> API doc for this type.
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
            <td class="align-top">Certificate<wbr>Url</td>
            <td class="align-top">
                
                <code>string?</code>
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
            <td class="align-top">Certificate<wbr>Url</td>
            <td class="align-top">
                
                <code>*string</code>
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
            <td class="align-top">certificate<wbr>Url</td>
            <td class="align-top">
                
                <code>string?</code>
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
            <td class="align-top">certificate<wbr>Url</td>
            <td class="align-top">
                
                <code>str</code>
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








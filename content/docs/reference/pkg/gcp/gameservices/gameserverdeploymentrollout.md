
---
title: "GameServerDeploymentRollout"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a GameServerDeploymentRollout Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/gameservices/#GameServerDeploymentRollout">GameServerDeploymentRollout</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/gameservices/#GameServerDeploymentRolloutArgs">GameServerDeploymentRolloutArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">GameServerDeploymentRollout</span><span class="p">(resource_name, opts=None, </span>default_game_server_config=None<span class="p">, </span>deployment_id=None<span class="p">, </span>game_server_config_overrides=None<span class="p">, </span>project=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewGameServerDeploymentRollout<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/gameservices?tab=doc#GameServerDeploymentRolloutArgs">GameServerDeploymentRolloutArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/gameservices?tab=doc#GameServerDeploymentRollout">GameServerDeploymentRollout</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Gameservices.GameServerDeploymentRollout.html">GameServerDeploymentRollout</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Gameservices.GameServerDeploymentRolloutArgs.html">GameServerDeploymentRolloutArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a GameServerDeploymentRollout resource with the given unique name, arguments, and options.

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
            <td class="align-top">Default<wbr>Game<wbr>Server<wbr>Config</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
This field points to the game server config that is applied by default to all realms and clusters. For example,
&#39;projects/my-project/locations/global/gameServerDeployments/my-game/configs/my-config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The deployment to rollout the new config to. Only 1 rollout must be associated with each deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Game<wbr>Server<wbr>Config<wbr>Overrides</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverride">List&lt;Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The game_server_config_overrides contains the per game server config overrides. The overrides are processed in the order
they are listed. As soon as a match is found for a cluster, the rest of the list is not processed.
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
            <td class="align-top">Default<wbr>Game<wbr>Server<wbr>Config</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
This field points to the game server config that is applied by default to all realms and clusters. For example,
&#39;projects/my-project/locations/global/gameServerDeployments/my-game/configs/my-config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The deployment to rollout the new config to. Only 1 rollout must be associated with each deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Game<wbr>Server<wbr>Config<wbr>Overrides</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverride">[]Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The game_server_config_overrides contains the per game server config overrides. The overrides are processed in the order
they are listed. As soon as a match is found for a cluster, the rest of the list is not processed.
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
            <td class="align-top">default<wbr>Game<wbr>Server<wbr>Config</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
This field points to the game server config that is applied by default to all realms and clusters. For example,
&#39;projects/my-project/locations/global/gameServerDeployments/my-game/configs/my-config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The deployment to rollout the new config to. Only 1 rollout must be associated with each deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">game<wbr>Server<wbr>Config<wbr>Overrides</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverride">Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The game_server_config_overrides contains the per game server config overrides. The overrides are processed in the order
they are listed. As soon as a match is found for a cluster, the rest of the list is not processed.
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
            <td class="align-top">default_<wbr>game_<wbr>server_<wbr>config</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
This field points to the game server config that is applied by default to all realms and clusters. For example,
&#39;projects/my-project/locations/global/gameServerDeployments/my-game/configs/my-config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The deployment to rollout the new config to. Only 1 rollout must be associated with each deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">game_<wbr>server_<wbr>config_<wbr>overrides</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverride">List[Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The game_server_config_overrides contains the per game server config overrides. The overrides are processed in the order
they are listed. As soon as a match is found for a cluster, the rest of the list is not processed.
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
    
    </tbody>
</table>


{{% /lang %}}







## GameServerDeploymentRollout Output Properties

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
            <td class="align-top">Default<wbr>Game<wbr>Server<wbr>Config</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} This field points to the game server config that is applied by default to all realms and clusters. For example,
&#39;projects/my-project/locations/global/gameServerDeployments/my-game/configs/my-config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The deployment to rollout the new config to. Only 1 rollout must be associated with each deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Game<wbr>Server<wbr>Config<wbr>Overrides</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverride">List&lt;Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} The game_server_config_overrides contains the per game server config overrides. The overrides are processed in the order
they are listed. As soon as a match is found for a cluster, the rest of the list is not processed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The resource id of the game server deployment eg:
&#39;projects/my-project/locations/global/gameServerDeployments/my-deployment/rollout&#39;.
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
            <td class="align-top">Default<wbr>Game<wbr>Server<wbr>Config</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} This field points to the game server config that is applied by default to all realms and clusters. For example,
&#39;projects/my-project/locations/global/gameServerDeployments/my-game/configs/my-config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The deployment to rollout the new config to. Only 1 rollout must be associated with each deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Game<wbr>Server<wbr>Config<wbr>Overrides</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverride">[]Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override</a></code>
            </td>
            <td class="align-top">{{% md %}} The game_server_config_overrides contains the per game server config overrides. The overrides are processed in the order
they are listed. As soon as a match is found for a cluster, the rest of the list is not processed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The resource id of the game server deployment eg:
&#39;projects/my-project/locations/global/gameServerDeployments/my-deployment/rollout&#39;.
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
            <td class="align-top">default<wbr>Game<wbr>Server<wbr>Config</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} This field points to the game server config that is applied by default to all realms and clusters. For example,
&#39;projects/my-project/locations/global/gameServerDeployments/my-game/configs/my-config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The deployment to rollout the new config to. Only 1 rollout must be associated with each deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">game<wbr>Server<wbr>Config<wbr>Overrides</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverride">Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} The game_server_config_overrides contains the per game server config overrides. The overrides are processed in the order
they are listed. As soon as a match is found for a cluster, the rest of the list is not processed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The resource id of the game server deployment eg:
&#39;projects/my-project/locations/global/gameServerDeployments/my-deployment/rollout&#39;.
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
            <td class="align-top">default_<wbr>game_<wbr>server_<wbr>config</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} This field points to the game server config that is applied by default to all realms and clusters. For example,
&#39;projects/my-project/locations/global/gameServerDeployments/my-game/configs/my-config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The deployment to rollout the new config to. Only 1 rollout must be associated with each deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">game_<wbr>server_<wbr>config_<wbr>overrides</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverride">List[Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override]</a></code>
            </td>
            <td class="align-top">{{% md %}} The game_server_config_overrides contains the per game server config overrides. The overrides are processed in the order
they are listed. As soon as a match is found for a cluster, the rest of the list is not processed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The resource id of the game server deployment eg:
&#39;projects/my-project/locations/global/gameServerDeployments/my-deployment/rollout&#39;.
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
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing GameServerDeploymentRollout Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/gameservices/#GameServerDeploymentRolloutState">GameServerDeploymentRolloutState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/gameservices/#GameServerDeploymentRollout">GameServerDeploymentRollout</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>default_game_server_config=None<span class="p">, </span>deployment_id=None<span class="p">, </span>game_server_config_overrides=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetGameServerDeploymentRollout<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/gameservices?tab=doc#GameServerDeploymentRolloutState">GameServerDeploymentRolloutState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/gameservices?tab=doc#GameServerDeploymentRollout">GameServerDeploymentRollout</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Gameservices.GameServerDeploymentRollout.html">GameServerDeploymentRollout</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Gameservices.GameServerDeploymentRolloutState.html">GameServerDeploymentRolloutState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing GameServerDeploymentRollout resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Default<wbr>Game<wbr>Server<wbr>Config</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field points to the game server config that is applied by default to all realms and clusters. For example,
&#39;projects/my-project/locations/global/gameServerDeployments/my-game/configs/my-config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The deployment to rollout the new config to. Only 1 rollout must be associated with each deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Game<wbr>Server<wbr>Config<wbr>Overrides</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverride">List&lt;Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The game_server_config_overrides contains the per game server config overrides. The overrides are processed in the order
they are listed. As soon as a match is found for a cluster, the rest of the list is not processed.
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
The resource id of the game server deployment eg:
&#39;projects/my-project/locations/global/gameServerDeployments/my-deployment/rollout&#39;.
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
            <td class="align-top">Default<wbr>Game<wbr>Server<wbr>Config</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field points to the game server config that is applied by default to all realms and clusters. For example,
&#39;projects/my-project/locations/global/gameServerDeployments/my-game/configs/my-config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The deployment to rollout the new config to. Only 1 rollout must be associated with each deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Game<wbr>Server<wbr>Config<wbr>Overrides</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverride">[]Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The game_server_config_overrides contains the per game server config overrides. The overrides are processed in the order
they are listed. As soon as a match is found for a cluster, the rest of the list is not processed.
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
The resource id of the game server deployment eg:
&#39;projects/my-project/locations/global/gameServerDeployments/my-deployment/rollout&#39;.
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
            <td class="align-top">default<wbr>Game<wbr>Server<wbr>Config</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field points to the game server config that is applied by default to all realms and clusters. For example,
&#39;projects/my-project/locations/global/gameServerDeployments/my-game/configs/my-config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The deployment to rollout the new config to. Only 1 rollout must be associated with each deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">game<wbr>Server<wbr>Config<wbr>Overrides</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverride">Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The game_server_config_overrides contains the per game server config overrides. The overrides are processed in the order
they are listed. As soon as a match is found for a cluster, the rest of the list is not processed.
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
The resource id of the game server deployment eg:
&#39;projects/my-project/locations/global/gameServerDeployments/my-deployment/rollout&#39;.
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
            <td class="align-top">default_<wbr>game_<wbr>server_<wbr>config</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field points to the game server config that is applied by default to all realms and clusters. For example,
&#39;projects/my-project/locations/global/gameServerDeployments/my-game/configs/my-config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The deployment to rollout the new config to. Only 1 rollout must be associated with each deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">game_<wbr>server_<wbr>config_<wbr>overrides</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverride">List[Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The game_server_config_overrides contains the per game server config overrides. The overrides are processed in the order
they are listed. As soon as a match is found for a cluster, the rest of the list is not processed.
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
The resource id of the game server deployment eg:
&#39;projects/my-project/locations/global/gameServerDeployments/my-deployment/rollout&#39;.
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
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### GameServerDeploymentRolloutGameServerConfigOverride
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#GameServerDeploymentRolloutGameServerConfigOverride">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GameServerDeploymentRolloutGameServerConfigOverride">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/gameservices?tab=doc#GameServerDeploymentRolloutGameServerConfigOverrideArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/gameservices?tab=doc#GameServerDeploymentRolloutGameServerConfigOverrideOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Gameservices.GameServerDeploymentRolloutGameServerConfigOverrideArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Gameservices.GameServerDeploymentRolloutGameServerConfigOverride.html">output</a> API doc for this type.
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
            <td class="align-top">Config<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Realms<wbr>Selector</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverriderealmsselector">Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override<wbr>Realms<wbr>Selector<wbr>Args?</a></code>
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
            <td class="align-top">Config<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Realms<wbr>Selector</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverriderealmsselector">*Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override<wbr>Realms<wbr>Selector</a></code>
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
            <td class="align-top">config<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">realms<wbr>Selector</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverriderealmsselector">Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override<wbr>Realms<wbr>Selector?</a></code>
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
            <td class="align-top">config<wbr>Version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">realms<wbr>Selector</td>
            <td class="align-top">
                
                <code><a href="#gameserverdeploymentrolloutgameserverconfigoverriderealmsselector">Dict[Game<wbr>Server<wbr>Deployment<wbr>Rollout<wbr>Game<wbr>Server<wbr>Config<wbr>Override<wbr>Realms<wbr>Selector]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GameServerDeploymentRolloutGameServerConfigOverrideRealmsSelector
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#GameServerDeploymentRolloutGameServerConfigOverrideRealmsSelector">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GameServerDeploymentRolloutGameServerConfigOverrideRealmsSelector">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/gameservices?tab=doc#GameServerDeploymentRolloutGameServerConfigOverrideRealmsSelectorArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/gameservices?tab=doc#GameServerDeploymentRolloutGameServerConfigOverrideRealmsSelectorOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Gameservices.GameServerDeploymentRolloutGameServerConfigOverrideRealmsSelectorArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Gameservices.GameServerDeploymentRolloutGameServerConfigOverrideRealmsSelector.html">output</a> API doc for this type.
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
            <td class="align-top">Realms</td>
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
            <td class="align-top">Realms</td>
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
            <td class="align-top">realms</td>
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
            <td class="align-top">realms</td>
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








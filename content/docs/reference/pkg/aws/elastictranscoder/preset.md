
---
title: "Preset"
block_external_search_index: true
---

Provides an Elastic Transcoder preset resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const bar = new aws.elastictranscoder.Preset("bar", {
    audio: {
        audioPackingMode: "SingleTrack",
        bitRate: "96",
        channels: "2",
        codec: "AAC",
        sampleRate: "44100",
    },
    audioCodecOptions: {
        profile: "AAC-LC",
    },
    container: "mp4",
    description: "Sample Preset",
    thumbnails: {
        format: "png",
        interval: "120",
        maxHeight: "auto",
        maxWidth: "auto",
        paddingPolicy: "Pad",
        sizingPolicy: "Fit",
    },
    video: {
        bitRate: "1600",
        codec: "H.264",
        displayAspectRatio: "16:9",
        fixedGop: "false",
        frameRate: "auto",
        keyframesMaxDist: "240",
        maxFrameRate: "60",
        maxHeight: "auto",
        maxWidth: "auto",
        paddingPolicy: "Pad",
        sizingPolicy: "Fit",
    },
    videoCodecOptions: {
        ColorSpaceConversionMode: "None",
        InterlacedMode: "Progressive",
        Level: "2.2",
        MaxReferenceFrames: 3,
        Profile: "main",
    },
    videoWatermarks: [{
        horizontalAlign: "Right",
        horizontalOffset: "10px",
        id: "Test",
        maxHeight: "20%",
        maxWidth: "20%",
        opacity: "55.5",
        sizingPolicy: "ShrinkToFit",
        target: "Content",
        verticalAlign: "Bottom",
        verticalOffset: "10px",
    }],
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/elastictranscoder_preset.html.markdown.



## Create a Preset Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elastictranscoder/#Preset">Preset</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elastictranscoder/#PresetArgs">PresetArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Preset</span><span class="p">(resource_name, opts=None, </span>audio=None<span class="p">, </span>audio_codec_options=None<span class="p">, </span>container=None<span class="p">, </span>description=None<span class="p">, </span>name=None<span class="p">, </span>thumbnails=None<span class="p">, </span>type=None<span class="p">, </span>video=None<span class="p">, </span>video_codec_options=None<span class="p">, </span>video_watermarks=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewPreset<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PresetArgs">PresetArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#Preset">Preset</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.Preset.html">Preset</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PresetArgs.html">PresetArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Audio<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudio">Preset<wbr>Audio<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Audio parameters object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Audio<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudiocodecoptions">Preset<wbr>Audio<wbr>Codec<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Codec options for the audio parameters (documented below)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Container<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The container type for the output file. Valid values are `flac`, `flv`, `fmp4`, `gif`, `mp3`, `mp4`, `mpg`, `mxf`, `oga`, `ogg`, `ts`, and `webm`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the preset (maximum 255 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the preset. (maximum 40 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Thumbnails<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetthumbnails">Preset<wbr>Thumbnails<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Thumbnail parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Video<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideo">Preset<wbr>Video<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Video parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Video<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Video<wbr>Watermarks<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideowatermark">List&lt;Preset<wbr>Video<wbr>Watermark<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Watermark parameters for the video parameters (documented below)
* `video_codec_options` (Optional, Forces new resource) Codec options for the video parameters
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Audio<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudio">*Preset<wbr>Audio</a></span>
    </dt>
    <dd>{{% md %}}Audio parameters object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Audio<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudiocodecoptions">*Preset<wbr>Audio<wbr>Codec<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}Codec options for the audio parameters (documented below)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Container<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The container type for the output file. Valid values are `flac`, `flv`, `fmp4`, `gif`, `mp3`, `mp4`, `mpg`, `mxf`, `oga`, `ogg`, `ts`, and `webm`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A description of the preset (maximum 255 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the preset. (maximum 40 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Thumbnails<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetthumbnails">*Preset<wbr>Thumbnails</a></span>
    </dt>
    <dd>{{% md %}}Thumbnail parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Video<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideo">*Preset<wbr>Video</a></span>
    </dt>
    <dd>{{% md %}}Video parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Video<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Video<wbr>Watermarks<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideowatermark">[]Preset<wbr>Video<wbr>Watermark</a></span>
    </dt>
    <dd>{{% md %}}Watermark parameters for the video parameters (documented below)
* `video_codec_options` (Optional, Forces new resource) Codec options for the video parameters
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">audio<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudio">Preset<wbr>Audio?</a></span>
    </dt>
    <dd>{{% md %}}Audio parameters object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">audio<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudiocodecoptions">Preset<wbr>Audio<wbr>Codec<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}Codec options for the audio parameters (documented below)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">container<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The container type for the output file. Valid values are `flac`, `flv`, `fmp4`, `gif`, `mp3`, `mp4`, `mpg`, `mxf`, `oga`, `ogg`, `ts`, and `webm`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the preset (maximum 255 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the preset. (maximum 40 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">thumbnails<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetthumbnails">Preset<wbr>Thumbnails?</a></span>
    </dt>
    <dd>{{% md %}}Thumbnail parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">video<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideo">Preset<wbr>Video?</a></span>
    </dt>
    <dd>{{% md %}}Video parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">video<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">video<wbr>Watermarks<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideowatermark">Preset<wbr>Video<wbr>Watermark[]?</a></span>
    </dt>
    <dd>{{% md %}}Watermark parameters for the video parameters (documented below)
* `video_codec_options` (Optional, Forces new resource) Codec options for the video parameters
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">audio<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudio">Dict[Preset<wbr>Audio]</a></span>
    </dt>
    <dd>{{% md %}}Audio parameters object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">audio_<wbr>codec_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudiocodecoptions">Dict[Preset<wbr>Audio<wbr>Codec<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}Codec options for the audio parameters (documented below)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">container<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The container type for the output file. Valid values are `flac`, `flv`, `fmp4`, `gif`, `mp3`, `mp4`, `mpg`, `mxf`, `oga`, `ogg`, `ts`, and `webm`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A description of the preset (maximum 255 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the preset. (maximum 40 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">thumbnails<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetthumbnails">Dict[Preset<wbr>Thumbnails]</a></span>
    </dt>
    <dd>{{% md %}}Thumbnail parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">video<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideo">Dict[Preset<wbr>Video]</a></span>
    </dt>
    <dd>{{% md %}}Video parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">video_<wbr>codec_<wbr>options<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">video_<wbr>watermarks<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideowatermark">List[Preset<wbr>Video<wbr>Watermark]</a></span>
    </dt>
    <dd>{{% md %}}Watermark parameters for the video parameters (documented below)
* `video_codec_options` (Optional, Forces new resource) Codec options for the video parameters
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Preset Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Audio<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudio">Preset<wbr>Audio?</a></span>
    </dt>
    <dd>{{% md %}}Audio parameters object (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Audio<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudiocodecoptions">Preset<wbr>Audio<wbr>Codec<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}Codec options for the audio parameters (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Container<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The container type for the output file. Valid values are `flac`, `flv`, `fmp4`, `gif`, `mp3`, `mp4`, `mpg`, `mxf`, `oga`, `ogg`, `ts`, and `webm`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the preset (maximum 255 characters)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the preset. (maximum 40 characters)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Thumbnails<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetthumbnails">Preset<wbr>Thumbnails?</a></span>
    </dt>
    <dd>{{% md %}}Thumbnail parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Video<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideo">Preset<wbr>Video?</a></span>
    </dt>
    <dd>{{% md %}}Video parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Video<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Video<wbr>Watermarks<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideowatermark">List&lt;Preset<wbr>Video<wbr>Watermark&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Watermark parameters for the video parameters (documented below)
* `video_codec_options` (Optional, Forces new resource) Codec options for the video parameters
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Audio<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudio">*Preset<wbr>Audio</a></span>
    </dt>
    <dd>{{% md %}}Audio parameters object (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Audio<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudiocodecoptions">*Preset<wbr>Audio<wbr>Codec<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}Codec options for the audio parameters (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Container<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The container type for the output file. Valid values are `flac`, `flv`, `fmp4`, `gif`, `mp3`, `mp4`, `mpg`, `mxf`, `oga`, `ogg`, `ts`, and `webm`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A description of the preset (maximum 255 characters)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the preset. (maximum 40 characters)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Thumbnails<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetthumbnails">*Preset<wbr>Thumbnails</a></span>
    </dt>
    <dd>{{% md %}}Thumbnail parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Video<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideo">*Preset<wbr>Video</a></span>
    </dt>
    <dd>{{% md %}}Video parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Video<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Video<wbr>Watermarks<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideowatermark">[]Preset<wbr>Video<wbr>Watermark</a></span>
    </dt>
    <dd>{{% md %}}Watermark parameters for the video parameters (documented below)
* `video_codec_options` (Optional, Forces new resource) Codec options for the video parameters
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">audio<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudio">Preset<wbr>Audio?</a></span>
    </dt>
    <dd>{{% md %}}Audio parameters object (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">audio<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudiocodecoptions">Preset<wbr>Audio<wbr>Codec<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}Codec options for the audio parameters (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">container<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The container type for the output file. Valid values are `flac`, `flv`, `fmp4`, `gif`, `mp3`, `mp4`, `mpg`, `mxf`, `oga`, `ogg`, `ts`, and `webm`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the preset (maximum 255 characters)
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the preset. (maximum 40 characters)
{{% /md %}}</dd>

    <dt class="property-"
            title="">thumbnails<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetthumbnails">Preset<wbr>Thumbnails?</a></span>
    </dt>
    <dd>{{% md %}}Thumbnail parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">video<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideo">Preset<wbr>Video?</a></span>
    </dt>
    <dd>{{% md %}}Video parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">video<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">video<wbr>Watermarks<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideowatermark">Preset<wbr>Video<wbr>Watermark[]?</a></span>
    </dt>
    <dd>{{% md %}}Watermark parameters for the video parameters (documented below)
* `video_codec_options` (Optional, Forces new resource) Codec options for the video parameters
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">audio<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudio">Dict[Preset<wbr>Audio]</a></span>
    </dt>
    <dd>{{% md %}}Audio parameters object (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">audio_<wbr>codec_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudiocodecoptions">Dict[Preset<wbr>Audio<wbr>Codec<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}Codec options for the audio parameters (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">container<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The container type for the output file. Valid values are `flac`, `flv`, `fmp4`, `gif`, `mp3`, `mp4`, `mpg`, `mxf`, `oga`, `ogg`, `ts`, and `webm`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A description of the preset (maximum 255 characters)
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the preset. (maximum 40 characters)
{{% /md %}}</dd>

    <dt class="property-"
            title="">thumbnails<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetthumbnails">Dict[Preset<wbr>Thumbnails]</a></span>
    </dt>
    <dd>{{% md %}}Thumbnail parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">video<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideo">Dict[Preset<wbr>Video]</a></span>
    </dt>
    <dd>{{% md %}}Video parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">video_<wbr>codec_<wbr>options<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">video_<wbr>watermarks<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideowatermark">List[Preset<wbr>Video<wbr>Watermark]</a></span>
    </dt>
    <dd>{{% md %}}Watermark parameters for the video parameters (documented below)
* `video_codec_options` (Optional, Forces new resource) Codec options for the video parameters
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Preset Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elastictranscoder/#PresetState">PresetState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elastictranscoder/#Preset">Preset</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>audio=None<span class="p">, </span>audio_codec_options=None<span class="p">, </span>container=None<span class="p">, </span>description=None<span class="p">, </span>name=None<span class="p">, </span>thumbnails=None<span class="p">, </span>type=None<span class="p">, </span>video=None<span class="p">, </span>video_codec_options=None<span class="p">, </span>video_watermarks=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetPreset<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PresetState">PresetState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#Preset">Preset</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.Preset.html">Preset</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PresetState.html">PresetState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Preset resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Audio<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudio">Preset<wbr>Audio<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Audio parameters object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Audio<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudiocodecoptions">Preset<wbr>Audio<wbr>Codec<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Codec options for the audio parameters (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Container<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The container type for the output file. Valid values are `flac`, `flv`, `fmp4`, `gif`, `mp3`, `mp4`, `mpg`, `mxf`, `oga`, `ogg`, `ts`, and `webm`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the preset (maximum 255 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the preset. (maximum 40 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Thumbnails<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetthumbnails">Preset<wbr>Thumbnails<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Thumbnail parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Video<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideo">Preset<wbr>Video<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Video parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Video<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Video<wbr>Watermarks<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideowatermark">List&lt;Preset<wbr>Video<wbr>Watermark<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Watermark parameters for the video parameters (documented below)
* `video_codec_options` (Optional, Forces new resource) Codec options for the video parameters
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Audio<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudio">*Preset<wbr>Audio</a></span>
    </dt>
    <dd>{{% md %}}Audio parameters object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Audio<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudiocodecoptions">*Preset<wbr>Audio<wbr>Codec<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}Codec options for the audio parameters (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Container<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The container type for the output file. Valid values are `flac`, `flv`, `fmp4`, `gif`, `mp3`, `mp4`, `mpg`, `mxf`, `oga`, `ogg`, `ts`, and `webm`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A description of the preset (maximum 255 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the preset. (maximum 40 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Thumbnails<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetthumbnails">*Preset<wbr>Thumbnails</a></span>
    </dt>
    <dd>{{% md %}}Thumbnail parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Video<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideo">*Preset<wbr>Video</a></span>
    </dt>
    <dd>{{% md %}}Video parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Video<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Video<wbr>Watermarks<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideowatermark">[]Preset<wbr>Video<wbr>Watermark</a></span>
    </dt>
    <dd>{{% md %}}Watermark parameters for the video parameters (documented below)
* `video_codec_options` (Optional, Forces new resource) Codec options for the video parameters
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">audio<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudio">Preset<wbr>Audio?</a></span>
    </dt>
    <dd>{{% md %}}Audio parameters object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">audio<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudiocodecoptions">Preset<wbr>Audio<wbr>Codec<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}Codec options for the audio parameters (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">container<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The container type for the output file. Valid values are `flac`, `flv`, `fmp4`, `gif`, `mp3`, `mp4`, `mpg`, `mxf`, `oga`, `ogg`, `ts`, and `webm`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the preset (maximum 255 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the preset. (maximum 40 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">thumbnails<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetthumbnails">Preset<wbr>Thumbnails?</a></span>
    </dt>
    <dd>{{% md %}}Thumbnail parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">video<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideo">Preset<wbr>Video?</a></span>
    </dt>
    <dd>{{% md %}}Video parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">video<wbr>Codec<wbr>Options<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">video<wbr>Watermarks<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideowatermark">Preset<wbr>Video<wbr>Watermark[]?</a></span>
    </dt>
    <dd>{{% md %}}Watermark parameters for the video parameters (documented below)
* `video_codec_options` (Optional, Forces new resource) Codec options for the video parameters
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">audio<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudio">Dict[Preset<wbr>Audio]</a></span>
    </dt>
    <dd>{{% md %}}Audio parameters object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">audio_<wbr>codec_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetaudiocodecoptions">Dict[Preset<wbr>Audio<wbr>Codec<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}Codec options for the audio parameters (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">container<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The container type for the output file. Valid values are `flac`, `flv`, `fmp4`, `gif`, `mp3`, `mp4`, `mpg`, `mxf`, `oga`, `ogg`, `ts`, and `webm`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A description of the preset (maximum 255 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the preset. (maximum 40 characters)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">thumbnails<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetthumbnails">Dict[Preset<wbr>Thumbnails]</a></span>
    </dt>
    <dd>{{% md %}}Thumbnail parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">video<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideo">Dict[Preset<wbr>Video]</a></span>
    </dt>
    <dd>{{% md %}}Video parameters object (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">video_<wbr>codec_<wbr>options<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">video_<wbr>watermarks<span class="property-indicator"></span>
        <span class="property-type"><a href="#presetvideowatermark">List[Preset<wbr>Video<wbr>Watermark]</a></span>
    </dt>
    <dd>{{% md %}}Watermark parameters for the video parameters (documented below)
* `video_codec_options` (Optional, Forces new resource) Codec options for the video parameters
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### PresetAudio
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PresetAudio">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PresetAudio">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PresetAudioArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PresetAudioOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PresetAudioArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PresetAudio.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Audio<wbr>Packing<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The method of organizing audio channels and tracks. Use Audio:Channels to specify the number of channels in your output, and Audio:AudioPackingMode to specify the number of tracks and their relation to the channels. If you do not specify an Audio:AudioPackingMode, Elastic Transcoder uses SingleTrack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bit<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The bit rate of the video stream in the output file, in kilobits/second. You can configure variable bit rate or constant bit rate encoding.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Channels<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The number of audio channels in the output file
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Codec<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The video codec for the output file. Valid values are `gif`, `H.264`, `mpeg2`, `vp8`, and `vp9`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The sample rate of the audio stream in the output file, in hertz. Valid values are: `auto`, `22050`, `32000`, `44100`, `48000`, `96000`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Audio<wbr>Packing<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The method of organizing audio channels and tracks. Use Audio:Channels to specify the number of channels in your output, and Audio:AudioPackingMode to specify the number of tracks and their relation to the channels. If you do not specify an Audio:AudioPackingMode, Elastic Transcoder uses SingleTrack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bit<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The bit rate of the video stream in the output file, in kilobits/second. You can configure variable bit rate or constant bit rate encoding.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Channels<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The number of audio channels in the output file
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Codec<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The video codec for the output file. Valid values are `gif`, `H.264`, `mpeg2`, `vp8`, and `vp9`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The sample rate of the audio stream in the output file, in hertz. Valid values are: `auto`, `22050`, `32000`, `44100`, `48000`, `96000`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">audio<wbr>Packing<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The method of organizing audio channels and tracks. Use Audio:Channels to specify the number of channels in your output, and Audio:AudioPackingMode to specify the number of tracks and their relation to the channels. If you do not specify an Audio:AudioPackingMode, Elastic Transcoder uses SingleTrack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bit<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The bit rate of the video stream in the output file, in kilobits/second. You can configure variable bit rate or constant bit rate encoding.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">channels<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The number of audio channels in the output file
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">codec<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The video codec for the output file. Valid values are `gif`, `H.264`, `mpeg2`, `vp8`, and `vp9`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The sample rate of the audio stream in the output file, in hertz. Valid values are: `auto`, `22050`, `32000`, `44100`, `48000`, `96000`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">audio<wbr>Packing<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The method of organizing audio channels and tracks. Use Audio:Channels to specify the number of channels in your output, and Audio:AudioPackingMode to specify the number of tracks and their relation to the channels. If you do not specify an Audio:AudioPackingMode, Elastic Transcoder uses SingleTrack.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bit<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The bit rate of the video stream in the output file, in kilobits/second. You can configure variable bit rate or constant bit rate encoding.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">channels<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The number of audio channels in the output file
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">codec<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The video codec for the output file. Valid values are `gif`, `H.264`, `mpeg2`, `vp8`, and `vp9`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The sample rate of the audio stream in the output file, in hertz. Valid values are: `auto`, `22050`, `32000`, `44100`, `48000`, `96000`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### PresetAudioCodecOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PresetAudioCodecOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PresetAudioCodecOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PresetAudioCodecOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PresetAudioCodecOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PresetAudioCodecOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PresetAudioCodecOptions.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Bit<wbr>Depth<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The bit depth of a sample is how many bits of information are included in the audio samples. Valid values are `16` and `24`. (FLAC/PCM Only)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bit<wbr>Order<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The order the bits of a PCM sample are stored in. The supported value is LittleEndian. (PCM Only)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Profile<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If you specified AAC for Audio:Codec, choose the AAC profile for the output file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Signed<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Whether audio samples are represented with negative and positive numbers (signed) or only positive numbers (unsigned). The supported value is Signed. (PCM Only)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Bit<wbr>Depth<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The bit depth of a sample is how many bits of information are included in the audio samples. Valid values are `16` and `24`. (FLAC/PCM Only)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bit<wbr>Order<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The order the bits of a PCM sample are stored in. The supported value is LittleEndian. (PCM Only)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Profile<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If you specified AAC for Audio:Codec, choose the AAC profile for the output file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Signed<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Whether audio samples are represented with negative and positive numbers (signed) or only positive numbers (unsigned). The supported value is Signed. (PCM Only)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bit<wbr>Depth<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The bit depth of a sample is how many bits of information are included in the audio samples. Valid values are `16` and `24`. (FLAC/PCM Only)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bit<wbr>Order<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The order the bits of a PCM sample are stored in. The supported value is LittleEndian. (PCM Only)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">profile<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If you specified AAC for Audio:Codec, choose the AAC profile for the output file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">signed<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Whether audio samples are represented with negative and positive numbers (signed) or only positive numbers (unsigned). The supported value is Signed. (PCM Only)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bit<wbr>Depth<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The bit depth of a sample is how many bits of information are included in the audio samples. Valid values are `16` and `24`. (FLAC/PCM Only)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bit<wbr>Order<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The order the bits of a PCM sample are stored in. The supported value is LittleEndian. (PCM Only)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">profile<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If you specified AAC for Audio:Codec, choose the AAC profile for the output file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">signed<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Whether audio samples are represented with negative and positive numbers (signed) or only positive numbers (unsigned). The supported value is Signed. (PCM Only)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### PresetThumbnails
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PresetThumbnails">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PresetThumbnails">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PresetThumbnailsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PresetThumbnailsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PresetThumbnailsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PresetThumbnails.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Aspect<wbr>Ratio<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The display aspect ratio of the video in the output file. Valid values are: `auto`, `1:1`, `4:3`, `3:2`, `16:9`. (Note; to better control resolution and aspect ratio of output videos, we recommend that you use the values `max_width`, `max_height`, `sizing_policy`, `padding_policy`, and `display_aspect_ratio` instead of `resolution` and `aspect_ratio`.)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The format of thumbnails, if any. Valid formats are jpg and png.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Interval<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The approximate number of seconds between thumbnails. The value must be an integer. The actual interval can vary by several seconds from one thumbnail to the next.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Height<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum height of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Width<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum width of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Padding<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When you set PaddingPolicy to Pad, Elastic Transcoder might add black bars to the top and bottom and/or left and right sides of the output video to make the total size of the output video match the values that you specified for `max_width` and `max_height`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resolution<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The width and height of the video in the output file, in pixels. Valid values are `auto` and `widthxheight`. (see note for `aspect_ratio`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sizing<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A value that controls scaling of the watermark. Valid values are: `Fit`, `Stretch`, `ShrinkToFit`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Aspect<wbr>Ratio<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The display aspect ratio of the video in the output file. Valid values are: `auto`, `1:1`, `4:3`, `3:2`, `16:9`. (Note; to better control resolution and aspect ratio of output videos, we recommend that you use the values `max_width`, `max_height`, `sizing_policy`, `padding_policy`, and `display_aspect_ratio` instead of `resolution` and `aspect_ratio`.)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Format<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The format of thumbnails, if any. Valid formats are jpg and png.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Interval<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The approximate number of seconds between thumbnails. The value must be an integer. The actual interval can vary by several seconds from one thumbnail to the next.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Height<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum height of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Width<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum width of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Padding<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}When you set PaddingPolicy to Pad, Elastic Transcoder might add black bars to the top and bottom and/or left and right sides of the output video to make the total size of the output video match the values that you specified for `max_width` and `max_height`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resolution<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The width and height of the video in the output file, in pixels. Valid values are `auto` and `widthxheight`. (see note for `aspect_ratio`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sizing<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A value that controls scaling of the watermark. Valid values are: `Fit`, `Stretch`, `ShrinkToFit`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">aspect<wbr>Ratio<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The display aspect ratio of the video in the output file. Valid values are: `auto`, `1:1`, `4:3`, `3:2`, `16:9`. (Note; to better control resolution and aspect ratio of output videos, we recommend that you use the values `max_width`, `max_height`, `sizing_policy`, `padding_policy`, and `display_aspect_ratio` instead of `resolution` and `aspect_ratio`.)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The format of thumbnails, if any. Valid formats are jpg and png.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">interval<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The approximate number of seconds between thumbnails. The value must be an integer. The actual interval can vary by several seconds from one thumbnail to the next.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Height<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum height of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Width<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum width of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">padding<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When you set PaddingPolicy to Pad, Elastic Transcoder might add black bars to the top and bottom and/or left and right sides of the output video to make the total size of the output video match the values that you specified for `max_width` and `max_height`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resolution<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The width and height of the video in the output file, in pixels. Valid values are `auto` and `widthxheight`. (see note for `aspect_ratio`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sizing<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A value that controls scaling of the watermark. Valid values are: `Fit`, `Stretch`, `ShrinkToFit`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">aspect<wbr>Ratio<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The display aspect ratio of the video in the output file. Valid values are: `auto`, `1:1`, `4:3`, `3:2`, `16:9`. (Note; to better control resolution and aspect ratio of output videos, we recommend that you use the values `max_width`, `max_height`, `sizing_policy`, `padding_policy`, and `display_aspect_ratio` instead of `resolution` and `aspect_ratio`.)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">format<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The format of thumbnails, if any. Valid formats are jpg and png.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">interval<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The approximate number of seconds between thumbnails. The value must be an integer. The actual interval can vary by several seconds from one thumbnail to the next.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Height<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum height of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Width<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum width of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">padding<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When you set PaddingPolicy to Pad, Elastic Transcoder might add black bars to the top and bottom and/or left and right sides of the output video to make the total size of the output video match the values that you specified for `max_width` and `max_height`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resolution<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The width and height of the video in the output file, in pixels. Valid values are `auto` and `widthxheight`. (see note for `aspect_ratio`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sizing<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A value that controls scaling of the watermark. Valid values are: `Fit`, `Stretch`, `ShrinkToFit`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### PresetVideo
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PresetVideo">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PresetVideo">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PresetVideoArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PresetVideoOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PresetVideoArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PresetVideo.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Aspect<wbr>Ratio<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The display aspect ratio of the video in the output file. Valid values are: `auto`, `1:1`, `4:3`, `3:2`, `16:9`. (Note; to better control resolution and aspect ratio of output videos, we recommend that you use the values `max_width`, `max_height`, `sizing_policy`, `padding_policy`, and `display_aspect_ratio` instead of `resolution` and `aspect_ratio`.)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bit<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The bit rate of the video stream in the output file, in kilobits/second. You can configure variable bit rate or constant bit rate encoding.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Codec<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The video codec for the output file. Valid values are `gif`, `H.264`, `mpeg2`, `vp8`, and `vp9`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Display<wbr>Aspect<wbr>Ratio<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The value that Elastic Transcoder adds to the metadata in the output file. If you set DisplayAspectRatio to auto, Elastic Transcoder chooses an aspect ratio that ensures square pixels. If you specify another option, Elastic Transcoder sets that value in the output file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Fixed<wbr>Gop<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Whether to use a fixed value for Video:FixedGOP. Not applicable for containers of type gif. Valid values are true and false. Also known as, Fixed Number of Frames Between Keyframes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Frame<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The frames per second for the video stream in the output file. The following values are valid: `auto`, `10`, `15`, `23.97`, `24`, `25`, `29.97`, `30`, `50`, `60`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Keyframes<wbr>Max<wbr>Dist<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum number of frames between key frames. Not applicable for containers of type gif.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Frame<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If you specify auto for FrameRate, Elastic Transcoder uses the frame rate of the input video for the frame rate of the output video, up to the maximum frame rate. If you do not specify a MaxFrameRate, Elastic Transcoder will use a default of 30.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Height<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum height of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Width<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum width of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Padding<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When you set PaddingPolicy to Pad, Elastic Transcoder might add black bars to the top and bottom and/or left and right sides of the output video to make the total size of the output video match the values that you specified for `max_width` and `max_height`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resolution<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The width and height of the video in the output file, in pixels. Valid values are `auto` and `widthxheight`. (see note for `aspect_ratio`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sizing<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A value that controls scaling of the watermark. Valid values are: `Fit`, `Stretch`, `ShrinkToFit`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Aspect<wbr>Ratio<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The display aspect ratio of the video in the output file. Valid values are: `auto`, `1:1`, `4:3`, `3:2`, `16:9`. (Note; to better control resolution and aspect ratio of output videos, we recommend that you use the values `max_width`, `max_height`, `sizing_policy`, `padding_policy`, and `display_aspect_ratio` instead of `resolution` and `aspect_ratio`.)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bit<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The bit rate of the video stream in the output file, in kilobits/second. You can configure variable bit rate or constant bit rate encoding.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Codec<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The video codec for the output file. Valid values are `gif`, `H.264`, `mpeg2`, `vp8`, and `vp9`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Display<wbr>Aspect<wbr>Ratio<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The value that Elastic Transcoder adds to the metadata in the output file. If you set DisplayAspectRatio to auto, Elastic Transcoder chooses an aspect ratio that ensures square pixels. If you specify another option, Elastic Transcoder sets that value in the output file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Fixed<wbr>Gop<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Whether to use a fixed value for Video:FixedGOP. Not applicable for containers of type gif. Valid values are true and false. Also known as, Fixed Number of Frames Between Keyframes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Frame<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The frames per second for the video stream in the output file. The following values are valid: `auto`, `10`, `15`, `23.97`, `24`, `25`, `29.97`, `30`, `50`, `60`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Keyframes<wbr>Max<wbr>Dist<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum number of frames between key frames. Not applicable for containers of type gif.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Frame<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If you specify auto for FrameRate, Elastic Transcoder uses the frame rate of the input video for the frame rate of the output video, up to the maximum frame rate. If you do not specify a MaxFrameRate, Elastic Transcoder will use a default of 30.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Height<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum height of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Width<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum width of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Padding<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}When you set PaddingPolicy to Pad, Elastic Transcoder might add black bars to the top and bottom and/or left and right sides of the output video to make the total size of the output video match the values that you specified for `max_width` and `max_height`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resolution<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The width and height of the video in the output file, in pixels. Valid values are `auto` and `widthxheight`. (see note for `aspect_ratio`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sizing<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A value that controls scaling of the watermark. Valid values are: `Fit`, `Stretch`, `ShrinkToFit`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">aspect<wbr>Ratio<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The display aspect ratio of the video in the output file. Valid values are: `auto`, `1:1`, `4:3`, `3:2`, `16:9`. (Note; to better control resolution and aspect ratio of output videos, we recommend that you use the values `max_width`, `max_height`, `sizing_policy`, `padding_policy`, and `display_aspect_ratio` instead of `resolution` and `aspect_ratio`.)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bit<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The bit rate of the video stream in the output file, in kilobits/second. You can configure variable bit rate or constant bit rate encoding.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">codec<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The video codec for the output file. Valid values are `gif`, `H.264`, `mpeg2`, `vp8`, and `vp9`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">display<wbr>Aspect<wbr>Ratio<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The value that Elastic Transcoder adds to the metadata in the output file. If you set DisplayAspectRatio to auto, Elastic Transcoder chooses an aspect ratio that ensures square pixels. If you specify another option, Elastic Transcoder sets that value in the output file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">fixed<wbr>Gop<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Whether to use a fixed value for Video:FixedGOP. Not applicable for containers of type gif. Valid values are true and false. Also known as, Fixed Number of Frames Between Keyframes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">frame<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The frames per second for the video stream in the output file. The following values are valid: `auto`, `10`, `15`, `23.97`, `24`, `25`, `29.97`, `30`, `50`, `60`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">keyframes<wbr>Max<wbr>Dist<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum number of frames between key frames. Not applicable for containers of type gif.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Frame<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If you specify auto for FrameRate, Elastic Transcoder uses the frame rate of the input video for the frame rate of the output video, up to the maximum frame rate. If you do not specify a MaxFrameRate, Elastic Transcoder will use a default of 30.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Height<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum height of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Width<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum width of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">padding<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When you set PaddingPolicy to Pad, Elastic Transcoder might add black bars to the top and bottom and/or left and right sides of the output video to make the total size of the output video match the values that you specified for `max_width` and `max_height`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resolution<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The width and height of the video in the output file, in pixels. Valid values are `auto` and `widthxheight`. (see note for `aspect_ratio`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sizing<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A value that controls scaling of the watermark. Valid values are: `Fit`, `Stretch`, `ShrinkToFit`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">aspect<wbr>Ratio<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The display aspect ratio of the video in the output file. Valid values are: `auto`, `1:1`, `4:3`, `3:2`, `16:9`. (Note; to better control resolution and aspect ratio of output videos, we recommend that you use the values `max_width`, `max_height`, `sizing_policy`, `padding_policy`, and `display_aspect_ratio` instead of `resolution` and `aspect_ratio`.)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bit<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The bit rate of the video stream in the output file, in kilobits/second. You can configure variable bit rate or constant bit rate encoding.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">codec<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The video codec for the output file. Valid values are `gif`, `H.264`, `mpeg2`, `vp8`, and `vp9`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">display<wbr>Aspect<wbr>Ratio<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The value that Elastic Transcoder adds to the metadata in the output file. If you set DisplayAspectRatio to auto, Elastic Transcoder chooses an aspect ratio that ensures square pixels. If you specify another option, Elastic Transcoder sets that value in the output file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">fixed<wbr>Gop<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Whether to use a fixed value for Video:FixedGOP. Not applicable for containers of type gif. Valid values are true and false. Also known as, Fixed Number of Frames Between Keyframes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">frame<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The frames per second for the video stream in the output file. The following values are valid: `auto`, `10`, `15`, `23.97`, `24`, `25`, `29.97`, `30`, `50`, `60`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">keyframes<wbr>Max<wbr>Dist<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum number of frames between key frames. Not applicable for containers of type gif.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Frame<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If you specify auto for FrameRate, Elastic Transcoder uses the frame rate of the input video for the frame rate of the output video, up to the maximum frame rate. If you do not specify a MaxFrameRate, Elastic Transcoder will use a default of 30.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Height<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum height of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Width<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum width of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">padding<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When you set PaddingPolicy to Pad, Elastic Transcoder might add black bars to the top and bottom and/or left and right sides of the output video to make the total size of the output video match the values that you specified for `max_width` and `max_height`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resolution<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The width and height of the video in the output file, in pixels. Valid values are `auto` and `widthxheight`. (see note for `aspect_ratio`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sizing<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A value that controls scaling of the watermark. Valid values are: `Fit`, `Stretch`, `ShrinkToFit`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### PresetVideoWatermark
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PresetVideoWatermark">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PresetVideoWatermark">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PresetVideoWatermarkArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PresetVideoWatermarkOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PresetVideoWatermarkArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PresetVideoWatermark.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Horizontal<wbr>Align<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The horizontal position of the watermark unless you specify a nonzero value for `horzontal_offset`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Horizontal<wbr>Offset<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The amount by which you want the horizontal position of the watermark to be offset from the position specified by `horizontal_align`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique identifier for the settings for one watermark. The value of Id can be up to 40 characters long. You can specify settings for up to four watermarks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Height<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum height of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Width<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum width of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Opacity<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A percentage that indicates how much you want a watermark to obscure the video in the location where it appears.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sizing<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A value that controls scaling of the watermark. Valid values are: `Fit`, `Stretch`, `ShrinkToFit`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A value that determines how Elastic Transcoder interprets values that you specified for `video_watermarks.horizontal_offset`, `video_watermarks.vertical_offset`, `video_watermarks.max_width`, and `video_watermarks.max_height`. Valid values are `Content` and `Frame`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vertical<wbr>Align<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The vertical position of the watermark unless you specify a nonzero value for `vertical_align`. Valid values are `Top`, `Bottom`, `Center`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vertical<wbr>Offset<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The amount by which you want the vertical position of the watermark to be offset from the position specified by `vertical_align`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Horizontal<wbr>Align<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The horizontal position of the watermark unless you specify a nonzero value for `horzontal_offset`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Horizontal<wbr>Offset<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The amount by which you want the horizontal position of the watermark to be offset from the position specified by `horizontal_align`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A unique identifier for the settings for one watermark. The value of Id can be up to 40 characters long. You can specify settings for up to four watermarks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Height<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum height of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Width<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum width of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Opacity<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A percentage that indicates how much you want a watermark to obscure the video in the location where it appears.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sizing<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A value that controls scaling of the watermark. Valid values are: `Fit`, `Stretch`, `ShrinkToFit`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A value that determines how Elastic Transcoder interprets values that you specified for `video_watermarks.horizontal_offset`, `video_watermarks.vertical_offset`, `video_watermarks.max_width`, and `video_watermarks.max_height`. Valid values are `Content` and `Frame`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vertical<wbr>Align<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The vertical position of the watermark unless you specify a nonzero value for `vertical_align`. Valid values are `Top`, `Bottom`, `Center`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vertical<wbr>Offset<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The amount by which you want the vertical position of the watermark to be offset from the position specified by `vertical_align`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">horizontal<wbr>Align<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The horizontal position of the watermark unless you specify a nonzero value for `horzontal_offset`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">horizontal<wbr>Offset<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The amount by which you want the horizontal position of the watermark to be offset from the position specified by `horizontal_align`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique identifier for the settings for one watermark. The value of Id can be up to 40 characters long. You can specify settings for up to four watermarks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Height<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum height of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Width<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum width of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">opacity<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A percentage that indicates how much you want a watermark to obscure the video in the location where it appears.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sizing<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A value that controls scaling of the watermark. Valid values are: `Fit`, `Stretch`, `ShrinkToFit`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A value that determines how Elastic Transcoder interprets values that you specified for `video_watermarks.horizontal_offset`, `video_watermarks.vertical_offset`, `video_watermarks.max_width`, and `video_watermarks.max_height`. Valid values are `Content` and `Frame`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vertical<wbr>Align<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The vertical position of the watermark unless you specify a nonzero value for `vertical_align`. Valid values are `Top`, `Bottom`, `Center`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vertical<wbr>Offset<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The amount by which you want the vertical position of the watermark to be offset from the position specified by `vertical_align`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">horizontal<wbr>Align<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The horizontal position of the watermark unless you specify a nonzero value for `horzontal_offset`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">horizontal<wbr>Offset<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The amount by which you want the horizontal position of the watermark to be offset from the position specified by `horizontal_align`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique identifier for the settings for one watermark. The value of Id can be up to 40 characters long. You can specify settings for up to four watermarks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Height<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum height of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Width<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum width of the watermark.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">opacity<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A percentage that indicates how much you want a watermark to obscure the video in the location where it appears.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sizing<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A value that controls scaling of the watermark. Valid values are: `Fit`, `Stretch`, `ShrinkToFit`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A value that determines how Elastic Transcoder interprets values that you specified for `video_watermarks.horizontal_offset`, `video_watermarks.vertical_offset`, `video_watermarks.max_width`, and `video_watermarks.max_height`. Valid values are `Content` and `Frame`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vertical<wbr>Align<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The vertical position of the watermark unless you specify a nonzero value for `vertical_align`. Valid values are `Top`, `Bottom`, `Center`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vertical<wbr>Offset<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The amount by which you want the vertical position of the watermark to be offset from the position specified by `vertical_align`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








---
title: Experiments
description: Gallery of few advanced examples achieved with DPiCSS with a bit of JavaScript
layout: libdoc_page.liquid
permalink: usage/experiments.html
eleventyNavigation:
    key: Experiments
    order: 70
    parent: Usage
---
<link rel="stylesheet" href="/dist/dpicss.css">

## AVIF is the new GIF

DPiCSS is an interesting option when you have small pieces of videos an you don't need audio. Using <abbr title="AV1 Image File Format">AVIF</abbr> image format is a relevant option to get high quality short animated sequences with fewer kilobytes. With this modern format, it becomes possible to display high definition media without losing page performance, bandwidth and user patience. This page uses some examples of still and animated AVIF files in combination with DPiCSS.

The following example uses DPiCSS integrated into [Eleventy LibDoc](https://eleventy-libdoc.netlify.app):

<div class="pos-relative z-1 mt-7"
    style="padding: 0">
    <details id="mmfr-opening"
        data-dpicss="play pause box_shadow button_shadow">
        <summary>
            <picture>
                <img src="https://assets.olivewhite.com/dpicss/mmfrteaser-opening_360-thumbnail.avif"
                    srcset="https://assets.olivewhite.com/dpicss/mmfrteaser-opening_720-thumbnail.avif 2x"
                    alt="The thumbnail"
                    width="1728"
                    height="720"
                    loading="lazy"
                    eleventy:ignore>
            </picture>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/mmfrteaser-opening_360.avif"
                srcset="https://assets.olivewhite.com/dpicss/mmfrteaser-opening_720.avif 2x"
                alt="Large sized image"
                width="1728"
                height="720"
                loading="lazy"
                eleventy:ignore>
        </picture>
    </details>
</div>

```html
<details data-dpicss="play pause box_shadow button_shadow">
    <summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/mmfrteaser-opening_360-thumbnail.avif"
                srcset="https://assets.olivewhite.com/dpicss/mmfrteaser-opening_720-thumbnail.avif 2x"
                alt="The thumbnail"
                width="1728"
                height="720"
                loading="lazy">
        </picture>
    </summary>
    <picture>
        <img src="https://assets.olivewhite.com/dpicss/mmfrteaser-opening_360.avif"
            srcset="https://assets.olivewhite.com/dpicss/mmfrteaser-opening_720.avif 2x"
            alt="Large sized image"
            width="1728"
            height="720"
            loading="lazy">
    </picture>
</details>
```

* AVIF thumbnail 22KB for pixel density > 1 - 1728x720px definition.
* AVIF thumbnail 7KB for pixel density 1x - 864x360px definition.
* 9s animated AVIF file 1.1MB for pixel density > 1 - 1728x720px.
* 9s animated AVIF file 1.1MB for pixel density x1 - 864x360px.
* ffmpeg command for animated file: 
    ```
    ffmpeg -i mmfrteaser_nb_opening.mkv -ss 8 -to 17 \
        -vf "fps=24000/1001,scale=-2:720:flags=lanczos,zscale=t=linear:npl=100,format=gbrpf32le,zscale=p=bt709,tonemap=hable:desat=0,zscale=t=bt709:m=bt709:r=tv,format=yuv420p,eq=saturation=1.4:brightness=0.1" \
        -c:v libsvtav1 -crf 50 -preset 6 -g 15 -keyint_min 15 -an \
        mmfrteaser-opening_720.avif
    ```
    * There are much parameters on `-vf` because video source is <abbr title="High Dynamic Range">HDR</abbr>.
    * `-g` and `-keyint_min` are set to force key frames, otherwise some browser like Safari may lag.
* ffmpeg command for thumbnail file:
    ```
    ffmpeg -i mmfrteaser_nb_opening.mkv -ss 8 \
        -vf "fps=24000/1001,scale=-2:720:flags=lanczos,zscale=t=linear:npl=100,format=gbrpf32le,zscale=p=bt709,tonemap=hable:desat=0,zscale=t=bt709:m=bt709:r=tv,format=yuv420p,eq=saturation=1.4:brightness=0.1" \
        -frames:v 1 -c:v libaom-av1 -crf 40 -cpu-used 8 \
        mmfrteaser-opening_720-thumbnail.avif
    ```

## Play once and still

The following example uses an AVIF encoded with `-loop 1` that play only once. A bit of JavaScript is added only to add a class name on the large sized image loaded. This allows to block the natural behavior of the details summary tag when you want to keep the last frame visible. A reload button allows to reset the scene.

{% sandbox 'Play once and still' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<main>
    <details id="foo"
        data-dpicss="play button_shadow">
        <summary>
            <picture>
                <img src="https://assets.olivewhite.com/dpicss/mmfrteaser-blower-thumbnail.avif"
                    alt="The thumbnail"
                    width="2592"
                    height="1080"
                    loading="lazy">
            </picture>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/mmfrteaser-blower.avif"
                alt="Large sized image"
                width="2592"
                height="1080"
                loading="lazy"
                onload="this.classList.add('loaded')">
        </picture>
    </details>
    <button id="reset" onclick="window.location.reload(true);">Reload</button>
</main>
<style>
    body {
        font-family: -apple-system, BlinkMacSystemFont, avenir next, avenir, segoe ui, helvetica neue, Adwaita Sans, Cantarell, Ubuntu, roboto, noto, helvetica, arial, sans-serif;
        margin: 0; padding: 0;
    }
    #foo {
        /* START DEMO */
        position: fixed;
        top: 50%;
        left: 50%;
        transform: translateX(-50%) translateY(-50%);
        width: 100%;
        /* END DEMO */
        /* START DPiCSS */
        --play-text: 'Ignite';
        --padding: 0px;
        --border-radius: 0px;
        --primary-color: #c17744;
        /* END DPiCSS */
    }
    #foo img {
        height: 100vh;
    }
    #foo:has(img.loaded) summary {
        pointer-events: none;
    }
    #reset {
        display: none;
        cursor: pointer;
        position: fixed;
        bottom: 1em;
        left: 1em;
        background-color: #FFFFFF22;
        border: none;
        border-radius: 4px;
        padding: 0.5em 1em;
        color: #EEE;
        font-size: 14px;
    }
    #foo:has(img.loaded) ~ #reset {
        display: inherit;
    }
</style>
{% endsandbox %}


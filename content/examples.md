---
title: Examples
description: Gallery of examples with parameters, images formats and customizations
layout: libdoc_page.liquid
permalink: examples.html
eleventyNavigation:
    key: Examples
    order: 50
---
## Unmask an image

DPICSS can be used as an <abbr title="User Interface">UI</abbr> to unmask an image.

{% sandbox 'Unmask an image' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="play pause box_shadow button_shadow"
        style="
        --play-text: 'View';
        --pause-text: 'Hide';
        --padding: 0em;
        --border-radius: 0em;
        --text-align: center">
        <summary>
            <picture>
                <img src="/assets/img/tn_le-plan-de-la-laie.avif"
                    alt="The thumbnail"
                    width="2560"
                    height="1706"
                    loading="lazy">
            </picture>
            <span>View higher definition - Click to discover</span>
        </summary>
        <picture>
            <img src="/assets/img/le-plan-de-la-laie.avif"
                alt="Large sized image"
                width="2560"
                height="1706"
                loading="lazy">
        </picture>
    </details>
</main>
{% endsandbox %}

## Play once

Use a bit of JavaScript to play once an AVIF.

{% sandbox 'Play once' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<main>
    <details id="foo"
        data-dpicss="play button_shadow">
        <summary>
            <picture>
                <img src="/assets/img/tn_mmfrteaser_nb_4.avif"
                    alt="The thumbnail"
                    width="2592"
                    height="1080"
                    loading="lazy">
            </picture>
        </summary>
        <picture>
            <img src="/assets/img/mmfrteaser_nb_4.avif"
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
        /* START DPICSS */
        --play-text: 'Ignite';
        --padding: 0px;
        --border-radius: 0px;
        --primary-color: #c17744;
        /* END DPICSS */
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

## Play once 2

Use a bit of JavaScript to play once an AVIF.

{% sandbox 'Play once 2' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<main>
    <details id="foo"
        data-dpicss="play button_shadow">
        <summary>
            <picture>
                <img src="/assets/img/tn_mmfrteaser_nb_opening.avif"
                    alt="The thumbnail"
                    width="2592"
                    height="1080"
                    loading="lazy">
            </picture>
        </summary>
        <picture>
            <img src="/assets/img/mmfrteaser_nb_opening.avif"
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
        /* START DPICSS */
        --play-text: 'Ignite';
        --padding: 0px;
        --border-radius: 0px;
        --primary-color: #38342a;
        --shadow-color: black;
        /* END DPICSS */
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

## Display a GIF

Use DPICSS to simply display a GIF on click on a thumbnail.

{% sandbox 'Display a GIF' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="play pause box_shadow button_shadow"
        style="
        --play-text: 'GIF';
        --pause-text: 'Stop';
        --primary-color: #261b2c;
        --padding: 3cqi;
        --border-radius: 3cqi;">
        <summary>
            <picture>
                <img src="/assets/img/tn_crazy-rabbit.webp"
                    alt="The thumbnail"
                    width="640"
                    height="360"
                    loading="lazy">
            </picture>
            <span>Click to play or pause the animated GIF</span>
        </summary>
        <picture>
            <img src="/assets/img/crazy-rabbit.gif"
                alt="Large sized image"
                width="640"
                height="360"
                loading="lazy">
        </picture>
    </details>
</main>
{% endsandbox %}

## Display a WEBP

Use DPICSS to simply display an animated WEBP on click on a thumbnail.

{% sandbox 'Display a WEBP' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="play pause box_shadow"
        style="
        --play-text: 'Start!';
        --pause-text: 'Stop!';
        --primary-color: #235b9a;
        --padding: 16px;
        --shadow-opacity: 0.7;
        --shadow-color: #235b9a;
        --border-radius: 1000px">
        <summary title="Click to play or pause animated WEBP">
            <picture>
                <img src="/assets/img/tn_muppet.webp"
                    alt="The thumbnail"
                    width="480"
                    height="360"
                    loading="lazy">
            </picture>
        </summary>
        <picture>
            <img src="/assets/img/muppet.webp"
                alt="Large sized animated image"
                width="480"
                height="360"
                loading="lazy">
        </picture>
    </details>
</main>
{% endsandbox %}


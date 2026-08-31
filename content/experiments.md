---
title: Experiments
description: Gallery of few advanced examples achieved with DPICSS with a bit of JavaScript
layout: libdoc_page.liquid
permalink: usage/experiments.html
eleventyNavigation:
    key: Experiments
    order: 60
    parent: Usage
---
## Play once

Use a bit of JavaScript to play once an AVIF.

{% sandbox 'Play once' %}
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
                <img src="https://assets.olivewhite.com/dpicss/mmfrteaser-opening-thumbnail.avif"
                    alt="The thumbnail"
                    width="2592"
                    height="1080"
                    loading="lazy">
            </picture>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/mmfrteaser-opening.avif"
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

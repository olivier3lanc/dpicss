---
title: DPICSS
description: Details Player for Image with CSS. A tiny CSS library to display animated or higher definition images on click
layout: libdoc_page.liquid
permalink: index.html
---
{% sandbox %}
<link rel="stylesheet" href="/assets/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main style="display: flex; align-items: center; justify-content: center; height: 100vh; padding: 32px">
    <details data-dpicss="play pause box_shadow button_shadow">
        <summary title="Click to toggle">
            <picture>
                <img src="https://assets.olivewhite.com/sandboxes/details-css-image-player/albertville-timelapse-thumbnail.avif"
                    alt="Panoramique aérien des débuts des travaux"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                <code>avif</code> 
                Example with an AVIF file
            </span>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/sandboxes/details-css-image-player/albertville-timelapse-animated.avif"
                alt="Roselend Nightlapse thumbnail"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
    </details>
<main>
{% endsandbox %}

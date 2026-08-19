---
title: Parameters
description: Just add some keywords on DPICSS attribute to fine-tune your experience
layout: libdoc_page.liquid
permalink: parameters.html
eleventyNavigation:
    key: Parameters
    order: 20
---

| `data-dpicss` attribute contains | Description |
|--|--|
| `play`| Displays "play" button on thumbnail |
| `play_hover`| Displays a "Play" button on thumbnail only when user hovers the summary |
| `pause`| Displays a "Pause" button on large sized image only when user hovers the summary |
| `box_shadow`| Displays a box shadow of the entire details element |
| `button_shadow`| Displays a shadow around play and pause buttons |
| `invert`| Swaps foreground and background colors |


## Play button

Adding `play` on the `data-dpicss` attribute displays a "Play" button on thumbnail.

{% sandbox %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="play">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Simple "Play" button parameter
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
    </details>
</main>
{% endsandbox %}

## Play button on hover

Adding `play_hover` on the `data-dpicss` attribute displays a "Play" button on thumbnail only when user hovers the summary. For ergonomics reasons, this feature is only for desktop, play button always displays on touch devices.

{% sandbox %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="play_hover">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Simple "Play" button on hover parameter
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p>For ergonomics reasons, this feature is only for desktop, play button always displays on touch devices.</p>
    </details>
</main>
{% endsandbox %}

## Pause button

Adding `pause` on the `data-dpicss` attribute displays a "Pause" button on hover when playing large image. For ergonomics reasons, this feature is only for desktop, pause button is always hidden on touch devices.

{% sandbox %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="pause">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Simple "Pause" button parameter
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p>For ergonomics reasons, this feature is only for desktop, pause button is always hidden on touch devices.</p>
    </details>
</main>
{% endsandbox %}

## Box shadow

Adding `box_shadow` on the `data-dpicss` attribute displays a box shadow of the entire details element.

{% sandbox %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="box_shadow">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Box shadow parameter
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
    </details>
</main>
{% endsandbox %}

## Button shadow parameter

Adding `button_shadow` on the `data-dpicss` attribute displays a shadow around play and pause buttons. Note that at least one parameter like `play`, `play_hover` or `pause` must be set to make this feature visible.

{% sandbox %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="play pause button_shadow">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Button shadow parameter
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
    </details>
</main>
{% endsandbox %}

## Invert parameter

Adding `invert` on the `data-dpicss` attribute swaps/inverts foreground and background colors.

{% sandbox %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="invert play pause button_shadow">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Invert parameter
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
    </details>
</main>
{% endsandbox %}

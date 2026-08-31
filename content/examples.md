---
title: Examples
description: Gallery of examples with parameters, images formats and customizations
layout: libdoc_page.liquid
permalink: usage/examples.html
eleventyNavigation:
    key: Examples
    order: 50
    parent: Usage
---
## AVIF Rocks

[AV1 image format](https://fr.wikipedia.org/wiki/AVIF) works perfectly with DPICSS.

{% sandbox 'AVIF Rocks' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main class="alt1">
    <details data-dpicss="play pause box_shadow button_shadow"
        style="
        --play-text: 'What a lovely day!';
        --pause-text: 'Stop';
        --primary-color: #873003;
        --padding: 2px;
        --border-radius: 6px;
        --text-align: center;
        --shadow-color: var(--primary-color)">
        <summary>
            <picture>
                <img src="https://assets.olivewhite.com/dpicss/what-a-lovely-day-thumbnail.avif"
                    alt="The thumbnail"
                    width="2592"
                    height="1080"
                    loading="lazy">
            </picture>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/what-a-lovely-day.avif"
                alt="Large sized image"
                width="2592"
                height="1080"
                loading="lazy">
        </picture>
        <p>
            <a  href="https://www.warnerbros.com/movies/mad-max-fury-road"
                target="_blank"
                style="color: var(--primary-color-contrast)">
                &copy; Warner Bros - Mad Max Fury Road
            </a>
        </p>
    </details>
</main>
{% endsandbox %}

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
                <img src="https://assets.olivewhite.com/dpicss/le-plan-de-la-laie-thumbnail.avif"
                    alt="The thumbnail"
                    width="2560"
                    height="1706"
                    loading="lazy">
            </picture>
            <span>View higher definition - Click to discover</span>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/le-plan-de-la-laie.avif"
                alt="Large sized image"
                width="2560"
                height="1706"
                loading="lazy">
        </picture>
    </details>
</main>
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
                <img src="https://assets.olivewhite.com/dpicss/crazy-rabbit-thumbnail.webp"
                    alt="The thumbnail"
                    width="640"
                    height="360"
                    loading="lazy">
            </picture>
            <span>Click to play or pause the animated GIF</span>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/crazy-rabbit.gif"
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
                <img src="https://assets.olivewhite.com/dpicss/muppet-thumbnail.webp"
                    alt="The thumbnail"
                    width="480"
                    height="360"
                    loading="lazy">
            </picture>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/muppet.webp"
                alt="Large sized animated image"
                width="480"
                height="360"
                loading="lazy">
        </picture>
    </details>
</main>
{% endsandbox %}


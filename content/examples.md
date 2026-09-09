---
title: Examples
description: Gallery of examples with combination of DPiCSS parameters and images formats
layout: libdoc_page.liquid
permalink: usage/examples.html
eleventyNavigation:
    key: Examples
    order: 50
    parent: Usage
---
## Display an animated AVIF

[AV1 image format](https://fr.wikipedia.org/wiki/AVIF) works perfectly with DPiCSS.

{% sandbox 'Display an animated AVIF' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="play pause box_shadow button_shadow">
        <summary title="Click to toggle play pause">
            <picture>
                <img src="https://assets.olivewhite.com/dpicss/kitfly_a-thumbnail.avif"
                    alt="The thumbnail"
                    width="860"
                    height="568"
                    loading="lazy">
            </picture>
            <span>Click to toggle PLAY PAUSE the animated AVIF</span>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/kitfly_a.avif"
                alt="Large sized image"
                width="860"
                height="568"
                loading="lazy">
        </picture>
        <p>
            &copy; 
            <a  href="https://brand.mozilla.com/d/5UkPdpbtt8LS/visual-elements#/-/mascot"
                target="_blank"
                style="color: var(--primary-color-contrast)">
                Kit by Mozilla
            </a>
        </p>
    </details>
</main>
{% endsandbox %}

## Add content to details

DPiCSS uses `details` tag as primary holder, you can off course add any content after or before the `picture` tag as follows. Into this example, the animated AVIF image file is encoded with `-loop 1`, this means that it keep the last frame as still image once played.

{% sandbox 'Add content to details' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="play box_shadow">
        <summary>
            <picture>
                <img src="https://assets.olivewhite.com/dpicss/severance-elevator-thumbnail.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="536"
                    loading="lazy">
            </picture>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/severance-elevator.avif"
                alt="Large sized animated image"
                width="1280"
                height="536"
                loading="lazy">
        </picture>
        <p>
            <small>In “<a  href="https://www.apple.com/tv-pr/originals/severance/"
                target="_blank"
                title="Open Apple TV Severance official page in a new tab"
                style="color: var(--primary-color-contrast)">Severance</a>,” Mark Scout (Adam Scott) leads a team at Lumon Industries, whose employees have undergone a severance procedure that surgically divides their memories between their work and personal lives. This daring experiment in “work-life balance” is called into question as Mark finds himself at the center of an unraveling mystery that will force him to confront the true nature of his work … and of himself. In season two, Mark and his friends learn the dire consequences of trifling with the severance barrier, leading them further down a path of woe.</small>
        </p>
        <div>
            <button type="button"
                onclick="window.location.reload(true)"
                title="Reload the current iframe to retart experience">
                Reload
            </button>
        </div>
    </details>
</main>
{% endsandbox %}

## Responsiveness

DPiCSS is just a CSS library based on HTML5, `picture` tag manages perfectly the responsiveness just like the following example: 

{% sandbox 'Responsiveness' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="play pause box_shadow button_shadow">
        <summary>
            <picture>
                <source media="(min-width:700px)" srcset="https://assets.olivewhite.com/dpicss/albertville-timelapse-thumbnail.avif">
                <img src="https://assets.olivewhite.com/dpicss/albertville-timelapse_mini-thumbnail.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Try to resize width to 700px or higher to view responsiveness
            </span>
        </summary>
        <picture>
            <source media="(min-width:700px)" srcset="https://assets.olivewhite.com/dpicss/albertville-timelapse.avif">
            <img src="https://assets.olivewhite.com/dpicss/albertville-timelapse_mini.avif"
                alt="Large sized image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
    </details>
</main>
{% endsandbox %}

## Reveal an image

DPiCSS can be used as an <abbr title="User Interface">UI</abbr> to unmask an image.

{% sandbox 'Reveal an image' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="play pause box_shadow button_shadow"
        style="
        --play-text: 'View';
        --pause-text: 'Hide';">
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

Use DPiCSS to simply display a GIF on click on a thumbnail.

{% sandbox 'Display a GIF' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="play pause box_shadow button_shadow">
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

Use DPiCSS to simply display an animated WEBP on click on a thumbnail.

{% sandbox 'Display a WEBP' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="play pause box_shadow">
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


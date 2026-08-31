---
title: Usage
description: How to use DPICSS with some examples
layout: libdoc_page.liquid
permalink: usage.html
eleventyNavigation:
    key: Usage
    order: 10
---
DPICSS works with [details](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/details), [picture](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/picture) and [image](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/img). Since `alt` attribute is entered, details summary accessibility is fulfilled, but an optional `span` can be added as child of `summary` tag to display HTML content under the thumbnail.

Here is the associated markup to use with DPICSS:

```html
<details data-dpicss="<OPTIONAL_LIST_OF_KEYWORDS_PARAMETERS>">
    <summary title="<OPTIONAL_TOOLTIP_TEXT>">
        <picture>
            <img src="<THUMBNAIL_IMAGE_URL>"
                alt="<THUMBNAIL_ALTERNATE_TEXT>"
                width="<NATURAL_WIDTH_OF_BOTH_IMAGES>"
                height="<NATURAL_HEIGHT_OF_BOTH_IMAGES>"
                loading="lazy">
        </picture>
        <!-- Optional <span>, can be removed if unnecessary-->
        <span>
            Optional summary text into a span tag
        </span>
    </summary>
    <picture>
        <img src="<LARGE_SIZED_IMAGE_URL>"
            alt="<LARGE_SIZED_IMAGE_ALTERNATE_TEXT>"
            width="<NATURAL_WIDTH_OF_BOTH_IMAGES>"
            height="<NATURAL_WIDTH_OF_BOTH_IMAGES>"
            loading="lazy">
    </picture>
    <!-- Optional below - Any content as "details" tag can display -->
</details>
```
*   `<OPTIONAL_LIST_OF_KEYWORDS_PARAMETERS>`<br>
    The keyword based [parameters of DPICSS](/content/parameters.md)
*   `<OPTIONAL_TOOLTIP_TEXT>`<br>
    May be useful if no optional `span` is set into the `summary` tag, even if `<img alt="..."` attribute is there to describe your stuff. Also consider using `aria-label`.
*   `<THUMBNAIL_IMAGE_URL>`<br>
    The <abbr title="Uniform Resource Locator">URL</abbr> of the thumbnail.
*   `<THUMBNAIL_ALTERNATE_TEXT>`<br>
    The alternate text of the thumbnail. Enter a proper [alt attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/img#alt) that describes image and action of the thumbnail.
*   `<NATURAL_WIDTH_OF_BOTH_IMAGES>`<br>
    The natural width of both images. *It is highly recommended for the thumbnail to have the same width as the large sized image*, otherwise aspect ratio issues may occur.
*   `<NATURAL_HEIGHT_OF_BOTH_IMAGES>`<br>
    The natural height of both images. *It is highly recommended for the thumbnail to have the same height as the large sized image*, otherwise aspect ratio issues may occur.
*   `<LARGE_SIZED_IMAGE_URL>`<br>
    The <abbr title="Uniform Resource Locator">URL</abbr> of the large sized image.
*   `<LARGE_SIZED_IMAGE_ALTERNATE_TEXT>`<br>
    The alternate text of the large sized image. Enter a proper [alt attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/img#alt) that describes the large sized image.

## Simple example

Here is a fully fonctionnal minimalistic example with a still <abbr title="AV1 Image File Format">AVIF</abbr> file thumbnail and an animated AVIF.

{% sandbox 'Minimalist example' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<main>
    <details data-dpicss="">
        <summary>
            <picture>
                <img src="https://assets.olivewhite.com/dpicss/albertville-timelapse-thumbnail.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
    </details>
</main>
{% endsandbox %}

## Interoperability

Since DPICSS uses CSS and HTML5 tags, it may interfere with others librairies or frameworks. The following sandboxes includes most common CSS libraries to check DPICSS renders properly across every framework or library. Feel free to [suggest other libraries](https://github.com/olivier3lanc/dpicss/issues) or [report issues](https://github.com/olivier3lanc/dpicss/issues).

### With Bootstrap

Example of a page with [Bootstrap](https://getbootstrap.com) and DPICSS.

{% sandbox 'With Bootstrap' %}
<link href="/assets/bootstrap.5.3.8.min.css"" rel="stylesheet">
<link href="/assets/demo.css" rel="stylesheet">
<link href="/dist/dpicss.css" rel="stylesheet">
<main>
    <details data-dpicss="play pause box_shadow">
        <summary>
            <picture>
                <img src="https://assets.olivewhite.com/dpicss/albertville-timelapse-thumbnail.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>DPICSS with Bootstrap</span>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p>Details is opened. Lorem ipsum Charizard learned Scratch.</p>
    </details>
</main>
{% endsandbox %}

### With Tailwind

Example of a page with [Tailwind CSS](https://tailwindcss.com/) and DPICSS.

{% sandbox 'With Tailwind' %}
<link href="/assets/tailwind.4.3.0.min.css"" rel="stylesheet">
<link href="/assets/demo.css" rel="stylesheet">
<link href="/dist/dpicss.css" rel="stylesheet">
<main>
    <details data-dpicss="play pause box_shadow">
        <summary>
            <picture>
                <img src="https://assets.olivewhite.com/dpicss/albertville-timelapse-thumbnail.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>DPICSS with Tailwind</span>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p>Details is opened. Lorem ipsum Charizard learned Scratch.</p>
    </details>
</main>
{% endsandbox %}

### With Reset CSS

Example of a page with [Eric A. Meyer Reset CSS](https://meyerweb.com/eric/tools/css/reset/) and DPICSS.

{% sandbox 'Eric A. Meyer Reset CSS' %}
<link href="/assets/meyerweb.reset.2.css" rel="stylesheet">
<link href="/assets/demo.css" rel="stylesheet">
<link href="/dist/dpicss.css" rel="stylesheet">

<main>
    <details data-dpicss="play pause box_shadow">
        <summary>
            <picture>
                <img src="https://assets.olivewhite.com/dpicss/albertville-timelapse-thumbnail.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>DPICSS with Reset CSS into its own @layer</span>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p>Details is opened. Lorem ipsum Charizard learned Scratch.</p>
    </details>
</main>
{% endsandbox %}

### Normalize CSS

Example of a page with [Normalize CSS](https://necolas.github.io/normalize.css/) and DPICSS.

{% sandbox 'Normalize CSS' %}
<link href="/assets/normalize.8.0.1.css" rel="stylesheet">
<link href="/assets/demo.css" rel="stylesheet">
<link href="/dist/dpicss.css" rel="stylesheet">
<main>
    <details data-dpicss="play pause box_shadow">
        <summary>
            <picture>
                <img src="https://assets.olivewhite.com/dpicss/albertville-timelapse-thumbnail.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>DPICSS with Normalize CSS</span>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p>Details is opened. Lorem ipsum Charizard learned Scratch.</p>
    </details>
</main>
{% endsandbox %}

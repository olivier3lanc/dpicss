---
title: DPICSS
description: Details Player for Image with CSS. A tiny CSS library to display animated or higher definition images on click
layout: libdoc_page.liquid
permalink: index.html
---
**The main idea behind DPICSS is to beautifully display large-sized images or animated images only on user demand without bloating and reducing page performances.**

<div class="mt-8 mb-8">
    <details data-dpicss="play pause box_shadow">
        <summary>
            <picture>
                <img src="https://assets.olivewhite.com/dpicss/poppy-cinemagraph-thumbnail.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy"
                    eleventy:ignore>
            </picture>
            <span>Poppy cinemagraph</span>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/poppy-cinemagraph.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy"
                eleventy:ignore>
        </picture>
        <p>
            <small>
                Here is a simple usage example of DPICSS
                &copy; <a href="https://www.olivewhite.com">Olive White Photographies</a>
            </small>
        </p>
    </details>
</div>

DPICSS achieves this combining modern native HTML5 and CSS features:

* **Uses fully semantic HTML5** with `<details>`, `<picture>` and `<img>` tags to display an animated or higher definition image. 
* As a details tag HTML5 element, DPICSS can [display extra summary content and toggled content](/content/examples.md#add-content-to-details).
* Uses native **lazy loading** of `<img>` tag that allows to download the thumbnail only when it is into the viewport and the larger asset only when its thumbnail is clicked.
* **Responsive type scale**: [Primary font size](/content/customization.md#custom-primary-size) of every DPICSS instance adjusts automatically based on its container.
* **Automatic color contrast**: Set your preferred primary color and DPICSS [automatically adjusts the proper contrasted black or white color](/content/customization.md#custom-primary-color).
* **Works with any animated or still image**.
* **Integrates seamlessly into existing pages**.
* **Works without JavaScript**, works even if JavaScript is disabled.
* **Main [parameters](/content/parameters.md) are customizable with few CSS variables**.
* **Displays a loader while thumbnail and large sized image are being loaded**.
* **Supports light and dark color scheme preferences**.
* DPICSS is [easy to use](/content/usage.md) and has a nice range of [parameters](/content/parameters.md) and [customizations](/content/customization.md). You can [view some examples](/content/examples.md) and [the gallery](/content/gallery.md).

## Installation

Just include the CSS file [dpicss.css](./dist/dpicss.css) into the page.

CDN:

```plain
https://cdn.jsdelivr.net/gh/olivier3lanc/dpicss/dist/dpicss.css
```

npm:

```bash
npm install dpicss
```

Local:

```bash
npm install
npx @11ty/eleventy --serve
```

Now you can go to [usage](/content/usage.md).

## How it works

The following demo logs what happens during the multiple steps to the final display of the large sized image:

<link rel="stylesheet" href="/dist/dpicss.css">
<div>
    <details data-dpicss="play pause box_shadow button_shadow">
        <summary onclick="display(`🕙 Loading large sized image`);this.onclick = null">
            <picture>
                <img src="https://assets.olivewhite.com/dpicss/albertville-timelapse-thumbnail.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy"
                    onload="display(`✅ Thumbnail loaded, waiting click to load large sized image`)"
                    eleventy:ignore>
            </picture>
            <span>
                A simple log to monitor what happens:<br>
                <code id="test_console">🕙 Waiting for thumbnail into the viewport<br></code>
            </span>
        </summary>
        <picture>
            <img src="https://assets.olivewhite.com/dpicss/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy"
                onload="display(`✅ Large sized image loaded`)"
                eleventy:ignore>
        </picture>
    </details>
    <script>
        const elTestConsole = document.querySelector('#test_console');
        const display = function(string) {
            if (elTestConsole) { elTestConsole.innerHTML += `${string}<br>`; }
        }
    </script>
</div>


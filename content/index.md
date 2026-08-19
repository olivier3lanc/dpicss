---
title: DPICSS
description: Details Player for Image with CSS. A tiny CSS library to display animated or higher definition images on click
layout: libdoc_page.liquid
permalink: index.html
---
**The main idea behind DPICSS is to beautifully display large-sized images only on user demand without reducing page performances with a minimum of code.**

<div>
    <details data-dpicss="play pause box_shadow">
        <summary>
            <picture>
                <img src="/assets/img/tn_nightlapse-roselend.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy"
                    eleventy:ignore>
            </picture>
        </summary>
        <picture>
            <img src="/assets/img/nightlapse-roselend.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy"
                eleventy:ignore>
        </picture>
    </details>
</div>

DPICSS achieves this combining modern native HTML5 and CSS features:

* Uses **native HTML5** `<details>`, `<picture>` and `<img>` tags to display an animated or higher definition image. 
* As a details tag HTML5 element, DPICSS can display extra summary content and toggled content.
* Uses native **lazy loading** of `<img>` tag that allows to download the thumbnail only when it is into the viewport and the larger asset only when its thumbnail is clicked.
* **Works with any animated or still image**.
* **Integrates seamlessly into existing pages**.
* **Works without JavaScript**, works even if JavaScript is disabled.
* **Fully customizable with few CSS variables**.
* **Smooth transitions** between states.
* **Displays a loader while thumbnail and large sized image are being loaded**.
* **Supports light and dark color scheme preferences**.

## Installation

Just include the CSS file [dpicss.css](./dist/dpicss.css) into the page.

CDN:

```plain
https://cdn.jsdelivr.net/gh/olivier3lanc/dpicss/dist/dpicss.css
```

Local:

```bash
npm install
npx @11ty/eleventy --serve
```

## How it works

The following demo logs what happens during the multiple steps to the final display of the large sized image:

<link rel="stylesheet" href="/dist/dpicss.css">
<div>
    <details data-dpicss="play pause box_shadow button_shadow">
        <summary onclick="display(`🕙 Loading large sized image`);this.onclick = null">
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
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
            <img src="/assets/img/albertville-timelapse.avif"
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


---
title: Customization
description: DPICSS comes with some CSS variables that make it easy to fine tune
layout: libdoc_page.liquid
permalink: customization.html
eleventyNavigation:
    key: Customization
    order: 30
---

| CSS variable | Default value | Description |
|--|--|--|
| `--primary-color`| `white` | Primary color from which every other color is set |
| `--primary-size`| `clamp(12px, 3cqi, 16px)` | The primary size defines text size. By default in DPICSS, primary size is used to set font size and paddings|
| `--font-family`| `inherit` | Defines the font family |
| `--text-align`| `left` | Defines the default text alignment for the summary text |
| `--padding`| `calc(0.5 * var(--primary-size))` | Defines the padding of the box and the images. By default, calculated from primary size |
| `--border-radius`| `calc(var(--primary-size) * 0.7)` | Defines the border radius of the box and the images. By default, calculated from primary size |
| `--button-border-radius`| `1000px` | Defines the border radius of the play and pause buttons  |
| `--shadow-radius`| `3em` | Defines the box shadow radius |
| `--shadow-opacity`| `0.5` | Defines the box shadow opacity |
| `--shadow-color`| `oklch(from var(--primary-color) round(1.21 - L) 0 0)` | Defines the box shadow opacity |
| `--play-text`| `Play` | Text to display on thumbnail |
| `--pause-text`| `Pause` | Text to display on large sized image |
| `--transition-duration`| `500ms` | Defines transition duration on properties changes |

## Global

To customize every instance of DPICSS, just replace one or more CSS variables replacing the defaults.

```css
@layer dpicss {
    details[data-dpicss] {
        /* Primary color from which every other color is set */
        --primary-color:        white;
        /* The primary size defines text size. By default in DPICSS, primary size is used to set font size and paddings.  */
        --primary-size:         clamp(12px, 3cqi, 16px);
        /* Defines the font family */
        --font-family:          inherit;
        /* Defines the default text alignment for the summary text */
        --text-align:           left;
        /* Defines the padding of the box and the images. By default, calculated from primary size */
        --padding:              calc(0.5 * var(--primary-size));
        /* Defines the border radius of the box and the images. By default, calculated from primary size */
        --border-radius:        calc(var(--primary-size) * 0.7);
        /* Defines the border radius of the play and pause buttons */
        --button-border-radius: 1000px;
        /* Defines the box shadow radius */
        --shadow-radius:        3em; 
        /* Defines the box shadow opacity */
        --shadow-opacity:       0.5;
        /* Defines the box shadow color. By default, calculated from the primary color */
        --shadow-color:         oklch(from var(--primary-color) round(1.21 - L) 0 0);
        /* Text to display on thumbnail */
        --play-text:            'Play';
        /* Text to display when large sized image is running */
        --pause-text:           'Pause';
        /* Defines transition duration on properties changes */
        --transition-duration:  500ms;
    }
}
```

For example, to replace primary color:

```css
details[data-dpicss] {
    --primary-color: #242d11;
}
```
## Custom primary color

{% sandbox 'Custom primary color' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<style>
    details[data-dpicss] {
        --primary-color: #242d11;
    }
</style>
<main>
    <details data-dpicss="">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Custom global primary color
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
    <details data-dpicss=""
        style="--primary-color: #b06630">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                CSS variable override on element
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

## Custom primary size

{% sandbox 'Custom primary size' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<style>
    details[data-dpicss] {
        --primary-size: 5cqi;
    }
</style>
<main>
    <details data-dpicss="">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Custom global primary size 5cqi
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
    <details data-dpicss=""
        style="--primary-size: 12px">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                CSS variable 12px on DPICSS details element
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

## Custom text align

{% sandbox 'Custom text align' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<style>
    details[data-dpicss] {
        --text-align: center;
    }
</style>
<main>
    <details data-dpicss="">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Custom global text aligned center
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p><code>--text-align</code> does affect summary span only</p>
    </details>
    <details data-dpicss=""
        style="--text-align: right">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Text align right on DPICSS details element
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p><code>--text-align</code> does affect summary span only</p>
    </details>
</main>
{% endsandbox %}

## Custom padding

{% sandbox 'Custom padding' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<style>
    details[data-dpicss] {
        --padding: 3px;
    }
</style>
<main>
    <details data-dpicss="">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Custom global padding 3px
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p><code>--padding: 3px</code></p>
    </details>
    <details data-dpicss=""
        style="--padding: 3vw">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Padding 3vw on DPICSS details element
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p><code>--padding: 3vw</code></p>
    </details>
</main>
{% endsandbox %}

## Custom border radius

{% sandbox 'Custom border radius' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<style>
    details[data-dpicss] {
        --border-radius: 0px;
    }
</style>
<main>
    <details data-dpicss="">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Custom global border radius 0px
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p><code>--border-radius: 0px</code></p>
    </details>
    <details data-dpicss=""
        style="--border-radius: 10vw; --text-align: center">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Border radius 10vw on DPICSS details element
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

## Custom button border radius

{% sandbox 'Custom button border radius' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<style>
    details[data-dpicss] {
        --button-border-radius: 0px;
    }
</style>
<main>
    <details data-dpicss="play pause">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Custom global button border radius 0px
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p><code>--button-border-radius: 0px</code></p>
    </details>
    <details data-dpicss="play pause"
        style="--button-border-radius: 0.5em">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Button border radius 0.5em on DPICSS details element
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p><code>--button-border-radius: 0.5em</code></p>
    </details>
</main>
{% endsandbox %}

## Custom shadow radius

{% sandbox 'Custom shadow radius' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<style>
    details[data-dpicss] {
        --shadow-radius: 32px;
    }
</style>
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
                Custom global shadow radius 32px
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p><code>--shadow-radius: 32px</code></p>
    </details>
    <details data-dpicss="box_shadow"
        style="--shadow-radius: 0.5em">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Shadow radius 0.5em on DPICSS details element
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p><code>--shadow-radius: 0.5em</code></p>
    </details>
</main>
{% endsandbox %}

## Custom shadow opacity

{% sandbox 'Custom shadow opacity' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<style>
    details[data-dpicss] {
        --shadow-opacity: 0.8;
    }
</style>
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
                Custom global shadow opacity 0.8
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p><code>--shadow-opacity: 0.8</code></p>
    </details>
    <details data-dpicss="box_shadow"
        style="--shadow-opacity: 0.2">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Shadow opacity 0.2 on DPICSS details element
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p><code>--shadow-opacity: 0.2</code></p>
    </details>
</main>
{% endsandbox %}

## Custom shadow color

{% sandbox 'Custom shadow color' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<style>
    details[data-dpicss] {
        --shadow-color: #7c783a;
    }
</style>
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
                Custom global shadow color #7c783a
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p><code>--shadow-color: #7c783a</code></p>
    </details>
    <details data-dpicss="box_shadow"
        style="--shadow-color: green">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Shadow color green on DPICSS details element
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p><code>--shadow-color: green</code></p>
    </details>
</main>
{% endsandbox %}

## Custom button texts

{% sandbox 'Custom button texts' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<style>
    details[data-dpicss] {
        --play-text: 'Start now!';
        --pause-text: 'Please stop!';
    }
</style>
<main>
    <details data-dpicss="play pause">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Custom button texts
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p><code>--play-text: 'Start now!'</code> and <code>--pause-text: 'Please stop!'</code></p>
    </details>
    <details data-dpicss="play pause"
        style="
        --play-text: '▶️';
        --pause-text: '⏸';">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Custom button texts on DPICSS details element
            </span>
        </summary>
        <picture>
            <img src="/assets/img/albertville-timelapse.avif"
                alt="Large sized animated image"
                width="1280"
                height="720"
                loading="lazy">
        </picture>
        <p><code>--play-text: '▶️'</code> and <code>--pause-text: '⏸'</code></p>
    </details>
</main>
{% endsandbox %}

## Custom transition duration

{% sandbox 'Custom transition duration' %}
<link rel="stylesheet" href="/dist/dpicss.css">
<link rel="stylesheet" href="/assets/demo.css">
<style>
    details[data-dpicss] {
        --transition-duration: 0ms;
    }
</style>
<main>
    <details data-dpicss="play pause">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Custom global transition duration 0ms
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
    <details data-dpicss="play pause"
        style="--transition-duration: 1s">
        <summary>
            <picture>
                <img src="/assets/img/tn_albertville-timelapse.avif"
                    alt="The thumbnail"
                    width="1280"
                    height="720"
                    loading="lazy">
            </picture>
            <span>
                Custom transition duration 1s on DPICSS details element
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

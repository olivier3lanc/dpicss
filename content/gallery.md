---
title: Gallery
description: A list of DPICSS examples
layout: libdoc_page.liquid
permalink: usage/gallery.html
eleventyNavigation:
    key: Gallery
    order: 60
    parent: Usage
---
<link rel="stylesheet" href="/dist/dpicss.css">

The following example uses DPICSS integrated into [Eleventy LibDoc](https://eleventy-libdoc.netlify.app) to create a simple gallery of animated images. 

<div class="ctn pos-relative z-1">
    <style>
        @layer dpicss {
            details[data-dpicss] {
                --shadow-opacity: 0.3;
                --shadow-radius: 0.5em;
                --primary-size: clamp(11px, 2cqi, 14px);
            }
        }
        .ctn {
            display: inherit;
            container-type: inline-size;
            container-name: gallery;
        }
        .gallery details[data-dpicss] + details[data-dpicss] {
            margin-top: 16px;
        }
    </style>
    <div class="gallery">
        {% for item in gallery %}<details data-dpicss="{{ item.parameters }}"
            {%- if item.style %}
            style="{{- item.style }}"{% endif %}>
            <summary>
                <picture>
                    <img src="{{ item.thumbnailUrl }}"
                        alt="The thumbnail"
                        width="{{ item.width }}"
                        height="{{ item.height }}"
                        loading="lazy"
                        eleventy:ignore>
                </picture>
                <span>{{ item.description }}</span>
            </summary>
            <picture>
                <img src="{{ item.imageUrl }}"
                    alt="Large sized image"
                    width="{{ item.width }}"
                    height="{{ item.height }}"
                    loading="lazy"
                    eleventy:ignore>
            </picture>
        </details>
        {% endfor %}
    </div>
</div>

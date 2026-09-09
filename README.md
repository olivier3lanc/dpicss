# DPiCSS

Details Player for Image with CSS. A tiny CSS library to display animated or higher definition images on click.

[Website](https://dpicss.netlify.app)

**The main idea behind DPiCSS is to beautifully display large-sized images or animated images only on user demand without bloating and reducing page performances.**

https://github.com/user-attachments/assets/53be0c7b-d456-4abe-8c56-58de562e80b6

DPiCSS achieves this combining modern native HTML5 and CSS features:

* **Uses fully semantic HTML5** with `<details>`, `<picture>` and `<img>` tags to display an animated or higher definition image. 
* As a details tag HTML5 element, DPiCSS can [display extra summary content and toggled content](/content/examples.md#add-content-to-details).
* Uses native **lazy loading** of `<img>` tag that allows to download the thumbnail only when it is into the viewport and the larger asset only when its thumbnail is clicked.
* **Responsive type scale**: [Primary font size](/content/customization.md#custom-primary-size) of every DPiCSS instance adjusts automatically based on its container.
* **Automatic color contrast**: Set your preferred primary color and DPiCSS [automatically adjusts the proper contrasted black or white color](/content/customization.md#custom-primary-color).
* **Works with any animated or still image**.
* **Integrates seamlessly into existing pages**.
* **Works without JavaScript**, works even if JavaScript is disabled.
* **Main [parameters](/content/parameters.md) are customizable with few CSS variables**.
* **Displays a loader while thumbnail and large sized image are being loaded**.
* **Supports light and dark color scheme preferences**.
* DPiCSS is [easy to use](/content/usage.md) and has a nice range of [parameters](/content/parameters.md) and [customizations](/content/customization.md). You can [view some examples](/content/examples.md) and [the gallery](/content/gallery.md).

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
git clone git@github.com:olivier3lanc/dpicss.git
cd dpicss
npm install
npx @11ty/eleventy --serve
```

Now you can go to [usage](/content/usage.md).

## Usage

DPiCSS works with [details](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/details), [picture](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/picture) and [image](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/img). Since `alt` attribute is entered, details summary accessibility is fulfilled, but an optional `span` can be added as child of `summary` tag to display HTML content under the thumbnail.

Here is the associated markup to use with DPiCSS:

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
    The keyword based [parameters of DPiCSS](/content/parameters.md)
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

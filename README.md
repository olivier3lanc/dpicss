# DPICSS

Details Player for Image with CSS. A tiny CSS library to display animated or higher definition images on click.

**The main idea behind DPICSS is to beautifully display large-sized images or animated images only on user demand without bloating and reducing page performances.**

![DPICSS screen cast](https://assets.olivewhite.com/dpicss/dpicss.avif)

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
git clone git@github.com:olivier3lanc/dpicss.git
cd dpicss
npm install
npx @11ty/eleventy --serve
```

Now you can go to [usage](/content/usage.md).
Many HTML elements can have their dimensions specified using the `width` and `height` attributes, including:

* `<img>`{.html}
* `<iframe>`{.html}
* `<object>`{.html}
* `<video>`{.html}

For the examples on this page, we will use the `<img>`{.html} element as an example. The base image we will be using 150 pixels in width and 100 pixels in height, split into a 2x3 grid of squares:

![A simple image of a grid with 2 rows and 3 columns](resources/base_image.png)

# Specifying Width and Height

When both `width` and `height` attributes are specified, the element will be displayed at the exact dimensions specified, regardless of its original aspect ratio:

```html
<img src="resources/base_image.png" alt="Base Image" width="400" height="400">
```

produces:

![Base Image](resources/base_image.png)

The values for `width` and `height` are unitless integers, always interpreted as pixels.

Note that in this case, for an image, the image is deformed to fit the specified dimensions, which may distort the image if the aspect ratio is not maintained.

Specifying both `width` and `height` is good practice even when you do not intend to resize the image, because it allows the browser to reserve the correct amount of space in the page layout before the image has finished loading. Without these attributes, the page may reflow and shift when the image loads.

# Specifying Width or Height

If we specify only one dimension (`width` or `height`), the result depends on the element type. For elements with intrinsic dimensions (such as `<img>`{.html} and `<video>`{.html}), the other dimension is adjusted proportionally to maintain aspect ratio:

`<img src="resources/base_image.png" alt="Base Image" width="600">`{.html}

produces:

![Base Image](resources/base_image.png)

and:

```html
<img src="resources/base_image.png" alt="Base Image" height="75">
```

produces:

![Base Image](resources/base_image.png)

For elements without intrinsic media dimensions (for example `<iframe>`{.html}), specifying only one attribute does not automatically scale the other dimension proportionally, so providing both values is usually clearer.

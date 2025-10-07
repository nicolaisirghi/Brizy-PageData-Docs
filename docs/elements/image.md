---
sidebar_position: 8
---

# Image

The `Image` element allows you to display visual media in your layout. It supports configuration for size, alt text, source, and alignment.

## Example

```json
{
  "type": "Image",
  "value": {
    "sizeType": "original",
    "size": 74,
    "sizeSuffix": "%",
    "imageSrc": "https://images.pexels.com/photos/414612/pexels-photo-414612.jpeg?cs=srgb&dl=pexels-souvenirpixels-414612.jpg&fm=jpg"
  }
}
```

![Example Image](/img/image-example.png)

## Key Properties

### Image

- `imageSrc`: The source URL of the image (e.g., `"https://example.com/image.jpg"`).
- `alt`: Alternative text for the image, used for accessibility and SEO (e.g., `"A beautiful sunset"`).
- `sizeType`: The type of size for the image, which can be `"original"`or `"custom"`.
- `zoom`: The zoom level of the image, defined as a number in percent (e.g., `150`). (this option work only if `sizeType` is set to `"custom"`).
- `linkLightBox`: Whether the image should open in a lightbox when clicked (`"on"`, `"off"`).
- `size`: The size of the image, defined as a number in percent (e.g., `100`). (this option work only if `sizeType` is set to `"original"`).
- `width`: The width of the image, defined as a number (e.g., `300`). This is only used if `sizeType` is set to `"custom"`.
- `widthSuffix`: The suffix for the width (`"px"`,`"%"`).
- `height`: The height of the image, defined as a number (e.g., `300`). This is only used if `sizeType` is set to `"custom"`.
- `heightSuffix`: The suffix for the height (`"px"`,`"%"`).
- `positionX`: The horizontal position of the image, defined as a number in percent (e.g., `50`). (this option work only if `sizeType` is set to `"custom"`).
- `positionY`: The vertical position of the image, defined as a number in percent (e.g., `50`). (this option work only if `sizeType` is set to `"custom"`).

### Filters

- `imageHue`: The hue of the image, defined as a number in degrees (0-360).
- `imageSaturation`: The saturation of the image, defined as a number in percent (e.g., `100`).
- `imageBrightness`: The brightness of the image, defined as a number in percent (e.g., `100`).
- `imageContrast`: The contrast of the image, defined as a number in percent (e.g., `100`).

### Background

- `bgColorHex`: The overlay color of the image in hexadecimal format.
- `bgColorOpacity`: The opacity of the overlay color, ranging from `0` (transparent) to `1` (opaque).
- `bgColorPalette`: A predefined overlay color palette option for quick selection. Set to empty string for no palette.
- `bgColorType`: The type of overlay color, which can be `solid`, `gradient`, or `none`.

- `gradientActivePointer`: Pointer to the active gradient .
- `gradientColorHex`: Hexadecimal color for the gradient.
- `gradientColorOpacity`: Opacity of the gradient color.
- `gradientColorPalette`: Named palette value for the gradient color. If not set, it defaults to an empty string. It
  should be set to empty string if no palette is used.
- `gradientFinishPointer`: Pointer to the gradient finish color.
- `gradientStartPointer`: Pointer to the gradient start color.
- `gradientLinearDegree`: Degree of the linear gradient (0-360).
- `gradientRadialDegree`: Degree of the radial gradient (0-360).
- `gradientType`: Type of gradient ("linear", "radial"). Defaults to "linear" if not set.

- `borderColorHex`: Hexadecimal border color.
- `borderColorOpacity`: Opacity of the border color.
- `borderColorPalette`: Named palette value for the border color. If not set, it defaults to an empty string. It should
  be set to empty string if no palette is used.
- `borderWidthType`: Type of border width ("grouped","ungrouped").
- `borderWidth`: If `borderWidthType` is "grouped", this is the width for all sides.
- `borderLeftWidth`, `borderRightWidth`, `borderBottomWidth`, `borderTopWidth`: Individual side border widths. These are
  only used if `borderWidthType` is "ungrouped".
- `borderStyle`: Style of the border ("none" | "solid"| "dashed"| "dotted"| "double"| "groove"| "ridge"| "inset"| "
  outset";).

- `boxShadow`: Box shadow for the section. ("", "on","outset")
- `boxShadowColorHex`: Hexadecimal color for the box shadow.
- `boxShadowColorOpacity`: Opacity of the box shadow color.
- `boxShadowColorPalette`: Named palette value for the box shadow color. If not set, it defaults to an empty string. It
  should be set to empty string if no palette is used.
- `boxShadowBlur`: Blur radius for the box shadow.
- `boxShadowSpread`: Spread radius for the box shadow.
- `boxShadowVertical`: Vertical offset for the box shadow.

- `borderRadius`: Border radius for the icon, defined as a number in pixels (e.g., `10`). Note that this is applied only if the `borderRadiusType` is set to "custom".
- `borderRadiusType`: Type of border radius ("square", "rounded", "custom").

### Hover Effects

The `Image` element supports hover effects for background-related properties. These properties control how the image appears when users hover over it.

**Background hover keys:**

- `hoverBgColorHex`: The background color of the image on hover in hexadecimal format.
- `hoverBgColorOpacity`: The opacity of the background color on hover, ranging from `0` (transparent) to `1` (opaque).
- `hoverBgColorPalette`: A predefined background color palette option for hover state. Set to empty string for no palette.
- `hoverBgColorType`: The type of background color on hover, which can be `solid`, `gradient`, or `none`.

**Gradient hover keys:**

- `hoverGradientActivePointer`: Pointer to the active gradient on hover.
- `hoverGradientColorHex`: Hexadecimal color for the gradient on hover.
- `hoverGradientColorOpacity`: Opacity of the gradient color on hover.
- `hoverGradientColorPalette`: Named palette value for the gradient color on hover. Set to empty string if no palette is used.
- `hoverGradientFinishPointer`: Pointer to the gradient finish color on hover.
- `hoverGradientStartPointer`: Pointer to the gradient start color on hover.
- `hoverGradientLinearDegree`: Degree of the linear gradient on hover (0-360).
- `hoverGradientRadialDegree`: Degree of the radial gradient on hover (0-360).
- `hoverGradientType`: Type of gradient on hover ("linear", "radial"). Defaults to "linear" if not set.

**Border hover keys:**

- `hoverBorderColorHex`: Hexadecimal border color on hover.
- `hoverBorderColorOpacity`: Opacity of the border color on hover.
- `hoverBorderColorPalette`: Named palette value for the border color on hover. Set to empty string if no palette is used.

**Box shadow hover keys:**

- `hoverBoxShadow`: Box shadow for the image on hover. ("", "on","outset")
- `hoverBoxShadowColorHex`: Hexadecimal color for the box shadow on hover.
- `hoverBoxShadowColorOpacity`: Opacity of the box shadow color on hover.
- `hoverBoxShadowColorPalette`: Named palette value for the box shadow color on hover. Set to empty string if no palette is used.
- `hoverBoxShadowBlur`: Blur radius for the box shadow on hover.
- `hoverBoxShadowSpread`: Spread radius for the box shadow on hover.
- `hoverBoxShadowVertical`: Vertical offset for the box shadow on hover.
- `hoverBoxShadowHorizontal`: Horizontal offset for the box shadow on hover.

**Filter hover keys:**

- `hoverImageHue`: The hue of the image on hover, defined as a number in degrees (0-360).
- `hoverImageSaturation`: The saturation of the image on hover, defined as a number in percent (e.g., `100`).
- `hoverImageBrightness`: The brightness of the image on hover, defined as a number in percent (e.g., `100`).
- `hoverImageContrast`: The contrast of the image on hover, defined as a number in percent (e.g., `100`).

**Image hover keys:**

- `hoverImageSrc`: URL of the image on hover.
- `hoverImageWidth` / `hoverImageHeight`: Image dimensions on hover.
- `hoverImageExtension`: File extension on hover ("jpg", "png", etc.)
- `hoverSizeType`: The type of size for the image on hover, which can be `"original"`or `"custom"`.
- `hoverSize`: The size of the image on hover, defined as a number in percent (e.g., `100`).
- `hoverWidth`: The width of the image on hover, defined as a number (e.g., `300`).
- `hoverWidthSuffix`: The suffix for the width on hover (`"px"`,`"%"`).
- `hoverHeight`: The height of the image on hover, defined as a number (e.g., `300`).
- `hoverHeightSuffix`: The suffix for the height on hover (`"px"`,`"%"`).
- `hoverPositionX`: The horizontal position of the image on hover, defined as a number in percent (e.g., `50`).
- `hoverPositionY`: The vertical position of the image on hover, defined as a number in percent (e.g., `50`).
- `hoverZoom`: The zoom level of the image on hover, defined as a number in percent (e.g., `150`).

**Mask hover keys:**

- `hoverMaskShape`: Shape of the mask on hover ("none", "circle", "square", etc.).
- `hoverMaskSize`: Size of the mask on hover ("cover", "contain", "auto").
- `hoverMaskPosition`: Position of the mask on hover ("center center", "50% 50%", etc.).
- `hoverMaskRepeat`: Repeat behavior of the mask on hover ("no-repeat", "repeat", "repeat-x", "repeat-y").
- `hoverMaskScale`: Scale of the mask on hover, defined as a number in percent (e.g., `50`).
- `hoverMaskScaleSuffix`: Suffix for the mask scale on hover (e.g., "%").
- `hoverMaskPositiony`: Vertical position of the mask on hover, defined as a number in percent (e.g., `3`).
- `hoverMaskPositionySuffix`: Suffix for the vertical mask position on hover (e.g., "%").
- `hoverMaskPositionx`: Horizontal position of the mask on hover, defined as a number in percent (e.g., `3`).
- `hoverMaskPositionxSuffix`: Suffix for the horizontal mask position on hover (e.g., "%").
- `hoverMaskCustomUploadImageSrc`: URL of the custom upload mask image on hover.
- `hoverMaskCustomUploadImageExtension`: File extension of the custom upload mask image on hover.
- `hoverMaskCustomUploadImageWidth` / `hoverMaskCustomUploadImageHeight`: Custom upload mask image dimensions on hover.
- `hoverMaskCustomUploadPositionX` / `hoverMaskCustomUploadPositionY`: Position of the custom upload mask image on hover.
- `hoverMaskCustomUploadImageType`: Type of the custom upload mask image on hover ("internal", "external").
- `hoverMaskCustomUploadAlt`: Alt text for the custom upload mask image on hover.
- `hoverMaskShadowColorHex`: Hexadecimal color for the mask shadow on hover.
- `hoverMaskShadowColorOpacity`: Opacity of the mask shadow color on hover.
- `hoverMaskShadowColorPalette`: Named palette value for the mask shadow color on hover. Set to empty string if no palette is used.
- `hoverMaskShadowBlur`: Blur radius for the mask shadow on hover.
- `hoverMaskShadowVertical`: Vertical offset for the mask shadow on hover.
- `hoverMaskShadowHorizontal`: Horizontal offset for the mask shadow on hover.

**Transition keys:**

- `hoverTransition`: Duration of the hover transition effect in milliseconds.
- `hoverTransitionSuffix`: Unit for the hover transition (typically empty string).

```json
{
  "hoverBgColorHex": "#f0f8ff",
  "hoverBgColorOpacity": 0.1,
  "hoverBgColorPalette": "color1",
  "hoverBorderColorHex": "#239ddb",
  "hoverBorderColorOpacity": 1,
  "hoverBorderColorPalette": "color3",
  "hoverImageHue": 10,
  "hoverImageSaturation": 120,
  "hoverImageBrightness": 110,
  "hoverImageContrast": 105,
  "hoverImageSrc": "https://example.com/hover-image.jpg",
  "hoverSizeType": "original",
  "hoverSize": 110,
  "hoverPositionX": 50,
  "hoverPositionY": 50,
  "hoverMaskShape": "circle",
  "hoverMaskSize": "cover",
  "hoverMaskPosition": "center center",
  "hoverMaskScale": 60,
  "hoverMaskScaleSuffix": "%",
  "hoverTransition": 300
}
```

### Link

The `Image` can also be linked to a URL, allowing the entire row to act as a clickable link:
Brizy has a flexible linking system that allows you to set links for elements. The link can be added as Popup, External, Page, Anchor, or Upload.
At the moment we will focus only to the external link, but the other types will be documented in the future.

- `linkType`: Type of link ("external", "page", "anchor","popup","upload").
- `linkExternal`: External URL for the link. (e.g., "https://example.com").
- `linkExternalBlank`: Whether to open the link in a new tab ("on","off").
- `linkExternalRel`: Make the link nofollow ("on","off").

### Styles key

The `styles` key is used to apply CSS classes to the `Image` element.

```json
{
  "_styles": ["image"]
}
```

## DefaultValue for Image

```json
{
  "imageSrc": "",
  "hoverImageSrc": "",
  "maskCustomUploadImageSrc": "",
  "maskCustomUploadImageFileName": "",
  "imageFileName": "",

  "imagePopulation": "",
  "hoverImagePopulation": "",
  "imagePopulationEntityType": "",
  "imagePopulationEntityId": "",

  "imageWidth": 600,
  "imageHeight": 450,
  "imageExtension": "",
  "sizeType": "custom",
  "imageType": "internal",

  "size": 100,
  "sizeSuffix": "%",

  "positionY": 50,
  "positionX": 50,

  "popups": [],
  "tags": "",
  "alt": "",
  "showOriginalImage": "off",

  "offsetX": 0,
  "offsetY": 0,

  "linkPage": "",
  "linkPageTitle": "",
  "linkPageSource": null,
  "linkInternalBlank": "off",
  "linkSource": "",
  "linkType": "external",
  "linkExternal": "",
  "linkAnchor": "",
  "linkToSlide": 1,
  "linkExternalBlank": "off",
  "linkExternalRel": "off",
  "linkLightBox": "off",
  "linkExternalType": "linkExternal",
  "linkPopulation": "",
  "linkPopulationEntityId": "",
  "linkPopulationEntityType": "",
  "linkUpload": "",
  "linkPopup": "",
  "actionClosePopup": "off",

  "blendMode": "normal",

  "customCSS": "",

  "imageBrightness": 100,
  "imageHue": 0,
  "imageSaturation": 100,
  "imageContrast": 100,

  "imageOpacity": 100,

  "zoom": 100,
  "zoomSuffix": "%",

  "width": 100,
  "height": 100,
  "hoverHeight": 100,

  "widthSuffix": "%",
  "heightSuffix": "%",

  "borderStyle": "",

  "borderColorHex": "#66738d",
  "borderColorOpacity": 0,
  "borderColorPalette": "",

  "tempBorderColorOpacity": 1,
  "tempBorderColorPalette": "",

  "tempBorderStyle": "solid",

  "borderWidthType": "grouped",
  "borderWidth": 0,
  "borderTopWidth": 0,
  "borderRightWidth": 0,
  "borderBottomWidth": 0,
  "borderLeftWidth": 0,

  "tempBorderWidth": 4,
  "tempBorderTopWidth": 4,
  "tempBorderRightWidth": 4,
  "tempBorderBottomWidth": 4,
  "tempBorderLeftWidth": 4,

  "borderRadiusType": "square",

  "borderRadius": 0,
  "borderTopLeftRadius": 0,
  "borderTopRightRadius": 0,
  "borderBottomRightRadius": 0,
  "borderBottomLeftRadius": 0,

  "tempBorderRadius": 0,
  "tempBorderTopLeftRadius": 0,
  "tempBorderTopRightRadius": 0,
  "tempBorderBottomRightRadius": 0,
  "tempBorderBottomLeftRadius": 0,

  "borderRadiusSuffix": "px",
  "borderTopLeftRadiusSuffix": "px",
  "borderTopRightRadiusSuffix": "px",
  "borderBottomRightRadiusSuffix": "px",
  "borderBottomLeftRadiusSuffix": "px",

  "tempBorderTopLeftRadiusSuffix": "px",
  "tempBorderTopRightRadiusSuffix": "px",
  "tempBorderBottomRightRadiusSuffix": "px",
  "tempBorderBottomLeftRadiusSuffix": "px",

  "bgColorHex": "#ffffff",
  "bgColorType": "none",
  "bgColorOpacity": 0,
  "bgColorPalette": "",

  "tempBgColorOpacity": 1,
  "tempBgColorPalette": "",
  "tempGradientColorOpacity": 1,

  "gradientType": "linear",

  "gradientColorHex": "#009900",
  "gradientColorOpacity": 1,
  "gradientColorPalette": "",

  "tempGradientColorPalette": "",

  "gradientActivePointer": "startPointer",
  "gradientStartPointer": 0,
  "gradientFinishPointer": 100,

  "gradientLinearDegree": 90,
  "gradientRadialDegree": 90,

  "tempBgColorType": "solid",

  "boxShadow": "none",

  "tempBoxShadow": "on",

  "boxShadowColorHex": "#000000",
  "boxShadowColorOpacity": 1,
  "boxShadowColorPalette": "",

  "tempBoxShadowColorOpacity": 1,
  "tempBoxShadowColorPalette": "",

  "boxShadowBlur": 0,
  "boxShadowSpread": 0,
  "boxShadowVertical": 0,
  "boxShadowHorizontal": 0,

  "tempBoxShadowBlur": 4,
  "tempBoxShadowSpread": 0,
  "tempBoxShadowVertical": 2,
  "tempBoxShadowHorizontal": 1,

  "hoverTransition": 50,
  "hoverTransitionSuffix": "",

  "maskShape": "none",
  "maskSize": "cover",
  "maskPosition": "center center",
  "maskRepeat": "no-repeat",
  "maskScale": 50,
  "maskScaleSuffix": "%",
  "maskPositiony": 3,
  "maskPositionySuffix": "%",
  "maskPositionx": 3,
  "maskPositionxSuffix": "%",

  "maskCustomUploadImageExtension": "",
  "maskCustomUploadImageWidth": 600,
  "maskCustomUploadImageHeight": 450,
  "maskCustomUploadPositionX": 50,
  "maskCustomUploadPositionY": 50,
  "maskCustomUploadImageType": "internal",
  "maskCustomUploadAlt": "",

  "maskShadowColorHex": "#000000",
  "maskShadowColorOpacity": 0,
  "maskShadowColorPalette": "",

  "maskShadowBlur": 0,
  "maskShadowVertical": 0,
  "maskShadowHorizontal": 0,

  "hoverName": "none",
  "hoverDuration": 600,
  "hoverDelay": 0,
  "hoverInfiniteAnimation": true
}
```

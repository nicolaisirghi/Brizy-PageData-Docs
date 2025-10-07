---
sidebar_position: 5
---

# Column

The `Column` is a layout container that is used exclusively inside a `Row`. Each `Row` can have one or more `Column` elements to arrange content side-by-side.

> **Important:** A `Column` must always be a **direct child** of a `Row`. Columns cannot be placed inside other Columns or outside of a Row.

---

## Structure

A `Column` contains a `value` object that holds an `items` array, where nested content (like text, images, etc.) is placed.

```json
{
  "type": "Column",
  "value": {
    "_id": "unique-id-column",
    "items": [
      {
        "type": "Wrapper",
        "value": {
          "_id": "unique-id-text",
          "items": [
            {
              "type": "RichText",
              "value": {
                "_styles": ["rich-text"],
                "text": "This is a text inside a column."
              }
            }
          ]
        }
      }
    ]
  }
}
```

## Properties

The `Column` element supports multiple properties that can be set in the `value` object, the most common ones include:

### Padding

The `padding` keys define the space inside the section, between its content and its border. Padding values can be
uniform or individual for each side, and are typically paired with a suffix to define the unit.

**Supported keys:**

- `padding`: Padding for all sides.
- `paddingSuffix`: Unit for `padding` (e.g., "px", "em").
- `paddingTop`, `paddingRight`, `paddingBottom`, `paddingLeft`: Individual side padding.
- `paddingTopSuffix`, `paddingRightSuffix`, `paddingBottomSuffix`, `paddingLeftSuffix`: Units for individual padding.
- `paddingType`: "grouped" (uniform padding) or "ungrouped" (individual padding).

```json
{
  "padding": 75,
  "paddingSuffix": "px",
  "paddingTop": 50,
  "paddingTopSuffix": "px",
  "paddingRight": 50,
  "paddingRightSuffix": "px",
  "paddingBottom": 50,
  "paddingBottomSuffix": "px",
  "paddingLeft": 50,
  "paddingLeftSuffix": "px",
  "paddingType": "ungrouped"
}
```

### Margin

The `margin` keys define the space outside the section, between its border and surrounding elements.

**Supported keys:**

- `margin`: Margin for all sides.
- `marginSuffix`: Unit for `margin`.
- `marginTop`, `marginRight`, `marginBottom`, `marginLeft`: Individual side margins.
- `marginTopSuffix`, `marginRightSuffix`, `marginBottomSuffix`, `marginLeftSuffix`: Units for individual margins.
- `marginType`: "grouped" or "ungrouped".

```json
{
  "margin": 75,
  "marginSuffix": "px",
  "marginTop": 50,
  "marginTopSuffix": "px",
  "marginRight": 50,
  "marginRightSuffix": "px",
  "marginBottom": 50,
  "marginBottomSuffix": "px",
  "marginLeft": 50,
  "marginLeftSuffix": "px",
  "marginType": "ungrouped"
}
```

### Background

The `background` keys define the appearance of the section’s background, including color, image, and behavior.

**Color-related keys:**

- `bgColorHex`: Hexadecimal background color.
- `bgColorOpacity`: Opacity of the background color.
- `bgColorPalette`: Named palette value ("color1", "color2", etc.). If not set, it defaults to an empty string. It
  should be set to empty string if no palette is used.
- `bgColorType`: Type of background color ("solid", "gradient", "none")

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

```json
{
  "bgColorHex": "#ffffff",
  "bgColorOpacity": 1,
  "bgColorPalette": "",
  "bgColorType": "solid",
  "gradientActivePointer": 0,
  "gradientColorHex": "#000000",
  "gradientColorOpacity": 1,
  "gradientColorPalette": "",
  "gradientFinishPointer": 1,
  "gradientStartPointer": 0,
  "gradientLinearDegree": 90,
  "gradientRadialDegree": 0,
  "gradientType": "linear",
  "borderColorHex": "#000000",
  "borderColorOpacity": 1,
  "borderColorPalette": "",
  "borderWidthType": "ungrouped",
  "borderWidth": 1,
  "borderLeftWidth": 1,
  "borderRightWidth": 1,
  "borderBottomWidth": 1,
  "borderTopWidth": 1,
  "borderStyle": "solid",
  "boxShadow": "on",
  "boxShadowColorHex": "#000000",
  "boxShadowColorOpacity": 0.5,
  "boxShadowColorPalette": "",
  "boxShadowBlur": 10,
  "boxShadowSpread": 0,
  "boxShadowVertical": 5,
  "boxShadowHorizontal": 0
}
```

**Image-related keys:**

- `bgImageSrc`: URL of the background image.
- `bgImageWidth` / `bgImageHeight`: Image dimensions.
- `bgImageExtension`: File extension ("jpg", "png", etc.)

**Behavior and layout keys:**

- `bgSize`: Image size behavior ("cover", "contain", "auto").
- `bgPosition`: Position of the background image ("center center", "50% 50%", etc.).
- `bgRepeat`: Repeat behavior ("off", "on", "repeat-x", "repeat-y").
- `bgAttachment`: Background attachment ("none", "fixed", "animated").

```json
{
  "bgColorHex": "#ffffff",
  "bgColorOpacity": 1,
  "bgColorPalette": "",
  "bgImageSrc": "https://example.com/image.jpg",
  "bgImageWidth": 1920,
  "bgImageHeight": 1080,
  "bgImageExtension": "jpg",
  "bgSize": "cover",
  "bgPosition": "50% 50%",
  "bgRepeat": "off",
  "bgAttachment": "none"
}
```

### Size and Layout

The `Column` element supports various size and layout properties to control its appearance and behavior:

- `width`: Defines the width of the column only in percentage (0-100). (px)
- `height`: Height of the columns in the row.
- `heightSuffix`: Unit for the column height (e.g., "px", "%").
- `heightStyle`: Style of the column height ("auto", "custom").
- `verticalAlign`: Vertical alignment of the row's content ("top", "center", "bottom").

```json
{
  "width": 50,
  "height": 400,
  "heightSuffix": "px",
  "heightStyle": "custom",
  "verticalAlign": "center"
}
```

### Hover Effects

The `Column` element supports hover effects for background-related properties. These properties control how the column appears when users hover over it.

**Background hover keys:**

- `hoverBgColorHex`: The background color of the column on hover in hexadecimal format.
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
- `hoverBorderWidthType`: Type of border width on hover ("grouped","ungrouped").
- `hoverBorderWidth`: If `hoverBorderWidthType` is "grouped", this is the width for all sides on hover.
- `hoverBorderLeftWidth`, `hoverBorderRightWidth`, `hoverBorderBottomWidth`, `hoverBorderTopWidth`: Individual side border widths on hover. These are only used if `hoverBorderWidthType` is "ungrouped".
- `hoverBorderStyle`: Style of the border on hover ("none" | "solid"| "dashed"| "dotted"| "double"| "groove"| "ridge"| "inset"| "outset").

**Box shadow hover keys:**

- `hoverBoxShadow`: Box shadow for the column on hover. ("", "on","outset")
- `hoverBoxShadowColorHex`: Hexadecimal color for the box shadow on hover.
- `hoverBoxShadowColorOpacity`: Opacity of the box shadow color on hover.
- `hoverBoxShadowColorPalette`: Named palette value for the box shadow color on hover. Set to empty string if no palette is used.
- `hoverBoxShadowBlur`: Blur radius for the box shadow on hover.
- `hoverBoxShadowSpread`: Spread radius for the box shadow on hover.
- `hoverBoxShadowVertical`: Vertical offset for the box shadow on hover.
- `hoverBoxShadowHorizontal`: Horizontal offset for the box shadow on hover.

**Image hover keys:**

- `hoverBgImageSrc`: URL of the background image on hover.
- `hoverBgImageExtension`: File extension on hover ("jpg", "png", etc.)

**Filter hover keys:**

- `hoverBrightness`: The brightness of the column on hover, defined as a number in percent (e.g., `100`).
- `hoverHue`: The hue of the column on hover, defined as a number in degrees (0-360).
- `hoverSaturation`: The saturation of the column on hover, defined as a number in percent (e.g., `100`).
- `hoverContrast`: The contrast of the column on hover, defined as a number in percent (e.g., `100`).

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
  "hoverBgColorHex": "#f8f9fa",
  "hoverBgColorOpacity": 0.1,
  "hoverBgColorPalette": "color1",
  "hoverBorderColorHex": "#239ddb",
  "hoverBorderColorOpacity": 1,
  "hoverBorderColorPalette": "color3",
  "hoverBorderWidthType": "grouped",
  "hoverBorderWidth": 2,
  "hoverBorderStyle": "solid",
  "hoverBoxShadow": "on",
  "hoverBoxShadowColorHex": "#000000",
  "hoverBoxShadowColorOpacity": 0.2,
  "hoverBoxShadowBlur": 4,
  "hoverBoxShadowVertical": 2,
  "hoverBoxShadowHorizontal": 1,
  "hoverBgImageSrc": "https://example.com/hover-bg.jpg",
  "hoverBrightness": 110,
  "hoverHue": 10,
  "hoverSaturation": 120,
  "hoverContrast": 105,
  "hoverMaskShape": "circle",
  "hoverMaskSize": "cover",
  "hoverMaskPosition": "center center",
  "hoverMaskScale": 60,
  "hoverMaskScaleSuffix": "%",
  "hoverTransition": 300
}
```

### Link

The `Column` can also be linked to a URL, allowing the entire row to act as a clickable link:
Brizy has a flexible linking system that allows you to set links for elements, including columns. The link can be added as Popup, External, Page, Anchor, or Upload.
At the moment we will focus only to the external link, but the other types will be documented in the future.

- `linkType`: Type of link ("external", "page", "anchor","popup","upload").
- `linkExternal`: External URL for the link. (e.g., "https://example.com").
- `linkExternalBlank`: Whether to open the link in a new tab ("on","off").
- `linkExternalRel`: Make the link nofollow ("on","off").

```json
{
  "linkType": "external",
  "linkExternal": "https://example.com",
  "linkExternalBlank": "on",
  "linkExternalRel": "nofollow"
}
```

### Styles key

The `styles` key is used to apply CSS classes to the `Column` element.

```json
{
  "_styles": ["column"]
}
```

## DefaultValue for Column

```json
{
  "width": 50,
  "widthSuffix": "%",
  "tagName": "div",
  "media": "image",

  "bgSizeType": "custom",
  "bgImageType": "internal",

  "bgImageFileName": null,
  "maskCustomUploadImageFileName": "",

  "bgImageSrc": "",
  "maskCustomUploadImageSrc": "",

  "brightness": 100,
  "hue": 0,
  "saturation": 100,
  "contrast": 100,

  "bgImageWidth": 0,
  "bgImageHeight": 0,
  "bgPositionY": 50,
  "bgPositionX": 50,
  "bgImageExtension": "",

  "bgPopulation": "",
  "hoverBgPopulation": null,
  "bgPopulationEntityType": "",
  "bgPopulationEntityId": "",

  "bgVideo": "",
  "bgVideoCustom": "",
  "bgVideoType": "youtube",
  "bgVideoLoop": "off",

  "bgMapAddress": "Wall Street",

  "bgMapZoom": 15,
  "bgMapZoomSuffix": "",

  "bgSize": "cover",
  "bgRepeat": "off",
  "bgAlt": "",

  "hoverMedia": "image",

  "tabletMedia": null,

  "tabletBgPopulation": "",

  "mobileWidth": 100,

  "mobileMedia": null,

  "mobileBgPopulation": "",

  "showOnDesktop": "on",

  "zIndex": 0,
  "zIndexSuffix": "",

  "items": [],

  "popups": [],

  "showOnTablet": "on",

  "tabletPopups": [],

  "showOnMobile": "on",

  "mobilePopups": [],

  "linkSource": "",
  "linkPage": "",
  "linkPageTitle": "",
  "linkPageSource": null,
  "linkInternalBlank": "off",
  "linkType": "external",
  "linkExternal": "",
  "linkAnchor": "",
  "linkExternalBlank": "off",
  "linkExternalRel": "off",
  "linkExternalType": "linkExternal",
  "linkPopulation": "",
  "linkPopulationEntityId": "",
  "linkPopulationEntityType": "",
  "linkUpload": "",
  "linkPopup": "",

  "blendMode": "normal",

  "className": "",
  "elementPosition": "relative",

  "heightStyle": "auto",
  "height": 400,
  "heightSuffix": "px",

  "tabletHeightStyle": "auto",
  "tabletHeight": 400,
  "tabletHeightSuffix": "px",

  "mobileHeightStyle": "auto",
  "mobileHeight": 400,
  "mobileHeightSuffix": "px",

  "customAttributes": "",
  "customAttributesPopulation": "",
  "customAttributesPopulationEntityType": "",
  "customAttributesPopulationEntityId": "",

  "borderStyle": "solid",

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

  "borderRadiusType": "grouped",
  "borderRadius": 0,
  "borderTopLeftRadius": 0,
  "borderTopRightRadius": 0,
  "borderBottomRightRadius": 0,
  "borderBottomLeftRadius": 0,

  "borderRadiusSuffix": "px",
  "borderTopLeftRadiusSuffix": "px",
  "borderTopRightRadiusSuffix": "px",
  "borderBottomRightRadiusSuffix": "px",
  "borderBottomLeftRadiusSuffix": "px",

  "tempBorderRadius": 0,
  "tempBorderTopLeftRadius": 0,
  "tempBorderTopRightRadius": 0,
  "tempBorderBottomRightRadius": 0,
  "tempBorderBottomLeftRadius": 0,

  "tempBorderRadiusSuffix": "px",
  "tempBorderTopLeftRadiusSuffix": "px",
  "tempBorderTopRightRadiusSuffix": "px",
  "tempBorderBottomRightRadiusSuffix": "px",
  "tempBorderBottomLeftRadiusSuffix": "px",

  "bgColorType": "solid",

  "gradientActivePointer": "startPointer",
  "gradientStartPointer": 0,
  "gradientFinishPointer": 100,

  "gradientType": "linear",

  "gradientLinearDegree": 90,
  "gradientRadialDegree": 90,

  "bgColorHex": "#000000",
  "bgColorOpacity": 0,
  "bgColorPalette": "",

  "tempBgColorOpacity": 1,
  "tempBgColorPalette": "",
  "tempBgColorType": "solid",

  "gradientColorHex": "#009900",
  "gradientColorOpacity": 1,
  "gradientColorPalette": "",

  "tempGradientColorOpacity": 1,
  "tempGradientColorPalette": "",

  "borderColorHex": "#66738d",
  "borderColorOpacity": 0,
  "borderColorPalette": "",

  "tempBorderColorOpacity": 1,
  "tempBorderColorPalette": "",

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

  "verticalAlign": "top",

  "paddingType": "ungrouped",
  "tempPaddingType": "ungrouped",

  "padding": 15,
  "paddingTop": 5,
  "paddingRight": 15,
  "paddingBottom": 5,
  "paddingLeft": 15,

  "tempPadding": 15,
  "tempPaddingTop": 5,
  "tempPaddingRight": 15,
  "tempPaddingBottom": 5,
  "tempPaddingLeft": 15,

  "paddingSuffix": "px",
  "paddingTopSuffix": "px",
  "paddingRightSuffix": "px",
  "paddingBottomSuffix": "px",
  "paddingLeftSuffix": "px",

  "tempPaddingSuffix": "px",
  "tempPaddingTopSuffix": "px",
  "tempPaddingRightSuffix": "px",
  "tempPaddingBottomSuffix": "px",
  "tempPaddingLeftSuffix": "px",

  "marginType": "grouped",
  "margin": 0,
  "marginTop": 0,
  "marginRight": 0,
  "marginBottom": 0,
  "marginLeft": 0,

  "marginSuffix": "px",
  "marginTopSuffix": "px",
  "marginRightSuffix": "px",
  "marginBottomSuffix": "px",
  "marginLeftSuffix": "px",

  "tempMargin": 0,
  "tempMarginTop": 0,
  "tempMarginRight": 0,
  "tempMarginBottom": 0,
  "tempMarginLeft": 0,

  "tempMarginSuffix": "px",
  "tempMarginTopSuffix": "px",
  "tempMarginRightSuffix": "px",
  "tempMarginBottomSuffix": "px",
  "tempMarginLeftSuffix": "px",

  "customClassName": "",

  "customCSS": "",

  "customID": "",

  "cssIDPopulation": "",
  "cssIDPopulationEntityType": "",
  "cssIDPopulationEntityId": "",

  "cssClassPopulation": "",
  "cssClassPopulationEntityType": "",
  "cssClassPopulationEntityId": "",

  "tabletPaddingType": "ungrouped",
  "tempTabletPaddingType": "ungrouped",

  "tabletPadding": 15,
  "tabletPaddingTop": 5,
  "tabletPaddingRight": 15,
  "tabletPaddingBottom": 5,
  "tabletPaddingLeft": 15,

  "tempTabletPadding": 15,
  "tempTabletPaddingTop": 5,
  "tempTabletPaddingRight": 15,
  "tempTabletPaddingBottom": 5,
  "tempTabletPaddingLeft": 15,

  "tabletPaddingSuffix": "px",
  "tabletPaddingTopSuffix": "px",
  "tabletPaddingRightSuffix": "px",
  "tabletPaddingBottomSuffix": "px",
  "tabletPaddingLeftSuffix": "px",

  "tempTabletPaddingSuffix": "px",
  "tempTabletPaddingTopSuffix": "px",
  "tempTabletPaddingRightSuffix": "px",
  "tempTabletPaddingBottomSuffix": "px",
  "tempTabletPaddingLeftSuffix": "px",

  "tabletMarginType": "ungrouped",
  "tabletMargin": 0,
  "tabletMarginTop": 0,
  "tabletMarginRight": 0,
  "tabletMarginBottom": 0,
  "tabletMarginLeft": 0,

  "tabletMarginSuffix": "px",
  "tabletMarginTopSuffix": "px",
  "tabletMarginRightSuffix": "px",
  "tabletMarginBottomSuffix": "px",
  "tabletMarginLeftSuffix": "px",

  "tempTabletMargin": 0,
  "tempTabletMarginTop": 0,
  "tempTabletMarginRight": 0,
  "tempTabletMarginBottom": 0,
  "tempTabletMarginLeft": 0,

  "tempTabletMarginSuffix": "px",
  "tempTabletMarginTopSuffix": "px",
  "tempTabletMarginRightSuffix": "px",
  "tempTabletMarginBottomSuffix": "px",
  "tempTabletMarginLeftSuffix": "px",

  "mobilePaddingType": "ungrouped",
  "tempMobilePaddingType": "ungrouped",

  "mobilePadding": 0,
  "mobilePaddingTop": 0,
  "mobilePaddingRight": 0,
  "mobilePaddingBottom": 0,
  "mobilePaddingLeft": 0,

  "tempMobilePadding": 0,
  "tempMobilePaddingTop": 0,
  "tempMobilePaddingRight": 0,
  "tempMobilePaddingBottom": 0,
  "tempMobilePaddingLeft": 0,

  "mobilePaddingSuffix": "px",
  "mobilePaddingTopSuffix": "px",
  "mobilePaddingRightSuffix": "px",
  "mobilePaddingBottomSuffix": "px",
  "mobilePaddingLeftSuffix": "px",

  "tempMobilePaddingSuffix": "px",
  "tempMobilePaddingTopSuffix": "px",
  "tempMobilePaddingRightSuffix": "px",
  "tempMobilePaddingBottomSuffix": "px",
  "tempMobilePaddingLeftSuffix": "px",

  "mobileMarginType": "ungrouped",
  "mobileMargin": 10,
  "mobileMarginTop": 10,
  "mobileMarginRight": 0,
  "mobileMarginBottom": 10,
  "mobileMarginLeft": 0,

  "mobileMarginSuffix": "px",
  "mobileMarginTopSuffix": "px",
  "mobileMarginRightSuffix": "px",
  "mobileMarginBottomSuffix": "px",
  "mobileMarginLeftSuffix": "px",

  "tempMobileMargin": 10,
  "tempMobileMarginTop": 10,
  "tempMobileMarginRight": 0,
  "tempMobileMarginBottom": 10,
  "tempMobileMarginLeft": 0,

  "tempMobileMarginSuffix": "px",
  "tempMobileMarginTopSuffix": "px",
  "tempMobileMarginRightSuffix": "px",
  "tempMobileMarginBottomSuffix": "px",
  "tempMobileMarginLeftSuffix": "px",

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

  "motionActive": false,
  "motionVerticalEnabled": false,
  "motionVerticalSpeed": 0.5,
  "motionVerticalSpeedSuffix": null,
  "motionVerticalDirection": "up",
  "motionVerticalViewportType": "viewport",
  "motionVerticalViewportTop": 0,
  "motionVerticalViewportBottom": 100,

  "motionHorizontalEnabled": false,
  "motionHorizontalSpeed": 0.5,
  "motionHorizontalSpeedSuffix": null,
  "motionHorizontalDirection": "left",
  "motionHorizontalViewportType": "viewport",
  "motionHorizontalViewportBottom": 100,
  "motionHorizontalViewportTop": 0,

  "motionRotateEnabled": false,
  "motionRotateSpeed": 0.5,
  "motionRotateSpeedSuffix": null,
  "motionRotateDirection": "left",
  "motionRotateX": "center",
  "motionRotateY": "center",
  "motionRotateViewportType": "viewport",
  "motionRotateViewportBottom": 100,
  "motionRotateViewportTop": 0,

  "motionTransparencyEnabled": false,
  "motionTransparencyLevel": 0.5,
  "motionTransparencyLevelSuffix": null,
  "motionTransparencyDirection": "in",
  "motionTransparencyViewportType": "viewport",
  "motionTransparencyViewportBottom": 100,
  "motionTransparencyViewportTop": 0,

  "motionScaleEnabled": false,
  "motionScaleSpeed": 10,
  "motionScaleSpeedSuffix": null,
  "motionScaleDirection": "up",
  "motionScaleX": "center",
  "motionScaleY": "center",
  "motionScaleViewportType": "viewport",
  "motionScaleViewportBottom": 100,
  "motionScaleViewportTop": 0,

  "motionBlurEnabled": false,
  "motionBlurLevel": 0.5,
  "motionBlurLevelSuffix": null,
  "motionBlurDirection": "in",
  "motionBlurViewportType": "viewport",
  "motionBlurViewportBottom": 100,
  "motionBlurViewportTop": 0,

  "motionMouseTrackEnabled": false,
  "motionMouseTrackDirection": "direct",
  "motionMouseTrackSpeed": 0.25,
  "motionMouseTrackSpeedSuffix": null,

  "motionMouseTiltEnabled": false,
  "motionMouseTiltDirection": "direct",
  "motionMouseTiltSpeed": 0.25,
  "motionMouseTiltSpeedSuffix": null,

  "tabletMotionActive": false,
  "tabletMotionMouseTrackEnabled": false,
  "tabletMotionMouseTiltEnabled": false,

  "mobileMotionActive": false,
  "mobileMotionMouseTrackEnabled": false,
  "mobileMotionMouseTiltEnabled": false,

  "animationName": "none",
  "animationDuration": 1000,
  "animationDelay": 1000,
  "animationInfiniteAnimation": false,

  "tempAnimationName": "none",

  "hoverName": "none",
  "hoverDuration": 600,
  "hoverDelay": 0,
  "hoverInfiniteAnimation": true
}
```

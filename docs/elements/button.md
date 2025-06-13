---
sidebar_position: 7
---

# Button

The `Button` element is used to create a clickable button within your layout. It supports various properties such as text, size, colors, links, icons, and alignment.

## Example

```json
{
  "type": "Button",
  "value": {
    "_id": "unique-id",
    "text": "Click Me",
    "size": "medium",
    "iconName": "tail-right",
    "iconPosition": "right",
    "iconType": "glyph"
  }
}
```

![Example Button](/img/button-example.png)

## Key Properties

### Icon

- `iconName`: The name of the icon, which corresponds to a specific icon in the Brizy icon library (e.g., `"favourite-31"`).
- `iconType`: The type of icon, which can be `"glyph"`, `"outline"`, or `"fa"`.
- `iconPosition`: The position of the icon relative to the button text, which can be `"left"`, `"right"`
- `iconSize`: The size of the icon, which can be `"small"`, `"medium"`, `"large"`, or `"custom"`.
- `iconSpacing`: The spacing between the icon and the button text, defined as a number in pixels (e.g., `10`).
- `iconCustomSize`: Custom size for the icon in pixels (e.g., `24`).

### Size

- size: The size of the icon ("small", "medium", "large", "custom")
- paddingRL: Padding on the left and right sides of the button, defined as a number in pixels (e.g., `20`).
- // TODO
- customSizeSuffix: Suffix for the custom size, typically "px" (e.g., `"px"`).
- padding: Padding around the icon, defined as a number in percent (e.g., `50`).

### Color

- `colorHex`: The color of the icon in hexadecimal format (e.g., `#FF5733`).
- `colorOpacity`: The opacity of the icon color, ranging from `0` (transparent) to `1` (opaque).
- `colorPalette`: A predefined color palette option for quick selection. Set to empty string for no palette.

### Background

- `bgColorHex`: The background color of the icon in hexadecimal format.
- `bgColorOpacity`: The opacity of the background color, ranging from `0` (transparent) to `1` (opaque).
- `bgColorPalette`: A predefined background color palette option for quick selection. Set to empty string for no palette.
- `bgColorType`: The type of background color, which can be `solid`, `gradient`, or `none`.

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

### Link

The `Icon` can also be linked to a URL, allowing the entire row to act as a clickable link:
Brizy has a flexible linking system that allows you to set links for elements. The link can be added as Popup, External, Page, Anchor, or Upload.
At the moment we will focus only to the external link, but the other types will be documented in the future.

- `linkType`: Type of link ("external", "page", "anchor","popup","upload").
- `linkExternal`: External URL for the link. (e.g., "https://example.com").
- `linkExternalBlank`: Whether to open the link in a new tab ("on","off").
- `linkExternalRel`: Make the link nofollow ("on","off").

## DefaultValue for Icon

```json
{
  "type": "glyph",
  "name": "favourite-31",

  "showOnDesktop": "on",

  "offsetX": 0,
  "offsetY": 0,

  "popups": [],

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
  "linkExternalType": "linkExternal",
  "linkPopulation": "",
  "linkPopulationEntityType": "",
  "linkPopulationEntityId": "",
  "linkUpload": "",
  "linkPopup": "",
  "actionClosePopup": "off",

  "className": "",

  "customClassName": "",

  "customID": "",

  "cssIDPopulation": "",
  "cssIDPopulationEntityType": "",
  "cssIDPopulationEntityId": "",

  "cssClassPopulation": "",
  "cssClassPopulationEntityType": "",
  "cssClassPopulationEntityId": "",

  "size": "custom",

  "customSize": 48,
  "customSizeSuffix": "px",

  "smallSize": 32,
  "mediumSize": 48,
  "largeSize": 64,

  "padding": 0,
  "paddingSuffix": "%",

  "tempPadding": 20,

  "colorHex": "#239ddb",
  "colorOpacity": 1,
  "colorPalette": "color3",

  "tempColorOpacity": 1,
  "tempColorPalette": "color3",

  "hoverColorHex": "#239ddb",
  "hoverColorOpacity": 0.8,
  "hoverColorPalette": "color3",

  "tempHoverColorOpacity": 1,
  "tempHoverColorPalette": "color3",

  "bgColorType": "solid",

  "gradientActivePointer": "startPointer",
  "gradientStartPointer": 0,
  "gradientFinishPointer": 100,

  "gradientType": "linear",

  "gradientLinearDegree": 90,
  "gradientRadialDegree": 90,

  "hoverBgColorType": "solid",

  "hoverGradientActivePointer": "startPointer",
  "hoverGradientStartPointer": 0,
  "hoverGradientFinishPointer": 100,

  "hoverGradientType": "linear",

  "hoverGradientLinearDegree": 90,
  "hoverGradientRadialDegree": 90,

  "bgColorHex": "#bde1f4",
  "bgColorOpacity": 0,
  "bgColorPalette": "",

  "tempBgColorOpacity": 1,
  "tempBgColorPalette": "color5",

  "hoverName": "none",
  "hoverDuration": 600,
  "hoverDelay": 0,
  "hoverInfiniteAnimation": true,

  "hoverBgColorHex": "#bde1f4",
  "hoverBgColorOpacity": 0,
  "hoverBgColorPalette": "",

  "tempHoverBgColorOpacity": 1,
  "tempHoverBgColorPalette": "color5",

  "gradientColorHex": "#009900",
  "gradientColorOpacity": 1,
  "gradientColorPalette": "",

  "tempGradientColorOpacity": 1,
  "tempGradientColorPalette": "",

  "hoverGradientColorHex": "#009900",
  "hoverGradientColorOpacity": 0,
  "hoverGradientColorPalette": "",

  "tempHoverGradientColorOpacity": 1,
  "tempHoverGradientColorPalette": "",

  "borderColorHex": "#239ddb",
  "borderColorOpacity": 0,
  "borderColorPalette": "",

  "tempBorderColorOpacity": 1,
  "tempBorderColorPalette": "color3",

  "tempHoverBorderColorOpacity": 1,
  "tempHoverBorderColorPalette": "color3",

  "borderRadiusType": "square",
  "borderRadiusSuffix": "px",

  "tempBorderRadiusType": "rounded",

  "borderRadius": 0,
  "borderTopLeftRadius": 0,
  "borderTopRightRadius": 0,
  "borderBottomRightRadius": 0,
  "borderBottomLeftRadius": 0,

  "tempBorderRadius": 4,
  "tempBorderTopLeftRadius": 4,
  "tempBorderTopRightRadius": 4,
  "tempBorderBottomRightRadius": 4,
  "tempBorderBottomLeftRadius": 4,

  "hoverBorderRadius": 0,
  "hoverBorderTopLeftRadius": 0,
  "hoverBorderTopRightRadius": 0,
  "hoverBorderBottomRightRadius": 0,
  "hoverBorderBottomLeftRadius": 0,

  "tempHoverBorderRadius": 4,
  "tempHoverBorderTopLeftRadius": 4,
  "tempHoverBorderTopRightRadius": 4,
  "tempHoverBorderBottomRightRadius": 4,
  "tempHoverBorderBottomLeftRadius": 4,

  "filterColorHex": "#73777f",
  "filterColorOpacity": 0.7,
  "filterColorPalette": "",

  "tempFilterColorOpacity": 0.7,
  "tempFilterColorPalette": "color8",

  "filterBorderStyle": "solid",

  "tempFilterBorderStyle": "solid",

  "filterBorderColorHex": "#dcdee1",
  "filterBorderColorOpacity": 1,
  "filterBorderColorPalette": "",

  "tempFilterBorderColorOpacity": 1,
  "tempFilterBorderColorPalette": "",

  "filterBorderWidthType": "grouped",
  "filterBorderWidth": 2,
  "filterBorderTopWidth": 2,
  "filterBorderRightWidth": 2,
  "filterBorderBottomWidth": 2,
  "filterBorderLeftWidth": 2,

  "tempFilterBorderWidth": 2,
  "tempFilterBorderTopWidth": 2,
  "tempFilterBorderRightWidth": 2,
  "tempFilterBorderBottomWidth": 2,
  "tempFilterBorderLeftWidth": 2,

  "tempBorderStyle": "solid",

  "borderWidthType": "grouped",
  "borderTopWidth": 2,
  "borderRightWidth": 2,
  "borderBottomWidth": 2,
  "borderLeftWidth": 2,

  "tempBorderTopWidth": 2,
  "tempBorderRightWidth": 2,
  "tempBorderBottomWidth": 2,
  "tempBorderLeftWidth": 2,

  "tempHoverBgColorType": "solid",

  "tempBgColorType": "solid",

  "fillType": "filled",
  "tempFillType": "filled",

  "borderWidth": 0,
  "tempBorderWidth": 3,

  "borderStyle": "solid",

  "hoverTransition": 50,
  "hoverTransitionSuffix": "",

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

  "strokeWidth": 1,

  "customCSS": "",

  "ariaLabel": "",

  "tempMobilePadding": 20,
  "tempMobileBorderRadius": 4
}
```

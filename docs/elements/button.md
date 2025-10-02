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

- `size`: The size of the icon (`"small"`, `"medium"`, `"large"`, `"custom"`)
- `paddingRL`: Padding on the left and right sides of the button, defined as a number in pixels (e.g., `20`).
- `paddingTB`: Padding on the top and bottom sides of the button, defined as a number in pixels (e.g., `10`).
- `customSizeSuffix`: Suffix for the custom size, typically "px" (e.g., `"px"`).
- `fillType`: The fill type of the button, which can be `"filled"`, `"outlined"`, or `"default"`. (default is `"filled"`)
- `padding`: Padding around the icon, defined as a number in percent (e.g., `50`).

### Text and Typography

- `text`: The text displayed on the button (e.g., `"Click Me"`).
- `fontSize`: The font size of the button text, defined as a number (e.g., `16`).
- `fontSizeSuffix`: Suffix for the font size, typically "px" (e.g., `"px"`).
- `fontWeight`: The font weight of the button text, which can be a numeric value (e.g., `400`) or a string value like . Note the font should have the weight defined in the font file.
- `fontFamily`: The font family of the button text, which can be a specific font name (e.g., `"Arial"`) or a generic font family (e.g., `"sans-serif"`).
- `fontFamilyType`: The type of font family, which can be `"system"`, `"google"`, or `"upload"`.
- `fontStyle`: If is set then it will apply the font from the global font settings like the colorPalette. Set to empty string for no font style.
- `letterSpacing`: The letter spacing of the button text, defined as a number in pixels (e.g., `1.5`).
- `lineHeight`: The line height of the button text, defined as a number (e.g., `1.5`).
- `bold`: Whether the button text is bold (`true`, `false`).
- `italic`: Whether the button text is italic (`true`, `false`).
- `underline`: Whether the button text is underlined (`true`, `false`).
- `strike:`: Whether the button text has a strikethrough (`true`, `false`).
- `uppercase`: Whether the button text is displayed in uppercase (`true`, `false`).
- `lowercase`: Whether the button text is displayed in lowercase (`true`, `false`).

### Color

- `colorHex`: The color of the text and icon in hexadecimal format (e.g., `#FF5733`).
- `colorOpacity`: The opacity of the text and icon color, ranging from `0` (transparent) to `1` (opaque).
- `colorPalette`: A predefined color palette option for quick selection. Set to empty string for no palette.

### Background

- `bgColorHex`: The background color of the button in hexadecimal format.
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

### Link

The `Button` can also be linked to a URL, allowing the entire row to act as a clickable link:
Brizy has a flexible linking system that allows you to set links for elements. The link can be added as Popup, External, Page, Anchor, or Upload.
At the moment we will focus only to the external link, but the other types will be documented in the future.

- `linkType`: Type of link ("external", "page", "anchor","popup","upload").
- `linkExternal`: External URL for the link. (e.g., "https://example.com").
- `linkExternalBlank`: Whether to open the link in a new tab ("on","off").
- `linkExternalRel`: Make the link nofollow ("on","off").

### Styles key

The `styles` key is used to apply CSS classes to the `Button` element.

```json
{
  "_styles": ["button"]
}
```

## DefaultValue for Button

```json
{
  "text": "BUTTON",
  "textPopulation": "",
  "textPopulationEntityType": "",
  "textPopulationEntityId": "",

  "showOnDesktop": "on",

  "type": "link",

  "iconName": "tail-right",
  "iconType": "glyph",
  "iconFilename": "",

  "popups": [],

  "offsetX": 0,
  "offsetY": 0,

  "linkSource": "",
  "linkPage": "",
  "linkPageTitle": "",
  "linkPageSource": null,
  "linkInternalBlank": "off",
  "linkType": "external",
  "linkExternal": "",
  "linkAnchor": "",
  "linkToSlide": 1,
  "linkExternalBlank": "off",
  "linkExternalRel": "off",
  "linkExternalType": "linkExternal",
  "linkPopulation": "",
  "linkPopulationEntityId": "",
  "linkPopulationEntityType": "",
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

  "iconSize": "small",

  "iconCustomSize": 16,
  "iconCustomSizeSuffix": "px",

  "iconPosition": "right",

  "iconSpacing": 10,
  "iconSpacingSuffix": "px",

  "iconStrokeWidth": 1,

  "smallIconSize": 16,
  "mediumIconSize": 24,
  "largeIconSize": 32,

  "families": {
    "fontFamily": "lato"
  },

  "fontStyle": "button",
  "fontFamilyType": "google",
  "fontSize": 12,
  "fontSizeSuffix": "px",
  "fontWeight": 700,
  "lineHeight": 1.8,
  "letterSpacing": 3,
  "variableFontWeight": 700,
  "fontWidth": 100,
  "fontSoftness": 0,
  "bold": false,
  "italic": false,
  "underline": false,
  "strike": false,
  "uppercase": false,
  "lowercase": false,

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

  "bgColorHex": "#239ddb",
  "bgColorOpacity": 1,
  "bgColorPalette": "color3",

  "tempBgColorOpacity": 1,
  "tempBgColorPalette": "color3",

  "hoverBgColorHex": "#239ddb",
  "hoverBgColorOpacity": 0.8,
  "hoverBgColorPalette": "color3",

  "tempHoverBgColorOpacity": 0.8,
  "tempHoverBgColorPalette": "color3",

  "gradientColorHex": "#009900",
  "gradientColorOpacity": 0.8,
  "gradientColorPalette": "",

  "tempGradientColorOpacity": 0.8,
  "tempGradientColorPalette": "",

  "hoverGradientColorHex": "#009900",
  "hoverGradientColorOpacity": 0,
  "hoverGradientColorPalette": "",

  "tempHoverGradientColorOpacity": 0.8,
  "tempHoverGradientColorPalette": "",

  "colorHex": "#ffffff",
  "colorOpacity": 1,
  "colorPalette": "color8",

  "tempColorOpacity": 1,
  "tempColorPalette": "color8",

  "hoverColorHex": "#ffffff",
  "hoverColorOpacity": 1,
  "hoverColorPalette": "color8",

  "tempHoverColorOpacity": 1,
  "tempHoverColorPalette": "color8",

  "borderColorHex": "#239ddb",
  "borderColorOpacity": 1,
  "borderColorPalette": "color3",

  "tempBorderColorOpacity": 1,
  "tempBorderColorPalette": "color3",

  "hoverBorderColorHex": "#239ddb",
  "hoverBorderColorOpacity": 1,
  "hoverBorderColorPalette": "color3",

  "tempHoverBorderColorOpacity": 0.8,
  "tempHoverBorderColorPalette": "color3",

  "size": "medium",

  "smallFontSize": 11,
  "mediumFontSize": 12,
  "largeFontSize": 13,

  "paddingTB": 14,
  "paddingRL": 42,

  "paddingTBSuffix": "px",
  "paddingRLSuffix": "px",

  "tempPaddingTB": 14,
  "tempPaddingRL": 42,

  "padding": 14,
  "paddingTop": 14,
  "paddingRight": 42,
  "paddingBottom": 14,
  "paddingLeft": 42,

  "paddingSuffix": "px",
  "paddingTopSuffix": "px",
  "paddingRightSuffix": "px",
  "paddingBottomSuffix": "px",
  "paddingLeftSuffix": "px",

  "tempPadding": 14,
  "tempPaddingTop": 14,
  "tempPaddingRight": 42,
  "tempPaddingBottom": 14,
  "tempPaddingLeft": 42,

  "smallPaddingY": 11,
  "smallPaddingX": 26,
  "mediumPaddingY": 14,
  "mediumPaddingX": 42,
  "largePaddingY": 19,
  "largePaddingX": 44,

  "borderRadiusType": "square",
  "tempBorderRadiusType": "square",

  "borderRadius": 2,
  "borderRadiusSuffix": "px",

  "borderTopLeftRadius": 2,
  "borderTopRightRadius": 2,
  "borderBottomRightRadius": 2,
  "borderBottomLeftRadius": 2,

  "tempBorderRadius": 2,
  "tempBorderTopLeftRadius": 2,
  "tempBorderTopRightRadius": 2,
  "tempBorderBottomRightRadius": 2,
  "tempBorderBottomLeftRadius": 2,

  "hoverBorderRadius": 2,
  "hoverBorderTopLeftRadius": 2,
  "hoverBorderTopRightRadius": 2,
  "hoverBorderBottomRightRadius": 2,
  "hoverBorderBottomLeftRadius": 2,

  "tempHoverBorderRadius": 2,
  "tempHoverBorderTopLeftRadius": 2,
  "tempHoverBorderTopRightRadius": 2,
  "tempHoverBorderBottomRightRadius": 2,
  "tempHoverBorderBottomLeftRadius": 2,

  "hoverName": "none",
  "hoverDuration": 600,
  "hoverDelay": 0,
  "hoverInfiniteAnimation": true,

  "fillType": "filled",
  "tempFillType": "filled",

  "borderStyle": "solid",

  "tempBorderStyle": "solid",

  "borderWidthType": "grouped",
  "borderWidth": 2,
  "borderTopWidth": 2,
  "borderRightWidth": 2,
  "borderBottomWidth": 2,
  "borderLeftWidth": 2,

  "tempBorderWidth": 2,
  "tempBorderTopWidth": 2,
  "tempBorderRightWidth": 2,
  "tempBorderBottomWidth": 2,
  "tempBorderLeftWidth": 2,

  "boxShadow": "",

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

  "customCSS": "",

  "width": null,
  "height": null,

  "tabletSize": "small",

  "tabletPadding": 11,
  "tabletPaddingTB": 11,
  "tabletPaddingRL": 26,
  "tempTabletPaddingTB": 11,
  "tempTabletPaddingRL": 26,

  "tabletPaddingTop": 11,
  "tabletPaddingRight": 26,
  "tabletPaddingBottom": 11,
  "tabletPaddingLeft": 26,

  "tabletPaddingSuffix": "px",
  "tabletPaddingTopSuffix": "px",
  "tabletPaddingRightSuffix": "px",
  "tabletPaddingBottomSuffix": "px",
  "tabletPaddingLeftSuffix": "px",

  "tempTabletPadding": 11,
  "tempTabletPaddingTop": 11,
  "tempTabletPaddingRight": 26,
  "tempTabletPaddingBottom": 11,
  "tempTabletPaddingLeft": 26,

  "tabletFontStyle": "button",
  "tabletFontSize": 11,
  "tabletFontSizeSuffix": "px",
  "tabletFontWeight": 700,
  "tabletLineHeight": 1.8,
  "tabletLetterSpacing": 1,

  "tempTabletBorderRadius": 2,

  "mobileSize": "small",

  "mobilePaddingTB": 11,
  "mobilePaddingRL": 26,
  "tempMobilePaddingTB": 11,
  "tempMobilePaddingRL": 26,

  "mobilePadding": 11,
  "mobilePaddingTop": 11,
  "mobilePaddingRight": 26,
  "mobilePaddingBottom": 11,
  "mobilePaddingLeft": 26,

  "mobilePaddingSuffix": "px",
  "mobilePaddingTopSuffix": "px",
  "mobilePaddingRightSuffix": "px",
  "mobilePaddingBottomSuffix": "px",
  "mobilePaddingLeftSuffix": "px",

  "tempMobilePadding": 11,
  "tempMobilePaddingTop": 11,
  "tempMobilePaddingRight": 26,
  "tempMobilePaddingBottom": 11,
  "tempMobilePaddingLeft": 26,

  "mobileFontStyle": "button",
  "mobileFontSize": 11,
  "mobileFontSizeSuffix": "px",
  "mobileFontWeight": 700,
  "mobileLineHeight": 1.8,
  "mobileLetterSpacing": 1,

  "tempMobileBorderRadius": 2
}
```

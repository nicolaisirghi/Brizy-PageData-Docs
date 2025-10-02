---
title: Section Footer
sidebar_position: 3
---

# Section Footer

## SectionFooter Structure

The `SectionFooter` is a special section used specifically for footers. While it shares the general structure of a `Section` or `SectionHeader`, it differs in that elements can be added directly to the items array.

```json
{
  "type": "SectionFooter",
  "value": {
    "items": [
      // Content such as RichText, Images, Buttons, etc.
    ]
  }
}
```

## Keys and Values Applied to SectionFooter

### Padding

The `padding` keys define the space inside the section, between its content and its border. Padding values can be uniform or individual for each side, and are typically paired with a suffix to define the unit.

### Styles key

The `styles` key is used to apply CSS classes to the `SectionFooter` element.

```json
{
  "_styles": ["sectionFooter"]
}
```

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
- `bgColorPalette`: Named palette value ("color1", "color2", etc.). If not set, it defaults to an empty string. It should be set to empty string if no palette is used.
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

### Width and Container Type

Controls how wide the `SectionHeaderItem` content area is.

**Supported keys:**

- `containerType`: "boxed" or "fullWidth".
- `containerSize`: Numeric width of the container.
- `containerSizeSuffix`: Unit for container size (e.g., "px").

```json
{
  "containerType": "boxed",
  "containerSize": 1200,
  "containerSizeSuffix": "px"
}
```

## Combined Example: SectionFooter

```json
{
  "type": "SectionFooter",
  "value": {
    "_id": "section-footer-1",
    "items": [],
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
    "paddingType": "ungrouped",
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
    "marginType": "ungrouped",
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
    "bgAttachment": "none",
    "containerType": "boxed",
    "containerSize": 1200,
    "containerSizeSuffix": "px"
  }
}
```

## DefaultValue for SectionFooter

```json
{
  "items": [],

  "media": "image",
  "tagName": "footer",

  "bgSizeType": "custom",

  "membership": "off",
  "membershipRoles": "[]",

  "translations": "off",
  "translationsLangs": "[]",

  "zIndex": 0,
  "zIndexSuffix": "",

  "elementPosition": "relative",

  "bgImageFileName": null,
  "maskCustomUploadImageFileName": "",

  "bgImageSrc": "",
  "maskCustomUploadImageSrc": "",

  "fullHeight": "off",

  "bgImageWidth": 0,
  "bgImageHeight": 0,
  "bgPositionY": 50,
  "bgPositionX": 50,
  "bgImageType": "internal",
  "bgPopulation": "",
  "bgPopulationEntityType": "",
  "bgPopulationEntityId": "",
  "bgImageExtension": "",
  "bgAlt": "",

  "bgSize": "cover",
  "bgRepeat": "off",

  "brightness": 100,
  "hue": 0,
  "saturation": 100,
  "contrast": 100,

  "bgVideo": "",
  "bgVideoLoop": "off",

  "bgMapAddress": "Wall Street",
  "bgMapZoom": 15,

  "hoverMedia": "image",

  "sectionHeightStyle": "auto",
  "sectionHeight": 400,
  "sectionHeightSuffix": "px",

  "verticalAlign": "center",

  "anchorName": "",

  "cssIDPopulation": "",
  "cssIDPopulationEntityType": "",
  "cssIDPopulationEntityId": "",

  "multiPage": "off",

  "showOnDesktop": "on",

  "showOnTablet": "on",

  "tabletMedia": "image",

  "tabletBgPopulation": "",

  "showOnMobile": "on",

  "mobileMedia": "image",

  "mobileBgPopulation": "",

  "className": "",

  "customClassName": "",

  "cssClassPopulation": "",
  "cssClassPopulationEntityType": "",
  "cssClassPopulationEntityId": "",

  "customAttributes": "",
  "customAttributesPopulation": "",
  "customAttributesPopulationEntityType": "",
  "customAttributesPopulationEntityId": "",

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

  "borderStyle": "",

  "tempBorderStyle": "solid",

  "borderWidthType": "grouped",
  "borderWidth": 0,
  "borderTopWidth": 0,
  "borderRightWidth": 0,
  "borderBottomWidth": 0,
  "borderLeftWidth": 0,

  "tempBorderWidth": 8,
  "tempBorderTopWidth": 8,
  "tempBorderRightWidth": 8,
  "tempBorderBottomWidth": 8,
  "tempBorderLeftWidth": 8,

  "borderRadiusType": "grouped",
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

  "tempBgColorType": "solid",
  "tempBgColorOpacity": 1,
  "tempBgColorPalette": "",

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

  "hoverTransition": 50,
  "hoverTransitionSuffix": "",

  "containerType": "boxed",
  "containerSize": 100,
  "containerSizeSuffix": "%",

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

  "tempMarginType": "grouped",
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

  "paddingType": "ungrouped",
  "tempPaddingType": "ungrouped",

  "padding": 75,
  "paddingTop": 75,
  "paddingRight": 0,
  "paddingBottom": 75,
  "paddingLeft": 0,

  "tempPadding": 75,
  "tempPaddingTop": 75,
  "tempPaddingRight": 0,
  "tempPaddingBottom": 75,
  "tempPaddingLeft": 0,

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

  "boxShadow": "none",

  "tempBoxShadow": "inset",

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

  "shape": "top",

  "shapeTopColorHex": "#000000",
  "shapeTopColorOpacity": 1,
  "shapeTopColorPalette": "",

  "tempShapeTopColorOpacity": 1,
  "tempShapeTopColorPalette": "",

  "shapeBottomColorHex": "#000000",
  "shapeBottomColorOpacity": 1,
  "shapeBottomColorPalette": "",

  "tempShapeBottomColorOpacity": 1,
  "tempShapeBottomColorPalette": "",

  "tempShapeColorOpacity": 1,
  "shapeTopHeight": 100,
  "shapeTopHeightSuffix": "px",
  "shapeBottomHeight": 100,
  "shapeBottomHeightSuffix": "px",
  "shapeTopType": "none",
  "shapeBottomType": "none",
  "shapeTopIndex": "auto",
  "shapeBottomIndex": "auto",
  "shapeTopHorizontal": "off",
  "shapeBottomHorizontal": "off",
  "shapeTopFlip": "off",
  "shapeBottomFlip": "off",

  "containerClassName": "",

  "customCSS": "",

  "tabletMarginType": "grouped",
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

  "tempTabletMarginType": "grouped",
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

  "tabletPaddingType": "ungrouped",
  "tempTabletPaddingType": "ungrouped",

  "tabletPadding": 25,
  "tabletPaddingTop": 25,
  "tabletPaddingRight": 15,
  "tabletPaddingBottom": 25,
  "tabletPaddingLeft": 15,

  "tempTabletPadding": 25,
  "tempTabletPaddingTop": 25,
  "tempTabletPaddingRight": 15,
  "tempTabletPaddingBottom": 25,
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

  "mobileMarginType": "grouped",
  "mobileMargin": 0,
  "mobileMarginTop": 0,
  "mobileMarginRight": 0,
  "mobileMarginBottom": 0,
  "mobileMarginLeft": 0,

  "mobileMarginSuffix": "px",
  "mobileMarginTopSuffix": "px",
  "mobileMarginRightSuffix": "px",
  "mobileMarginBottomSuffix": "px",
  "mobileMarginLeftSuffix": "px",

  "tempMobileMarginType": "grouped",
  "tempMobileMargin": 0,
  "tempMobileMarginTop": 0,
  "tempMobileMarginRight": 0,
  "tempMobileMarginBottom": 0,
  "tempMobileMarginLeft": 0,

  "tempMobileMarginSuffix": "px",
  "tempMobileMarginTopSuffix": "px",
  "tempMobileMarginRightSuffix": "px",
  "tempMobileMarginBottomSuffix": "px",
  "tempMobileMarginLeftSuffix": "px",

  "mobilePaddingType": "ungrouped",
  "tempMobilePaddingType": "ungrouped",

  "mobilePadding": 25,
  "mobilePaddingTop": 25,
  "mobilePaddingRight": 15,
  "mobilePaddingBottom": 25,
  "mobilePaddingLeft": 15,

  "tempMobilePadding": 25,
  "tempMobilePaddingTop": 25,
  "tempMobilePaddingRight": 15,
  "tempMobilePaddingBottom": 25,
  "tempMobilePaddingLeft": 15,

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

  "animationName": "none",
  "animationDuration": 1000,
  "animationDelay": 1000,
  "animationInfiniteAnimation": false,

  "tempAnimationName": "none"
}
```

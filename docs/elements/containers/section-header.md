---
title: Section Header
sidebar_position: 2
---

# Section Header

## SectionHeader Structure

The `SectionHeader` is a special section used for headers. It uses the same general structure as a `Section`, but allows for two items in its `value.items` array:

- `SectionHeaderItem` – **required**; holds the main header content.
- `SectionHeaderStickyItem` – **optional**; used when the header is sticky and needs separate sticky content.

```json
{
  "type": "SectionHeader",
  "value": {
    "items": [
      {
        "type": "SectionHeaderItem",
        "value": {
          "items": [
            // Content such as RichText, Images, etc.
          ]
        }
      },
      {
        "type": "SectionHeaderStickyItem",
        "value": {
          "items": [
            // Content for sticky header behavior
          ]
        }
      }
    ]
  }
}
```

## Keys and Values Applied to SectionHeader

- `type`: "static" | "fixed" | "animated"
  - Defines the behavior of the section header.
  - "fixed" means it stays at the top of the viewport.
  - "animated" means it scrolls with the page.
  - "static" means it does not change position on scroll.

### Styles key for SectionHeader

The `styles` key is used to apply CSS classes to the `SectionHeader` element.

```json
{
  "_styles": ["sectionHeader"]
}
```

## Keys and Values Applied to SectionHeaderItem and SectionHeaderStickyItem

### Padding

The `padding` keys define the space inside the section, between its content and its border. Padding values can be uniform or individual for each side, and are typically paired with a suffix to define the unit.

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

### Styles key for SectionHeaderItem

The `styles` key is used to apply CSS classes to the `SectionHeaderItem` element.

```json
{
  "_styles": ["sectionHeaderItem"]
}
```

### Styles key for SectionHeaderStickyItem

The `styles` key is used to apply CSS classes to the `SectionHeaderStickyItem` element.

```json
{
  "_styles": ["sectionHeaderStickyItem"]
}
```

### Hover Effects for SectionHeaderItem

The `SectionHeaderItem` element supports hover effects for background-related properties. These properties control how the section header item appears when users hover over it.

**Background hover keys:**

- `hoverBgColorHex`: The background color of the section header item on hover in hexadecimal format.
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

- `hoverBoxShadow`: Box shadow for the section header item on hover. ("", "on","outset")
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

- `hoverBrightness`: The brightness of the section header item on hover, defined as a number in percent (e.g., `100`).
- `hoverHue`: The hue of the section header item on hover, defined as a number in degrees (0-360).
- `hoverSaturation`: The saturation of the section header item on hover, defined as a number in percent (e.g., `100`).
- `hoverContrast`: The contrast of the section header item on hover, defined as a number in percent (e.g., `100`).

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

### Hover Effects for SectionHeaderStickyItem

The `SectionHeaderStickyItem` element supports hover effects for background-related properties. These properties control how the section header sticky item appears when users hover over it.

**Background hover keys:**

- `hoverBgColorHex`: The background color of the section header sticky item on hover in hexadecimal format.
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

- `hoverBoxShadow`: Box shadow for the section header sticky item on hover. ("", "on","outset")
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

- `hoverBrightness`: The brightness of the section header sticky item on hover, defined as a number in percent (e.g., `100`).
- `hoverHue`: The hue of the section header sticky item on hover, defined as a number in degrees (0-360).
- `hoverSaturation`: The saturation of the section header sticky item on hover, defined as a number in percent (e.g., `100`).
- `hoverContrast`: The contrast of the section header sticky item on hover, defined as a number in percent (e.g., `100`).

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

## Combined Example: SectionHeader with SectionHeaderItem and SectionHeaderStickyItem

```json
{
  "type": "SectionHeader",
  "value": {
    "_id": "sectionHeader_001",
    "items": [
      {
        "type": "SectionHeaderItem",
        "value": {
          "_id": "headerItem_001",
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
          "containerSizeSuffix": "px",
          "items": []
        }
      },
      {
        "type": "SectionHeaderStickyItem",
        "value": {
          "_id": "stickyItem_001",
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
          "bgColorHex": "#f5f5f5",
          "bgColorOpacity": 1,
          "bgColorPalette": "",
          "bgImageSrc": "",
          "bgImageWidth": 0,
          "bgImageHeight": 0,
          "bgImageExtension": "",
          "bgSize": "cover",
          "bgPosition": "50% 50%",
          "bgRepeat": "off",
          "bgAttachment": "none",
          "containerType": "boxed",
          "containerSize": 1200,
          "containerSizeSuffix": "px",
          "items": []
        }
      }
    ],
    "type": "fixed"
  }
}
```

## DefaultValue for SectionHeader

```json
{
  "items": [],

  "type": "fixed",

  "tagName": "section",

  "anchorName": "",

  "cssIDPopulation": "",
  "cssIDPopulationEntityType": "",
  "cssIDPopulationEntityId": "",

  "membership": "off",
  "membershipRoles": "[]",

  "translations": "off",
  "translationsLangs": "[]",

  "showOnDesktop": "on",
  "showOnTablet": "on",
  "showOnMobile": "on",

  "className": "",

  "customClassName": "",

  "cssClassPopulation": "",
  "cssClassPopulationEntityType": "",
  "cssClassPopulationEntityId": "",

  "containerClassName": "",

  "customAttributes": "",
  "customAttributesPopulation": "",
  "customAttributesPopulationEntityType": "",
  "customAttributesPopulationEntityId": "",

  "animationName": "none",
  "animationDuration": 1000,
  "animationDelay": 1000,
  "animationInfiniteAnimation": false,

  "tempAnimationName": "none"
}
```

## DefaultValue for SectionHeaderItem

```json
{
  "items": [],

  "media": "image",

  "bgSizeType": "custom",

  "bgImageFileName": null,
  "maskCustomUploadImageFileName": "",

  "bgImageSrc": "",
  "maskCustomUploadImageSrc": "",

  "bgImageWidth": 0,
  "bgImageHeight": 0,
  "bgPositionY": 50,
  "bgPositionX": 50,
  "bgPopulation": "",
  "bgPopulationEntityType": "",
  "bgPopulationEntityId": "",
  "bgImageExtension": "",
  "bgImageType": "internal",
  "bgAlt": "",

  "bgSize": "cover",
  "bgRepeat": "off",

  "brightness": 100,
  "hue": 0,
  "saturation": 100,
  "contrast": 100,

  "hoverMedia": "image",

  "tabletBgPopulation": "",

  "mobileBgPopulation": "",

  "className": "",

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
  "customClassName": "",

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

  "tabletPadding": 50,
  "tabletPaddingTop": 50,
  "tabletPaddingRight": 15,
  "tabletPaddingBottom": 50,
  "tabletPaddingLeft": 15,

  "tempTabletPadding": 50,
  "tempTabletPaddingTop": 50,
  "tempTabletPaddingRight": 15,
  "tempTabletPaddingBottom": 50,
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
  "tempMobilePaddingLeftSuffix": "px"
}
```

## DefaultValue for SectionHeaderStickyItem

```json
{
  "items": [],

  "media": "image",

  "bgSizeType": "custom",

  "bgImageFileName": null,

  "bgImageSrc": "",

  "bgImageWidth": 0,
  "bgImageHeight": 0,
  "bgPositionY": 50,
  "bgPositionX": 50,
  "bgPopulation": "",
  "bgPopulationEntityType": "",
  "bgPopulationEntityId": "",
  "bgImageExtension": "",
  "bgImageType": "internal",
  "bgAlt": "",

  "bgSize": "cover",
  "bgRepeat": "off",

  "brightness": 100,
  "hue": 0,
  "saturation": 100,
  "contrast": 100,

  "hoverMedia": "image",

  "tabletBgPopulation": "",

  "mobileBgPopulation": "",

  "className": "",

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

  "bgColorHex": "#FFFFFF",
  "bgColorOpacity": 1,
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

  "paddingType": "ungrouped",
  "tempPaddingType": "ungrouped",

  "padding": 10,
  "paddingTop": 10,
  "paddingRight": 0,
  "paddingBottom": 10,
  "paddingLeft": 0,

  "tempPadding": 10,
  "tempPaddingTop": 10,
  "tempPaddingRight": 0,
  "tempPaddingBottom": 10,
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
  "masKCustomUploadImageType": "internal",
  "maskCustomUpload": "",

  "maskShadowColorHex": "#000000",
  "maskShadowColorOpacity": 0,
  "maskShadowColorPalette": "",

  "maskShadowBlur": 0,
  "maskShadowVertical": 0,
  "maskShadowHorizontal": 0,

  "containerClassName": "",
  "customClassName": "",

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

  "tabletPaddingType": "ungrouped",
  "tempTabletPaddingType": "ungrouped",

  "tabletPadding": 10,
  "tabletPaddingTop": 10,
  "tabletPaddingRight": 0,
  "tabletPaddingBottom": 10,
  "tabletPaddingLeft": 0,

  "tempTabletPadding": 10,
  "tempTabletPaddingTop": 10,
  "tempTabletPaddingRight": 0,
  "tempTabletPaddingBottom": 10,
  "tempTabletPaddingLeft": 0,

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

  "mobilePaddingType": "ungrouped",
  "tempMobilePaddingType": "ungrouped",

  "mobilePadding": 10,
  "mobilePaddingTop": 10,
  "mobilePaddingRight": 0,
  "mobilePaddingBottom": 10,
  "mobilePaddingLeft": 0,

  "tempMobilePadding": 10,
  "tempMobilePaddingTop": 10,
  "tempMobilePaddingRight": 0,
  "tempMobilePaddingBottom": 10,
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
  "tempMobilePaddingLeftSuffix": "px"
}
```

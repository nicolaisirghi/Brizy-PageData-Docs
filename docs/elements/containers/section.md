---
id: section
title: Section
sidebar_position: 1
---

# Section

In the Brizy PageData structure, the top-level key is `items`, which contains an array of elements.  
Each of these elements is typically a `Section`, or an extended type of section such as:

- **SectionFooter**
- **SectionHeader**

These represent large layout blocks used to structure the page content.  
Each section element follows the same internal format with two required keys:

- **type**: The type of the element, e.g., `"Section"`, `"SectionFooter"`, etc.
- **value**: An object containing all the data and nested elements of that section.

Sections usually contain a list of nested items through the `value.items` key. These can include containers like `Wrapper`, `Cloneable`, or any supported Brizy element that builds the content layout.

## Section Structure

A `Section` is a fundamental layout block. It always contains one item: a `SectionItem`. This `SectionItem` wraps the actual content of the section.

Note: It can contain multiple `SectionItem` elements when the `slider` key is enabled (slider is "on").

```json
{
  "type": "Section",
  "value": {
    "items": [
      {
        "type": "SectionItem",
        "value": {
          "items": [
            // Nested elements like Wrappers, RichText, Images, etc.
          ]
        }
      }
    ]
  }
}
```

## Keys and Values Applied to Section

The `value` object of a `Section` contains various keys that control the layout and behavior of the section. Below are the most commonly used keys:

- `padding`: Controls the internal spacing of the section.
- `margin`: Controls the external spacing of the section.
- `height`: Defines the section height and related behavior.

### Styles key

The `styles` key is used to apply CSS classes to the `Section` element.

```json
{
  "_styles": ["section"]
}
```

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

### Height and Full Height Behavior

**Supported keys:**

- `fullHeight`: "off", "on", or "custom". Determines if the section takes full viewport height.
- `sectionHeight`: Numeric height of the section (used only when `fullHeight` is "custom").
- `sectionHeightSuffix`: Unit for `sectionHeight` (e.g., "px", "vh").

```json
{
  "fullHeight": "off",
  "sectionHeight": 600,
  "sectionHeightSuffix": "px"
}
```

---

## Keys and Values Applied to SectionItem

The `SectionItem` is the main content holder inside a `Section`. It supports various configuration keys that affect layout, background, and width.

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

Controls how wide the `SectionItem` content area is.

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

### Hover Effects for SectionItem

The `SectionItem` element supports hover effects for background-related properties. These properties control how the section item appears when users hover over it.

**Background hover keys:**

- `hoverBgColorHex`: The background color of the section item on hover in hexadecimal format.
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

- `hoverBoxShadow`: Box shadow for the section item on hover. ("", "on","outset")
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
  "hoverTransition": 300
}
```

### Styles key for SectionItem

The `styles` key is used to apply CSS classes to the `SectionItem` element.

```json
{
  "_styles": ["section-item"]
}
```

---

## Combined Example: Section with SectionItem

The example below demonstrates how all these keys come together to define a `Section` element with a `SectionItem`.

```json
{
  "type": "Section",
  "value": {
    "padding": 75,
    "paddingSuffix": "px",
    "paddingType": "ungrouped",
    "margin": 50,
    "marginSuffix": "px",
    "marginType": "ungrouped",
    "fullHeight": "off",
    "sectionHeight": 600,
    "sectionHeightSuffix": "px",
    "items": [
      {
        "type": "SectionItem",
        "value": {
          "bgColorHex": "#ffffff",
          "bgColorOpacity": 1,
          "bgImageSrc": "https://example.com/image.jpg",
          "bgSize": "cover",
          "bgPosition": "center center",
          "bgRepeat": "off",
          "bgAttachment": "none",
          "containerType": "boxed",
          "containerSize": 1200,
          "containerSizeSuffix": "px",
          "items": []
        }
      }
    ]
  }
}
```

## DefaultValue json of Section

```json
{
  "items": [],

  "anchorName": "",

  "cssIDPopulation": "",
  "cssIDPopulationEntityType": "",
  "cssIDPopulationEntityId": "",

  "membership": "off",
  "membershipRoles": "[]",

  "translations": "off",
  "translationsLangs": "[]",

  "fullHeight": "off",
  "tagName": "section",

  "slider": "off",

  "showOnDesktop": "on",

  "zIndex": 0,
  "zIndexSuffix": "",

  "showOnTablet": "on",

  "showOnMobile": "on",

  "sliderAnimation": "none",
  "sliderAnimationSpeed": "0.5",
  "sliderAnimationSpeedSuffix": "s",
  "sliderAutoPlay": "off",
  "sliderAutoPlaySpeed": 3,
  "sliderAutoPlaySpeedSuffix": null,

  "animationName": "none",
  "animationDuration": 1000,
  "animationDelay": 1000,
  "animationInfiniteAnimation": false,

  "tempAnimationName": "none",

  "className": "",
  "elementPosition": "relative",

  "customClassName": "",

  "cssClassPopulation": "",
  "cssClassPopulationEntityType": "",
  "cssClassPopulationEntityId": "",

  "customAttributes": "",
  "customAttributesPopulation": "",
  "customAttributesPopulationEntityType": "",
  "customAttributesPopulationEntityId": "",

  "sliderDots": "circle",

  "sliderDotsColorHex": "#000000",
  "sliderDotsColorOpacity": 1,
  "sliderDotsColorPalette": "",

  "tempSliderDotsColorOpacity": 1,
  "tempSliderDotsColorPalette": "",

  "hoverSliderDotsColorHex": "#000000",
  "hoverSliderDotsColorOpacity": 1,
  "hoverSliderDotsColorPalette": "",

  "tempHoverSliderDotsColorOpacity": 1,
  "tempHoverSliderDotsColorPalette": "",

  "sliderArrows": "thin",

  "sliderArrowsColorHex": "#000000",
  "sliderArrowsColorOpacity": 0.7,
  "sliderArrowsColorPalette": "",

  "sectionHeightStyle": "auto",
  "sectionHeight": 400,
  "sectionHeightSuffix": "px",

  "verticalAlign": "center",

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

  "mobileMarginType": "ungrouped",
  "mobileMargin": 0,
  "mobileMarginTop": 0,
  "mobileMarginRight": 0,
  "mobileMarginBottom": 0,
  "mobileMarginLeft": 0,

  "mobileMarginSuffix": "px",
  "mobileMarginTopSuffix": "px",
  "mobileMarginRightSuffix": "px",
  "mobileMarginBottomSuffix": "px",
  "mobileMarginLeftSuffix": "px"
}
```

## DefaultValue json for SectionItem

```json
{
  "items": [],

  "media": "image",
  "hoverMedia": "image",

  "bgSizeType": "custom",
  "bgImageFileName": null,
  "maskCustomUploadImageFileName": "",

  "bgImageSrc": "",
  "maskCustomUploadImageSrc": "",

  "bgImageWidth": 0,
  "bgImageHeight": 0,
  "bgImageType": "internal",
  "bgAlt": "",

  "bgPositionY": 50,
  "bgPositionX": 50,
  "bgPopulation": "",
  "hoverBgPopulation": null,
  "bgPopulationEntityType": "",
  "bgPopulationEntityId": "",
  "bgImageExtension": "",
  "bgSize": "cover",
  "bgRepeat": "off",
  "bgPosition": "50% 50%",

  "bgAttachment": "none",

  "bgVideo": "",
  "bgVideoType": "youtube",
  "bgVideoCustom": "",
  "bgVideoLoop": "off",
  "bgVideoStart": 0,

  "bgMapAddress": "Wall Street",
  "bgMapZoom": 15,
  "bgMapZoomSuffix": "",

  "brightness": 100,
  "hue": 0,
  "saturation": 100,
  "contrast": 100,

  "tabletMedia": null,

  "tabletBgPopulation": "",

  "tabletBgAttachment": "none",

  "mobileMedia": null,

  "mobileBgPopulation": "",

  "mobileBgAttachment": "none",

  "popups": [],

  "slideshow": "",
  "slideshowLoop": "on",
  "slideshowDuration": 1,
  "slideshowDurationSuffix": "s",
  "slideshowTransitionType": "fade",
  "slideshowTransition": 1,
  "slideshowTransitionSuffix": "s",
  "kenBurnsEffect": "off",

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

  "className": "",

  "blendMode": "normal",

  "borderStyle": "solid",
  "tempBorderStyle": "solid",

  "bgColorType": "solid",

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

  "gradientActivePointer": "startPointer",
  "gradientStartPointer": 0,
  "gradientFinishPointer": 100,

  "gradientType": "linear",

  "gradientLinearDegree": 90,
  "gradientRadialDegree": 90,

  "borderColorHex": "#66738d",
  "borderColorOpacity": 0,
  "borderColorPalette": "",

  "tempBorderColorOpacity": 1,
  "tempBorderColorPalette": "",

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

  "hoverTransition": 50,
  "hoverTransitionSuffix": "",

  "containerType": "boxed",

  "containerSize": 100,
  "containerSizeSuffix": "%",

  "paddingType": "ungrouped",
  "tempPaddingType": "ungrouped",

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

  "containerClassName": "",

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

  "customCSS": "",

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

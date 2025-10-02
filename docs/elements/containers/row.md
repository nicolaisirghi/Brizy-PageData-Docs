---
title: Row
sidebar_position: 4
---

# Row

The `Row` is a layout container used to arrange content horizontally. It is typically used within layout structures to
group multiple `Column` elements in a single row, similar to a flexbox row in CSS.

> **Important:** The `Row` can only contain `Column` elements as its **direct children** inside the `items` array. Any
> other element types must be nested **within a Column**.

---

## Structure

The `Row` contains a `value` object with an `items` array. Each item in the array must be of type `Column`.

The example bellow illustrate a `Row` with two `Columns` each of them with one image inside

```json
{
  "type": "Row",
  "value": {
    "_styles": ["row"],
    "items": [
      {
        "type": "Column",
        "value": {
          "_styles": ["column"],
          "items": [
            {
              "type": "Wrapper",
              "value": {
                "_styles": ["wrapper", "wrapper--image"],
                "items": [
                  {
                    "type": "Image",
                    "value": {
                      "_styles": ["image"],
                      "sizeType": "original",
                      "_id": "aMF8Inaz6spS"
                    }
                  }
                ],
                "_id": "lepy6p8PmdK_"
              }
            }
          ],
          "_id": "u0OqjWFfTMTz"
        }
      },
      {
        "type": "Column",
        "value": {
          "_styles": ["column"],
          "items": [
            {
              "type": "Wrapper",
              "value": {
                "_styles": ["wrapper", "wrapper--image"],
                "items": [
                  {
                    "type": "Image",
                    "value": {
                      "_styles": ["image"],
                      "sizeType": "original",
                      "_id": "uG6X7_O1H0WR"
                    }
                  }
                ]
              }
            }
          ]
        }
      }
    ],
    "_id": "yTGE0os6FDb4"
  }
}
```

![Example Row Rendering](/img/row-example.png)

## Properties

### Styles key

The `styles` key is used to apply CSS classes to the `Row` element.

```json
{
  "_styles": ["row"]
}
```

If you want to hide the rows to be only the columns your style should like this:

```json
{
  "_styles": ["row", "hide-row-borders", "padding-0"]
}
```

The `Row` element supports multiple properties that can be set in the `value` object, the most common ones include:

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

The `Row` element supports various size and layout properties to control its appearance and behavior:

- `size`: Defines the width of the row
- `sizeSuffix`: Unit for the size (e.g., "px", "%").
- `columnsHeight`: Height of the columns in the row.
- `columnsHeightSuffix`: Unit for the column height (e.g., "px", "%").
- `columnsHeightStyle`: Style of the column height ("auto", "custom").
- `verticalAlign`: Vertical alignment of the row's content ("top", "center", "bottom").

```json
{
  "size": 100,
  "sizeSuffix": "%",
  "columnsHeight": 300,
  "columnsHeightSuffix": "px",
  "columnsHeightStyle": "custom",
  "verticalAlign": "center"
}
```

### Link

The `Row` can also be linked to a URL, allowing the entire row to act as a clickable link:
Brizy has a flexible linking system that allows you to set links for elements, including rows. The link can be added as Popup, External, Page, Anchor, or Upload.
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

## DefaultValue for Row

```json
{
  "media": "image",
  "tagName": "div",

  "bgSizeType": "custom",
  "bgImageType": "internal",
  "bgAlt": "",

  "bgImageFileName": null,
  "maskCustomUploadImageFileName": "",

  "bgImageSrc": "",
  "maskCustomUploadImageSrc": "",

  "bgImageWidth": 0,
  "bgImageHeight": 0,
  "bgPositionY": 50,
  "bgPositionX": 50,
  "bgImageExtension": "",

  "bgPopulation": "",
  "hoverBgPopulation": null,
  "bgPopulationEntityType": "",
  "bgPopulationEntityId": "",

  "bgSize": "cover",
  "bgRepeat": "off",

  "brightness": 100,
  "hue": 0,
  "saturation": 100,
  "contrast": 100,

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

  "bgVideo": "",
  "bgVideoCustom": "",
  "bgVideoType": "youtube",
  "bgVideoLoop": "off",

  "bgMapAddress": "Wall Street",
  "bgMapZoom": 15,
  "bgMapZoomSuffix": "",

  "hoverMedia": "image",

  "showToolbar": "on",

  "showOnDesktop": "on",

  "zIndex": 0,
  "zIndexSuffix": "",

  "tabletReverseColumns": "off",

  "showOnTablet": "on",

  "tabletMedia": null,

  "tabletBgPopulation": "",

  "showOnMobile": "on",

  "mobileMedia": null,

  "mobileBgPopulation": "",

  "size": 100,
  "sizeSuffix": "%",

  "items": [],

  "popups": [],

  "linkPage": "",
  "linkPageTitle": "",
  "linkSource": "",
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

  "animationName": "none",
  "animationDuration": 1000,
  "animationDelay": 1000,
  "animationInfiniteAnimation": false,

  "hoverName": "none",
  "hoverDuration": 600,
  "hoverDelay": 0,
  "hoverInfiniteAnimation": true,

  "tempAnimationName": "none",

  "className": "",
  "elementPosition": "relative",

  "blendMode": "normal",

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

  "columnsHeightStyle": "auto",
  "columnsHeight": 400,
  "columnsHeightSuffix": "px",

  "verticalAlign": "top",
  "tabletVerticalAlign": "top",
  "mobileVerticalAlign": "top",

  "paddingType": "grouped",
  "tempPaddingType": "grouped",

  "padding": 10,
  "paddingTop": 10,
  "paddingRight": 10,
  "paddingBottom": 10,
  "paddingLeft": 10,

  "tempPadding": 10,
  "tempPaddingTop": 10,
  "tempPaddingRight": 10,
  "tempPaddingBottom": 10,
  "tempPaddingLeft": 10,

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

  "customClassName": "",

  "customCSS": "",

  "customID": "",

  "cssIDPopulation": "",
  "cssIDPopulationEntityType": "",
  "cssIDPopulationEntityId": "",

  "cssClassPopulation": "",
  "cssClassPopulationEntityType": "",
  "cssClassPopulationEntityId": "",

  "tabletColumnsHeightStyle": "auto",
  "tabletColumnsHeight": 400,
  "tabletColumnsHeightSuffix": "px",

  "tabletPaddingType": "ungrouped",
  "tempTabletPaddingType": "ungrouped",

  "tabletPadding": 0,
  "tabletPaddingTop": 0,
  "tabletPaddingRight": 0,
  "tabletPaddingBottom": 0,
  "tabletPaddingLeft": 0,

  "tempTabletPadding": 0,
  "tempTabletPaddingTop": 0,
  "tempTabletPaddingRight": 0,
  "tempTabletPaddingBottom": 0,
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

  "tabletMarginType": "grouped",
  "tabletMargin": 0,
  "tabletMarginTop": 10,
  "tabletMarginRight": 0,
  "tabletMarginBottom": 10,
  "tabletMarginLeft": 0,

  "tabletMarginSuffix": "px",
  "tabletMarginTopSuffix": "px",
  "tabletMarginRightSuffix": "px",
  "tabletMarginBottomSuffix": "px",
  "tabletMarginLeftSuffix": "px",

  "tempTabletMarginType": "grouped",
  "tempTabletMargin": 0,
  "tempTabletMarginTop": 10,
  "tempTabletMarginRight": 0,
  "tempTabletMarginBottom": 10,
  "tempTabletMarginLeft": 0,

  "tempTabletMarginSuffix": "px",
  "tempTabletMarginTopSuffix": "px",
  "tempTabletMarginRightSuffix": "px",
  "tempTabletMarginBottomSuffix": "px",
  "tempTabletMarginLeftSuffix": "px",

  "mobileReverseColumns": "off",

  "mobileColumnsHeightStyle": "auto",
  "mobileColumnsHeight": 400,
  "mobileColumnsHeightSuffix": "px",

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

  "mobileMarginType": "grouped",
  "mobileMargin": 0,
  "mobileMarginTop": 10,
  "mobileMarginRight": 0,
  "mobileMarginBottom": 10,
  "mobileMarginLeft": 0,

  "mobileMarginSuffix": "px",
  "mobileMarginTopSuffix": "px",
  "mobileMarginRightSuffix": "px",
  "mobileMarginBottomSuffix": "px",
  "mobileMarginLeftSuffix": "px",

  "tempMobileMarginType": "grouped",
  "tempMobileMargin": 0,
  "tempMobileMarginTop": 10,
  "tempMobileMarginRight": 0,
  "tempMobileMarginBottom": 10,
  "tempMobileMarginLeft": 0,

  "tempMobileMarginSuffix": "px",
  "tempMobileMarginTopSuffix": "px",
  "tempMobileMarginRightSuffix": "px",
  "tempMobileMarginBottomSuffix": "px",
  "tempMobileMarginLeftSuffix": "px",

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
  "mobileMotionMouseTiltEnabled": false
}
```

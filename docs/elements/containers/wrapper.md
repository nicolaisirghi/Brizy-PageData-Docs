---
sidebar_position: 6
---

# Wrapper

The `Wrapper` is a layout utility used to wrap and isolate a **single child element** such as `RichText`, `Image`, or `Map` within a layout. It allows additional styling and positioning (like background, padding, or margin) around that one element.

> **Note:** Unlike `Row` or `Column`, a `Wrapper` can contain only one item inside its `items` array.

---

## Structure

```json
{
  "type": "Wrapper",
  "value": {
    "_id": "wrapper-id",
    "horizontalAlign": "right",
    "items": [
      {
        "type": "Image",
        "value": {
          "_id": "image-id",
          "size": 33,
          "sizeSuffix": "%",
          "sizeType": "original"
        }
      }
    ]
  }
}
```

In the example above, the `Wrapper` contains a single `Image` element aligned to right. The `value` of the `Wrapper` can include additional properties like padding, margin, and alignment.
![Example Wrapper with Image Rendering](/img/wrapper-example.png)

## Properties

The `Wrapper` element supports a variety of properties that control its appearance, behavior, and layout. Below are the key properties you can use:

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

### Horizontal Align

The `horizontalAlign` property controls the horizontal alignment of the content within the wrapper. It can be set to "left", "center", or "right".

```json
{
  "horizontalAlign": "center"
}
```

### Z-Index

The `zIndex` property controls the stacking order of the wrapper relative to other elements. Higher values appear on top of lower values.

```json
{
  "zIndex": 10
}
```

### Styles key

The `styles` key is used to apply CSS classes to the `Wrapper` element.

It have two items:

- `wrapper` - for the `Wrapper` element
- `wrapper--[item-type]` - for the item type, it can be `image`

```json
{
  "_styles": ["wrapper"]
}
```

Example for Image:

```json
{
  "_styles": ["wrapper", "wrapper--image"]
}
```

Example for Text:

```json
{
  "_styles": ["wrapper", "wrapper--text"]
}
```

## DefaultValue for Wrapper

```json
{
  "items": [],

  "showToolbar": "off",

  "showOnDesktop": "on",

  "zIndex": 0,
  "zIndexSuffix": "",

  "showOnTablet": "on",

  "showOnMobile": "on",

  "elementPosition": "relative",

  "offsetX": 0,
  "offsetXSuffix": "px",
  "offsetXAlignment": "left",

  "offsetY": 0,
  "offsetYSuffix": "px",
  "offsetYAlignment": "top",

  "className": "",

  "customAttributes": "",
  "customAttributesPopulation": "",
  "customAttributesPopulationEntityType": "",
  "customAttributesPopulationEntityId": "",

  "horizontalAlign": "center",

  "animationName": "none",
  "animationDuration": 1000,
  "animationDelay": 1000,
  "animationInfiniteAnimation": false,

  "tempAnimationName": "none",

  "tabletAnimationName": "none",
  "tabletAnimationDuration": 1000,
  "tabletAnimationDelay": 1000,

  "tempTabletAnimationName": "none",

  "mobileAnimationName": "none",
  "mobileAnimationDuration": 1000,
  "mobileAnimationDelay": 1000,

  "tempMobileAnimationName": "none",

  "hoverName": "none",
  "hoverDuration": 600,
  "hoverDelay": 0,
  "hoverInfiniteAnimation": true,

  "width": 30,
  "widthSuffix": "%",
  "height": null,
  "heightSuffix": "%",

  "transformActive": false,

  "transformRotateDegree": "°",
  "transformRotateEnabled": false,
  "transformRotateRotate": 0,
  "transformRotateRotate3D": "off",
  "transformRotateRotateX": 0,
  "transformRotateRotateY": 0,
  "transformRotateRotatePerspective": 1000,

  "transformOffsetEnabled": false,
  "transformOffsetOffsetX": 0,
  "transformOffsetOffsetY": 0,

  "transformSkewEnabled": false,
  "transformSkewSkewX": 0,
  "transformSkewSkewY": 0,

  "transformScaleEnabled": false,
  "transformScaleScaleX": 0.1,
  "transformScaleScaleY": 0.1,
  "transformScaleScaleXY": 0.1,
  "transformScaleScalePreserveSize": false,

  "transformFlipEnabled": false,
  "transformFlipFlipHorizontal": false,
  "transformFlipFlipVertical": false,

  "transformAnchorPointX": "center",
  "transformAnchorPointY": "center",

  "paddingType": "grouped",
  "tempPaddingType": "grouped",

  "padding": 0,
  "paddingTop": 0,
  "paddingRight": 0,
  "paddingBottom": 0,
  "paddingLeft": 0,

  "tempPadding": 0,
  "tempPaddingTop": 0,
  "tempPaddingRight": 0,
  "tempPaddingBottom": 0,
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

  "marginType": "ungrouped",
  "margin": 0,
  "marginTop": 10,
  "marginRight": 0,
  "marginBottom": 10,
  "marginLeft": 0,

  "marginSuffix": "px",
  "marginTopSuffix": "px",
  "marginRightSuffix": "px",
  "marginBottomSuffix": "px",
  "marginLeftSuffix": "px",

  "tempMarginType": "ungrouped",
  "tempMargin": 0,
  "tempMarginTop": 10,
  "tempMarginRight": 0,
  "tempMarginBottom": 10,
  "tempMarginLeft": 0,

  "tempMarginSuffix": "px",
  "tempMarginTopSuffix": "px",
  "tempMarginRightSuffix": "px",
  "tempMarginBottomSuffix": "px",
  "tempMarginLeftSuffix": "px",

  "customClassName": "",

  "customID": "",

  "cssIDPopulation": "",
  "cssIDPopulationEntityType": "",
  "cssIDPopulationEntityId": "",

  "cssClassPopulation": "",
  "cssClassPopulationEntityType": "",
  "cssClassPopulationEntityId": "",

  "tabletPaddingType": "grouped",
  "tempTabletPaddingType": "grouped",

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

  "tabletMarginType": "ungrouped",
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

  "tempTabletMarginType": "ungrouped",
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

  "mobilePaddingType": "grouped",
  "tempMobilePaddingType": "grouped",

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

  "tempMobileMarginType": "ungrouped",
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

---
sidebar_position: 1
title: Introduction
---

# Introduction to Brizy API PageData

Welcome to the **Brizy API PageData** documentation. In just a few minutes, you'll understand how Brizy transforms content into fully-rendered pages using structured data.

## What is PageData?

Brizy's `PageData` is a **JSON structure** that represents the content and layout of a page. It is generated and managed through the **Brizy Editor**, which allows users to visually build their pages without writing code.

Behind the scenes, every element you add in the editor—whether it’s a heading, image, button, or layout block—is translated into a structured JSON object within the `PageData`.

## The Rendering Pipeline

The process from editor to webpage involves three key steps:

1. **Element Creation in the Editor**  
   Users interact with the Brizy Editor to design a page. Each component (e.g., text block, image, section) is internally represented as a JSON object with its own configuration and metadata.

2. **PageData Generation**  
   Once a page is saved, Brizy compiles all the elements into a single `PageData` JSON structure. This includes layout, styling, content, and relationships between components.

3. **React Rendering**  
   On the frontend, the `PageData` is **parsed and transformed into React components**. Each element in the JSON corresponds to a specific React component that knows how to interpret its configuration and render it appropriately on the page.

## Example Usage

Here’s a simplified example of what a snippet of `PageData` might look like:

```json
{
  "items": [
    {
      "type": "Section",
      "value": {
        "_styles": [
          "section"
        ],
        "items": [
          {
            "type": "SectionItem",
            "value": {
              "_styles": [
                "section-item"
              ],
              "items": [
                {
                  "type": "Wrapper",
                  "value": {
                    "_styles": [
                      "wrapper",
                      "wrapper--richText"
                    ],
                    "items": [
                      {
                        "type": "RichText",
                        "value": {
                          "_styles": [
                            "richText"
                          ],
                          "text": "<h1 class='brz-tp-heading1 brz-text-lg-center'><span class='brz-cp-color2'>Whiteboard seamless mindshare</span></h1>",
                          "_id": "hrrb35Dt8_sz"
                        }
                      }
                    ],
                    "_id": "kyLwBULma6Bb"
                  }
                },
                {
                  "type": "Wrapper",
                  "value": {
                    "_styles": [
                      "wrapper",
                      "wrapper--richText"
                    ],
                    "items": [
                      {
                        "type": "RichText",
                        "value": {
                          "_styles": [
                            "richText"
                          ],
                           "text": "<p class=\\\"brz-text-lg-center brz-tp-subtitle\\\"><span class=\\\"brz-cp-color7\\\"><span>If you are in the market for a computer, there are a number of factors to consider. Will it be used for your home, your office or perhaps even your home.</span></span></p>",
                           "_id": "q6H_PVZeAtrv"
                        }
                      }
                    ],
                    "paddingType": "ungrouped",
                    "paddingRightSuffix": "%",
                    "paddingRight": 22,
                    "padding": 0,
                    "paddingSuffix": "px",
                    "paddingLeftSuffix": "%",
                    "paddingLeft": 22,
                    "tabletPaddingType": "ungrouped",
                    "tabletPaddingRight": 100,
                    "tabletPadding": 0,
                    "tabletPaddingSuffix": "px",
                    "tabletPaddingLeft": 100,
                    "mobilePaddingType": "ungrouped",
                    "mobilePaddingRightSuffix": "px",
                    "mobilePaddingRight": 20,
                    "mobilePadding": 0,
                    "mobilePaddingSuffix": "px",
                    "mobilePaddingLeftSuffix": "px",
                    "mobilePaddingLeft": 20,
                    "_id": "spAfbBQ1oBWu"
                  }
                },
                {
                  "type": "Wrapper",
                  "value": {
                    "_styles": [
                      "wrapper",
                      "wrapper--spacer"
                    ],
                    "items": [
                      {
                        "type": "Spacer",
                        "value": {
                          "_styles": [
                            "spacer"
                          ],
                          "height": 30,
                          "mobileHeight": 20,
                          "tabletHeight": 20,
                          "_id": "jnlU76o1HEvC"
                        }
                      }
                    ],
                    "showOnTablet": "on",
                    "showOnMobile": "on",
                    "_id": "epGjWZHaPJQB"
                  }
                },
                {
                  "type": "Cloneable",
                  "value": {
                    "_styles": [
                      "wrapper-clone",
                      "wrapper-clone--button"
                    ],
                    "items": [
                      {
                        "type": "Button",
                        "value": {
                          "_styles": [
                            "button"
                          ],
                          "text": "Watch VideoÂ  Â  Â  Â ",
                          "iconName": "small-triangle-right",
                          "iconType": "glyph",
                          "iconPosition": "left",
                          "fillType": "outline",
                          "tempFillType": "outline",
                          "paddingRL": 42,
                          "paddingRight": 42,
                          "paddingLeft": 42,
                          "paddingTB": 14,
                          "paddingTop": 14,
                          "paddingBottom": 14,
                          "borderRadiusType": "custom",
                          "borderRadius": 4,
                          "borderWidth": 2,
                          "borderColorOpacity": 1,
                          "borderColorPalette": "color2",
                          "bgColorOpacity": 0,
                          "bgColorPalette": "color3",
                          "hoverBgColorOpacity": 1,
                          "hoverBorderColorOpacity": 0.8,
                          "tempBorderRadiusType": "custom",
                          "colorPalette": "color2",
                          "colorOpacity": 1,
                          "tempBorderColorPalette": "color2",
                          "hoverBgColorPalette": "color2",
                          "hoverBorderColorPalette": "color2",
                          "tempHoverBorderColorPalette": "color3",
                          "hoverBgColorHex": "#1c1c1c",
                          "tempHoverBgColorOpacity": 1,
                          "tempHoverBgColorPalette": "color3",
                          "hoverBorderColorHex": "#1c1c1c",
                          "iconSize": "custom",
                          "iconCustomSize": 25,
                          "tempBorderRadius": 4,
                          "hoverTransition": 30,
                          "_id": "ozl2iZbLHCFt"
                        }
                      }
                    ],
                    "_id": "crXsSizEOaTy"
                  }
                },
                {
                  "type": "Wrapper",
                  "value": {
                    "_styles": [
                      "wrapper",
                      "wrapper--spacer"
                    ],
                    "items": [
                      {
                        "type": "Spacer",
                        "value": {
                          "_styles": [
                            "spacer"
                          ],
                          "height": 40,
                          "tabletHeight": 10,
                          "mobileHeight": 20,
                          "_id": "cojBs9idyjUM"
                        }
                      }
                    ],
                    "showOnTablet": "on",
                    "showOnMobile": "on",
                    "_id": "yakTOY4sKyXv"
                  }
                },
                {
                  "type": "Wrapper",
                  "value": {
                    "_styles": [
                      "wrapper",
                      "wrapper--image"
                    ],
                    "items": [
                      {
                        "type": "Image",
                        "value": {
                          "_styles": [
                            "image"
                          ],
                          "imageWidth": 2364,
                          "imageHeight": 692,
                          "imageSrc": "d03-Browser.png",
                          "height": 100,
                          "positionX": 50,
                          "positionY": 50,
                          "imagePopulation": "",
                          "_id": "zYo2zB1SUWip"
                        }
                      }
                    ],
                    "marginBottomSuffix": "px",
                    "marginBottom": 0,
                    "margin": 0,
                    "marginSuffix": "px",
                    "tabletMarginBottom": 0,
                    "tabletMargin": 0,
                    "tabletMarginSuffix": "px",
                    "_id": "j3KpVh2T5zhO"
                  }
                }
              ],
              "paddingType": "ungrouped",
              "paddingTop": 110,
              "paddingBottom": 0,
              "padding": 75,
              "tabsCurrentElement": "",
              "tabsState": "tabNormal",
              "tabsColor": "tabOverlay",
              "bgImageWidth": 1920,
              "bgImageHeight": 1067,
              "bgImageSrc": "d03-moden-wall.jpg",
              "bgColorOpacity": 0,
              "tempBgColorOpacity": 1,
              "borderRadius": 0,
              "borderTopLeftRadius": 0,
              "borderTopRightRadius": 0,
              "borderBottomLeftRadius": 0,
              "borderBottomRightRadius": 0,
              "tempBorderTopLeftRadius": 0,
              "tempBorderTopRightRadius": 0,
              "tempBorderBottomLeftRadius": 0,
              "tempBorderBottomRightRadius": 0,
              "tabletPaddingType": "ungrouped",
              "tabletPaddingTop": 50,
              "tabletPaddingBottom": 0,
              "tabletPadding": 50,
              "mobileBgPositionX": 65,
              "mobileBgPositionY": 46,
              "mobileBorderRadius": 0,
              "_id": "gAHeWLsM4nq3"
            }
          }
        ],
        "_id": "wKniDFhVVfLx",
        "_thumbnailSrc": 20776451,
        "_thumbnailWidth": 600,
        "_thumbnailHeight": 195,
        "_thumbnailTime": 1749790937516
      },
      "blockId": "block2460light"
    }
  ]
}
```

This JSON structure defines a **section** composed of multiple elements such as **rich text**, **buttons**, and **images**—each configured with its own styles and properties.
When rendered in the UI, the `PageData` structure visually appears like this:
![Example PageData Rendering](/img/section-example.png)

Each component in the layout is mapped from the JSON data and rendered dynamically using React, making the interface both flexible and modular.

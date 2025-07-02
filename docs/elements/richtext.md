---
sidebar_position: 9
---

# RichText

The `RichText` element is used to display formatted text content, including headings, paragraphs, links, lists, and
more.

## Example

```json
{
  "type": "RichText",
  "value": {
    "_id": "unique-id",
    "html": "<p class=\"brz-tp-lg-paragraph\" data-uniq-id=\"eJfVa\" data-generated-css=\"brz-css-zb6vh\"><span class=\"brz-cp-color7\">The point of using dummy text for your paragrcaph is that it has a more-or-less normal distribution of letters. making it look like readable English.</span></p>"
  }
}
```

![Example Text](/img/text-example.png)

> **⚠️ Note:**  
> Our `RichText` element is **highly complex** and follows a custom formatting system that may be difficult to
> understand at first. It uses internal `formats`, handles links in a special way, and has strict structure rules.  
> If you're unsure how to work with it or need more advanced examples, please **reach out to me directly** for support.

## Structure

The `Brizy RichText` component follows a strict structure and set of rules to ensure consistent behavior and formatting.
Below, we explain these rules step by step:

---

### Allowed Tags and Hierarchy

Each line or block within the RichText is wrapped by a **parent tag**, referred to as the `wrapper tag`. The most common
`wrapper tags` are:

- Paragraphs: `<p>`
- Headings: `<h1>` to `<h6>`
- Preformatted Text: `<pre>`
- List Items: `<li>` (used inside lists)

> ⚠️ **Important:** RichText does **not** support certain HTML tags like `<div>`, `<table>`, etc. Using unsupported tags
> may break the structure or prevent RichText from functioning properly.

---

#### Lists

For list structures:

- Ordered Lists use: `<ol>`
- Unordered Lists use: `<ul>`
- Each list item is wrapped inside: `<li>`

**Example:**

```html
<ul>
  <li>List Item 1</li>
  <li>List Item 2</li>
</ul>
```

---

#### Content Inside Wrapper Tags

Inside every valid `wrapper tag` (`<p>`, `<h1>` - `<h6>`, `<pre>`, `<li>`), the immediate descendants must follow these
rules:

- **Normal Text**: Wrapped inside a `<span>` tag
- **Links**: Wrapped inside an `<a>` tag

**Valid Example:**

```html
<p>
  <span>This is normal text</span>
  <a data-href="{{link-encoded}}">This is a link</a>
</p>
```

**Incorrect Example (Unsupported Tags):**

```html
<div>
  <span>Text inside a div - Invalid</span>
</div>
```

---

#### Summary of Supported Tags

| Tag             | Purpose                   |
| --------------- | ------------------------- |
| `<p>`           | Paragraph wrapper         |
| `<h1>` - `<h6>` | Headings wrapper          |
| `<pre>`         | Preformatted text wrapper |
| `<ul>` / `<ol>` | List wrappers             |
| `<li>`          | Individual list items     |
| `<span>`        | Regular inline text       |
| `<a>`           | Links                     |

---

### Custom Classes

Since RichText supports advanced formatting (such as per-word color and style changes), we apply custom class names to the wrapper tag of each text row.

Some classes may include **device-specific suffixes**, allowing different styles per device:

- `lg` — Desktop
- `sm` — Tablet
- `xs` — Mobile

#### Common Class Patterns

- `brz-ff-[value]` — Sets the `font-family`.
  _Example:_ `brz-ff-noto_sans` → `font-family: "Noto Sans";`

- `brz-ft-[value]` — Defines the font source.
  _Possible values:_ `google`, `upload`, `system`

- `brz-fw-[device]-[value]` — Font weight for the specified device.
  _Example:_ `brz-fw-lg-400` → `font-weight: 400;` (Desktop)

- `brz-fs-[device]-[value]` — Font size for the specified device.
  _Example:_ `brz-fs-xs-14` → `font-size: 14px;` (Mobile)

- `brz-fss-[device]-[value]` — Font size suffix unit.
  _Example:_ `brz-fss-lg-rem brz-fs-lg-2` → `font-size: 2rem;`

- `brz-lh-[device]-[value]` — Line height for the specified device.
  _Example:_ `brz-lh-lg-2` → `line-height: 2;`

- `brz-ls-[device]-[value]` — Letter spacing for the specified device.
  _Example:_ `brz-ls-sm-10` → `letter-spacing: 10px;`

#### Notes on Decimal Values

For properties like `font-size`, `line-height`, and `letter-spacing`, you can use decimal values.
**Decimal Format:** Replace the decimal point with an underscore (`_`).

_Example:_
`brz-lh-lg-1_5` → `line-height: 1.5;`
`brz-fs-xs-1_25` → `font-size: 1.25px;`

### Colors

RichText supports applying both color and background-color styles to text content. These styles must be applied as inline styles directly on the child elements (`<span>` or `<a>` tags) using the rgb format.

_Example:_
To set white text with a black background, your RichText JSON should look like this:

```json
{
  "text": "<p><span style=\"color: rgb(255, 255, 255); background-color: rgb(0, 0, 0);\">Some text</span></p>"
}
```

![Example](/img/richtext-color-example.png)

### Links

To create links within RichText, the text must be wrapped inside an `<a>` tag. However, instead of using the standard `href` attribute, RichText uses a custom `data-href` attribute.

The `data-href` value should contain the link in Brizy's specific encoded format.

**Example:**

```html
<p>
  <a data-href="{Brizy link encoded value}">Click here</a>
</p>
```

For more details on how to structure the link value, refer to the [Links section](#link).

---

## Key Properties

### Text and Typography

- `text`: The text content of the element in HTML format (e.g., `<p>Your text here</p>`).
- `typographyFontFamily`: The font family of the text, which can be a specific font name (e.g., `"Arial"`, `"Roboto"`)
  or a generic family (e.g., `"serif"`, `"sans-serif"`).
- `typographyFontFamilyType`: The type of font family, which can be `"system"`, `"google"`, or `"upload"`.
- `typographyFontSize`: The font size of the text, defined as a number in pixels (e.g., `16`).
- `typographyFontSizeSuffix`: The suffix for the font size, typically `"px"` (e.g., `"px"`).
- `typographyFontWeight`: The font weight of the text, which can be a number (e.g., `400`, `700`). Note the font should
  have the weight defined in the font file.
- `typographyFontStyle`: If is set then it will apply the font from the global font settings like the colorPalette. Set
  to empty string for no font style.
- `typographyLetterSpacing`: The letter spacing of the text, defined as a number in pixels (e.g., `1.5`).
- `typographyLineHeight`: The line height of the text, defined as a number in pixels (e.g., `1.5`).
- `typographyBold`: Whether the button text is bold (`true`, `false`).
- `typographyItalic`: Whether the button text is italic (`true`, `false`).
- `typographyUnderline`: Whether the button text is underlined (`true`, `false`).
- `typographyStrike:`: Whether the button text has a strikethrough (`true`, `false`).
- `typographyUpercase`: Whether the button text is displayed in uppercase (`true`, `false`).
- `typographyLowercase`: Whether the button text is displayed in lowercase (`true`, `false`).

### Colors

- `bgColorHex`: The text color in hexadecimal format (e.g., `#FF5733`).
- `bgColorOpacity`: The opacity of the text color, ranging from `0` (transparent) to `1` (opaque).
- `bgColorPalette`: A predefined color palette option for quick selection. Set to empty string for no palette.
- `bgColorType`: The type of text color, which can be `solid`, `gradient`, or `none`.

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

- `textBgColorHex`: The background color of the text in hexadecimal format.
- `textBgColorOpacity`: The opacity of the text background color, ranging from `0` (transparent) to `1` (opaque).
- `textBgColorPalette`: A predefined background color palette option for quick selection. Set to empty string for no
  palette.
- `textBgColorType`: The type of background color, which can be `solid`, `gradient`, or `none`.

- `textGradientActivePointer`: Pointer to the active gradient for the text background.
- `textGradientColorHex`: Hexadecimal color for the text background gradient.
- `textGradientColorOpacity`: Opacity of the text background gradient color.
- `textGradientColorPalette`: Named palette value for the text background gradient color. If not set, it defaults to an
  empty string. It
  should be set to empty string if no palette is used.
- `textGradientFinishPointer`: Pointer to the gradient finish color for the text background.
- `textGradientStartPointer`: Pointer to the gradient start color for the text background.
- `textGradientLinearDegree`: Degree of the linear gradient for the text background (0-360).
- `textGradientRadialDegree`: Degree of the radial gradient for the text background (0-360).
- `textGradientType`: Type of gradient for the text background ("linear", "radial"). Defaults to "linear" if not set.

- `textShadowColorHex`: The color of the text shadow in hexadecimal format.
- `textShadowColorOpacity`: The opacity of the text shadow color, ranging from `0` (transparent) to `1` (opaque).
- `textShadowColorPalette`: A predefined color palette option for the text shadow. Set to empty string for no palette.
- `textShadowVertical`: The vertical offset of the text shadow, defined as a number in pixels (e.g., `2`).
- `textShadowHorizontal`: The horizontal offset of the text shadow, defined as a number in pixels (e.g., `2`).
- `textShadowBlur`: The blur radius of the text shadow, defined as a number in pixels (e.g., `4`).

### Link

The `RichText` element supports linking functionality, enabling the entire text block to behave as a clickable link.
This is especially useful for making sections of content interactive or redirecting users to external or internal
destinations.

---

#### How to Define a Link

For the `RichText` element, the `link` key must contain a **stringified and URI-encoded** JSON object that describes the
link's behavior and destination.

This allows precise control over how and where the link operates.

---

#### Supported Link Properties

The link object can include the following keys:

| Key             | Description                                                                                   |
| --------------- | --------------------------------------------------------------------------------------------- |
| `type`          | The type of link. Supported values: `"external"`, `"page"`, `"anchor"`, `"popup"`, `"upload"` |
| `external`      | The external URL (e.g., `"https://example.com"`)                                              |
| `externalBlank` | Whether to open the link in a new tab (`"on"` or `"off"`)                                     |
| `externalRel`   | Whether to mark the link as `rel="nofollow"` (`"on"` or `"off"`)                              |
| `externalType`  | Type of external link (`"external"` or `"linkPopulation"`)                                    |

---

#### Example: External Link to Google

To add a link to a `RichText` element:

1. **Create** a JSON object describing the link.
2. **Stringify** the object using `JSON.stringify(...)`.
3. **Encode** the resulting string using `encodeURIComponent(...)`.
4. Assign the encoded string to the `link` key inside the `RichText` value.

Here is the JSON representation of a link to [https://google.com](https://google.com):

```json
{
  "external": "https://google.com",
  "externalBlank": "on",
  "externalRel": "off",
  "type": "external",
  "externalType": "external"
}
```

The encoded object would look like this:

```json
{
  "link": "%7B%22external%22%3A%22https%3A%2F%2Fgoogle.com%22%2C%22externalBlank%22%3A%22on%22%2C%22externalRel%22%3A%22off%22%2C%22type%22%3A%22external%22%2C%22externalType%22%3A%22external%22%7D"
}
```

## DefaultValue for RichText

```json
{
  "text": "<p class='brz-tp-paragraph'><span class='brz-cp-color7'>The point of using dummy text for your paragraph is that it has a more-or-less normal distribution of letters. making it look like readable English.</span></p>",
  "textPopulation": "",
  "textPopulationEntityType": "",
  "textPopulationEntityId": "",
  "popups": [],
  "offsetX": 0,
  "offsetY": 0,
  "bgImageExtension": "",
  "bgImageFileName": null,
  "bgImageSrc": "",
  "blendMode": "normal",
  "customCSS": "",
  "numberOfLines": 0,
  "numberOfLinesSuffix": "",
  "width": 100,
  "widthSuffix": "%",
  "media": "image",
  "bgSizeType": "custom",
  "dynamicTextCapitalize": "off",
  "bgImageWidth": 0,
  "bgImageHeight": 0,
  "bgImageType": "internal",
  "bgAlt": "",
  "bgPositionX": 50,
  "bgPositionY": 50,
  "bgPopulation": "",
  "bgPopulationEntityType": "",
  "bgPopulationEntityId": "",
  "bold": false,
  "italic": false,
  "underline": false,
  "strike": false,
  "capitalize": false,
  "script": "",
  "contentHorizontalAlign": "left",
  "typographyFontFamily": "lato",
  "tabletTypographyFontFamily": null,
  "mobileTypographyFontFamily": null,
  "h1FontFamily": "lato",
  "tabletH1FontFamily": null,
  "mobileH1FontFamily": null,
  "h2FontFamily": "lato",
  "tabletH2FontFamily": null,
  "mobileH2FontFamily": null,
  "h3FontFamily": "lato",
  "tabletH3FontFamily": null,
  "mobileH3FontFamily": null,
  "h4FontFamily": "lato",
  "tabletH4FontFamily": null,
  "mobileH4FontFamily": null,
  "h5FontFamily": "lato",
  "tabletH5FontFamily": null,
  "mobileH5FontFamily": null,
  "h6FontFamily": "lato",
  "tabletH6FontFamily": null,
  "mobileH6FontFamily": null,
  "typographyFontStyle": "",
  "typographyFontFamilyType": "google",
  "typographyFontSize": 16,
  "typographyFontSizeSuffix": "px",
  "typographyFontWeight": 400,
  "typographyLineHeight": 1.3,
  "typographyLetterSpacing": 0,
  "typographyVariableFontWeight": 400,
  "typographyFontWidth": 100,
  "typographyFontSoftness": 0,
  "typographyBold": false,
  "typographyItalic": false,
  "typographyUnderline": false,
  "typographyStrike": false,
  "typographyUppercase": false,
  "typographyLowercase": false,
  "typographyScript": "",
  "h1FontStyle": "heading1",
  "h1FontFamilyType": "google",
  "h1FontSize": 16,
  "h1FontSizeSuffix": "px",
  "h1FontWeight": 400,
  "h1LineHeight": 1.3,
  "h1LetterSpacing": 0,
  "h1VariableFontWeight": 400,
  "h1FontWidth": 100,
  "h1FontSoftness": 0,
  "h1Bold": false,
  "h1Italic": false,
  "h1Underline": false,
  "h1Strike": false,
  "h1Uppercase": false,
  "h1Lowercase": false,
  "h1Script": "",
  "h2FontStyle": "heading2",
  "h2FontFamilyType": "google",
  "h2FontSize": 16,
  "h2FontSizeSuffix": "px",
  "h2FontWeight": 400,
  "h2LineHeight": 1.3,
  "h2LetterSpacing": 0,
  "h2VariableFontWeight": 400,
  "h2FontWidth": 100,
  "h2FontSoftness": 0,
  "h2Bold": false,
  "h2Italic": false,
  "h2Underline": false,
  "h2Strike": false,
  "h2Uppercase": false,
  "h2Lowercase": false,
  "h2Script": "",
  "h3FontStyle": "heading3",
  "h3FontFamilyType": "google",
  "h3FontSize": 16,
  "h3FontSizeSuffix": "px",
  "h3FontWeight": 400,
  "h3LineHeight": 1.3,
  "h3LetterSpacing": 0,
  "h3VariableFontWeight": 400,
  "h3FontWidth": 100,
  "h3FontSoftness": 0,
  "h3Bold": false,
  "h3Italic": false,
  "h3Underline": false,
  "h3Strike": false,
  "h3Uppercase": false,
  "h3Lowercase": false,
  "h3Script": "",
  "h4FontStyle": "heading4",
  "h4FontFamilyType": "google",
  "h4FontSize": 16,
  "h4FontSizeSuffix": "px",
  "h4FontWeight": 400,
  "h4LineHeight": 1.3,
  "h4LetterSpacing": 0,
  "h4VariableFontWeight": 400,
  "h4FontWidth": 100,
  "h4FontSoftness": 0,
  "h4Bold": false,
  "h4Italic": false,
  "h4Underline": false,
  "h4Strike": false,
  "h4Uppercase": false,
  "h4Lowercase": false,
  "h4Script": "",
  "h5FontStyle": "heading5",
  "h5FontFamilyType": "google",
  "h5FontSize": 16,
  "h5FontSizeSuffix": "px",
  "h5FontWeight": 400,
  "h5LineHeight": 1.3,
  "h5LetterSpacing": 0,
  "h5VariableFontWeight": 400,
  "h5FontWidth": 100,
  "h5FontSoftness": 0,
  "h5Bold": false,
  "h5Italic": false,
  "h5Underline": false,
  "h5Strike": false,
  "h5Uppercase": false,
  "h5Lowercase": false,
  "h5Script": "",
  "h6FontStyle": "heading6",
  "h6FontFamilyType": "google",
  "h6FontSize": 16,
  "h6FontSizeSuffix": "px",
  "h6FontWeight": 400,
  "h6LineHeight": 1.3,
  "h6LetterSpacing": 0,
  "h6VariableFontWeight": 400,
  "h6FontWidth": 100,
  "h6FontSoftness": 0,
  "h6Bold": false,
  "h6Italic": false,
  "h6Underline": false,
  "h6Strike": false,
  "h6Uppercase": false,
  "h6Lowercase": false,
  "h6Script": "",
  "colorHex": "",
  "colorOpacity": 1,
  "colorPalette": "color7",
  "gradientActivePointer": "startPointer",
  "gradientStartPointer": 0,
  "gradientFinishPointer": 100,
  "gradientType": "linear",
  "gradientLinearDegree": 90,
  "gradientRadialDegree": 90,
  "gradientColorHex": "#009900",
  "gradientColorOpacity": 1,
  "gradientColorPalette": "",
  "tempColorOpacity": 1,
  "tempColorPalette": "color7",
  "tempGradientColorOpacity": 1,
  "tempGradientColorPalette": "",
  "textGradientActivePointer": "startPointer",
  "textGradientStartPointer": 0,
  "textGradientFinishPointer": 100,
  "textGradientType": "linear",
  "textGradientLinearDegree": 90,
  "textGradientRadialDegree": 90,
  "textGradientColorHex": "#009900",
  "textGradientColorOpacity": 1,
  "textGradientColorPalette": "",
  "textBgColorType": "none",
  "textBgColorHex": "",
  "textBgColorOpacity": 0,
  "textBgColorPalette": "",
  "tempTextColorOpacity": 1,
  "tempTextColorPalette": "color7",
  "tempTextGradientColorOpacity": 1,
  "tempTextGradientColorPalette": "",
  "tempTextBgColorType": "solid",
  "colorType": "solid",
  "tag": "p",
  "textShadowColorHex": "#000000",
  "textShadowColorOpacity": 0,
  "textShadowColorPalette": "",
  "tempTextShadowColorOpacity": 1,
  "tempTextShadowColorPalette": "",
  "textShadowBlur": 4,
  "textShadowVertical": 2,
  "textShadowHorizontal": 1,
  "tempTextShadowBlur": 4,
  "tempTextShadowVertical": 2,
  "bgColorHex": "",
  "bgColorOpacity": 1,
  "bgColorPalette": "color7",
  "bgColorType": "solid",
  "tempBgColorType": "solid",
  "tempBgColorOpacity": 1,
  "tempBgColorPalette": "color7",
  "tempTextShadowHorizontal": 1,
  "tabletTypographyFontStyle": null,
  "tabletTypographyFontFamilyType": null,
  "tabletTypographyFontSize": null,
  "tabletTypographyFontSizeSuffix": "px",
  "tabletTypographyFontWeight": null,
  "tabletTypographyLineHeight": null,
  "tabletTypographyLetterSpacing": null,
  "tabletH1FontStyle": null,
  "tabletH1FontFamilyType": null,
  "tabletH1FontSize": null,
  "tabletH1FontSizeSuffix": "px",
  "tabletH1FontWeight": null,
  "tabletH1LineHeight": null,
  "tabletH1LetterSpacing": null,
  "tabletH2FontStyle": null,
  "tabletH2FontFamilyType": null,
  "tabletH2FontSize": null,
  "tabletH2FontSizeSuffix": "px",
  "tabletH2FontWeight": null,
  "tabletH2LineHeight": null,
  "tabletH2LetterSpacing": null,
  "tabletH3FontStyle": null,
  "tabletH3FontFamilyType": null,
  "tabletH3FontSize": null,
  "tabletH3FontSizeSuffix": "px",
  "tabletH3FontWeight": null,
  "tabletH3LineHeight": null,
  "tabletH3LetterSpacing": null,
  "tabletH4FontStyle": null,
  "tabletH4FontFamilyType": null,
  "tabletH4FontSize": null,
  "tabletH4FontSizeSuffix": "px",
  "tabletH4FontWeight": null,
  "tabletH4LineHeight": null,
  "tabletH4LetterSpacing": null,
  "tabletH5FontStyle": null,
  "tabletH5FontFamilyType": null,
  "tabletH5FontSize": null,
  "tabletH5FontSizeSuffix": "px",
  "tabletH5FontWeight": null,
  "tabletH5LineHeight": null,
  "tabletH5LetterSpacing": null,
  "tabletH6FontStyle": null,
  "tabletH6FontFamilyType": null,
  "tabletH6FontSize": null,
  "tabletH6FontSizeSuffix": "px",
  "tabletH6FontWeight": null,
  "tabletH6LineHeight": null,
  "tabletH6LetterSpacing": null,
  "mobileTypographyFontStyle": null,
  "mobileTypographyFontFamilyType": null,
  "mobileTypographyFontSize": null,
  "mobileTypographyFontSizeSuffix": "px",
  "mobileTypographyFontWeight": null,
  "mobileTypographyLineHeight": null,
  "mobileTypographyLetterSpacing": null,
  "mobileH1FontStyle": null,
  "mobileH1FontFamilyType": null,
  "mobileH1FontSize": null,
  "mobileH1FontSizeSuffix": "px",
  "mobileH1FontWeight": null,
  "mobileH1LineHeight": null,
  "mobileH1LetterSpacing": null,
  "mobileH2FontStyle": null,
  "mobileH2FontFamilyType": null,
  "mobileH2FontSize": null,
  "mobileH2FontSizeSuffix": "px",
  "mobileH2FontWeight": null,
  "mobileH2LineHeight": null,
  "mobileH2LetterSpacing": null,
  "mobileH3FontStyle": null,
  "mobileH3FontFamilyType": null,
  "mobileH3FontSize": null,
  "mobileH3FontSizeSuffix": "px",
  "mobileH3FontWeight": null,
  "mobileH3LineHeight": null,
  "mobileH3LetterSpacing": null,
  "mobileH4FontStyle": null,
  "mobileH4FontFamilyType": null,
  "mobileH4FontSize": null,
  "mobileH4FontSizeSuffix": "px",
  "mobileH4FontWeight": null,
  "mobileH4LineHeight": null,
  "mobileH4LetterSpacing": null,
  "mobileH5FontStyle": null,
  "mobileH5FontFamilyType": null,
  "mobileH5FontSize": null,
  "mobileH5FontSizeSuffix": "px",
  "mobileH5FontWeight": null,
  "mobileH5LineHeight": null,
  "mobileH5LetterSpacing": null,
  "mobileH6FontStyle": null,
  "mobileH6FontFamilyType": null,
  "mobileH6FontSize": null,
  "mobileH6FontSizeSuffix": "px",
  "mobileH6FontWeight": null,
  "mobileH6LineHeight": null,
  "mobileH6LetterSpacing": null,
  "linkPage": "",
  "linkPageTitle": "",
  "linkPageSource": null,
  "linkInternalBlank": "off",
  "linkSource": "",
  "linkType": "external",
  "linkExternal": "",
  "linkAnchor": "",
  "linkExternalBlank": "off",
  "linkExternalRel": "off",
  "linkExternalType": "linkExternal",
  "linkPopulation": "",
  "linkExternalPopulation": "",
  "linkPopulationEntityType": "",
  "linkPopulationEntityId": "",
  "linkUpload": "",
  "linkPopup": "",
  "actionClosePopup": "off",
  "linkToSlide": 1
}
```

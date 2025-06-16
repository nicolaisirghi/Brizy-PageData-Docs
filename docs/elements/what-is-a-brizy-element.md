---
sidebar_position: 0
---

# What is a Brizy Element?

A **Brizy Element** is a modular building block used to construct pages in the Brizy editor. Think of it like a widget: it can be a text block, button, image, video, spacer, form, or even an entire section. These elements are defined using JSON and rendered dynamically as React components in the frontend.

Each element follows a consistent structure in the `PageData` schema and **must include two required keys**:

### 1. `type` (string)

This is a string identifier that defines **what kind of element** it is. Examples include:

- `"Section"`
- `"Wrapper"`
- `"RichText"`
- `"Button"`
- `"Image"`
- `"Spacer"`

The `type` tells the renderer which React component to use when parsing and displaying this part of the page.

### 2. `value` (object)

This key contains the **configuration data** for the element. It includes:

- **Styles:** CSS classes or Brizy-specific style flags under the `_styles` key.
- **Nested elements:** Some elements like `Wrapper` or `Section` can contain an `items` array to hold child elements.
- **Content:** Text content (`text` for `RichText`), image paths (`imageSrc` for `Image`), or button labels (`text` for `Button`).
- **Layout & spacing:** Padding, margin, alignment, width, height, responsiveness, etc.
- **Behavioral props:** Like `iconPosition`, `fillType`, or conditional visibility (`showOnMobile`, `showOnTablet`).

> ⚠️ **Important:** Every `value` object must include an `_id` key (a unique string identifier).  
> Without `_id`, the editor will crash when rendering the element. This applies to all elements, containers, and nested children.

---

## Default Values

Every Brizy element has its own **default value** schema defined in the editor.  
This means you **don’t need to provide the full set of keys** when defining an element—only the properties you want to override or change.

When rendering the page, Brizy will **automatically fill in any missing keys** with the default values for that specific element.

> 📌 At the **bottom of each element’s documentation page**, you’ll find the full default value JSON used by the editor for that element. This helps you understand which keys are optional and what values are assumed if omitted.

---

## Responsive Design in Brizy

Brizy is a **fully responsive editor**. Many style options can be customized **independently** for desktop, tablet, and mobile views.  
To apply different values for each device, you use **prefixes** for the key names:

### Device-Specific Prefixes

- **Desktop:** No prefix (default)  
  Example: `paddingTop`, `fontSize`
- **Tablet:** Add `tablet` prefix  
  Example: `tabletPaddingTop`, `tabletFontSize`
- **Mobile:** Add `mobile` prefix  
  Example: `mobilePaddingTop`, `mobileFontSize`

This allows you to fine-tune the layout and typography for each device viewport individually.

---

### Hover States

To define **hover styles**, you also use prefixed keys, but **only for desktop** (tablet and mobile do not support hover):

- `colorHex` → `hoverColorHex`
- `bgColorHex` → `hoverBgColorHex`
- `borderColorHex` → `hoverBorderColorHex`

This allows you to change styling when the user hovers with their mouse on desktop devices.

---

## Summary

- Brizy Elements are JSON-defined UI blocks.
- Every element has a `type` and `value`.
- `value` must include an `_id`.
- Brizy supports responsive and hover styling via suffixes.
- You only need to define keys you want to customize—defaults are filled in automatically.
- Complex layouts are built by nesting elements using the `items` array.

This structured format allows Brizy to offer a flexible and consistent editing experience while maintaining clear separation between content, layout, and style.

---

### What's Next

In the next sections, we’ll explore each Brizy element in detail—one by one. You’ll learn what each `type` represents, what keys are expected in their `value` objects, how defaults are handled, and how they are rendered on the page.

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

Together, `type` and `value` allow you to describe both **what** an element is and **how** it should look and behave.

### Summary

- Brizy Elements are JSON-defined UI blocks.
- Every element has a `type` and `value`.
- `type` defines what it is.
- `value` defines how it looks, behaves, and what children it contains.
- Complex layouts are built by nesting elements inside each other using the `items` array.

This structured format allows Brizy to offer a flexible and consistent editing experience while maintaining clear separation between content, layout, and style.


### What's Next

In the next sections, we’ll explore each Brizy element in detail—one by one. You’ll learn what each `type` represents, what keys are expected in their `value` objects, and how they are rendered on the page.

This will help you better understand how to work with `PageData`, customize layouts, and even build your own custom elements if needed.
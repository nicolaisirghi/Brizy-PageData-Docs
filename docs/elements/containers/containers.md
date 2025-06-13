---
id: containers
title: Containers
sidebar_position: 0
---

# Containers

Containers are a fundamental and powerful element in Brizy that allow you to create flexible, organized, and responsive layouts for your web pages. They act as structural building blocks that help you group multiple elements together, manage their positioning, spacing, and styling in a consistent way. By using containers, you can easily control the visual hierarchy and layout flow of your content, making your designs both modular and adaptable across different screen sizes.

### Structure of Containers

Every container element in Brizy holds **multiple child elements** inside it. These children are stored in the container’s `items` key, which is explicitly **inside the container’s `value` key**. The `items` key contains an **array of elements**. Each element inside this array follows the familiar pattern of having two required keys:

- **type**: the identifier of the element type (e.g., "RichText", "Image", "Button")
- **value**: an object containing all the properties and settings of that element, including potentially its own nested `items`

This nested structure allows containers to be recursive, meaning containers can hold other containers or simple elements, enabling complex and deeply nested layouts.

### Common Container Types in Brizy

Brizy provides several specialized container elements that are commonly used to build layouts:

- **Row**: A horizontal container that groups columns or other elements, often used for grid-like layouts.
- **Column**: A vertical container that sits inside a row, used to divide rows into multiple vertical sections.
- **Section**: A top-level container representing large blocks or sections of a page, often spanning full width.
- **Wrapper**: A generic container that wraps around other elements to group and apply styles.
- **Cloneable**: A special container that allows the content inside it to be duplicated or repeated, useful for reusable blocks. The elements inside a Cloneable container are limited to Buttons and Icons.
- **Menu**: A container for navigation elements.
- **SectionHeader**: A container typically used for the top part of a section, like titles or introductory content.
- **SectionFooter**: A container used at the bottom of a section for footers or concluding content.

---

Using these container elements effectively is key to mastering page structure in Brizy, allowing you to build both simple and complex responsive designs with ease.

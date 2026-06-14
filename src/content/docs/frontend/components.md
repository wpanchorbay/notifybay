---
title: Component Libraries
description: Using the common and classics UI components.
---

NotifyBay provides two distinct sets of React components depending on the aesthetic you want to achieve.

## The `common` Library

Found in `src/components/common/`, this library contains over 30 modern, Tailwind-styled UI components. 

These are ideal if you want your plugin to look like a modern SaaS application.
- Examples: Modals, Toasts, Multi-selects, Steppers.

## The `classics` Library

Found in `src/components/classics/`, this library contains components designed to mimic the native WordPress and WooCommerce interface.

Use these if you want your plugin to seamlessly blend in with the rest of the WordPress dashboard.
- Examples: Native-looking text inputs, WP-list-tables, tooltips.

## Layout Switcher

You can switch the entire structural layout of the app by changing the wrapper in `src/App.tsx`.

- **`ClassicLayout`**: Wraps your content in a standard WordPress container.
- **`AppLayout`**: Wraps your content in a full-screen, modern dashboard layout.

> [!NOTE]  
> See the screenshots below for a visual comparison of the layouts and component styles (once captured).

<!-- Insert App Layout vs Classic Layout Screenshot Here -->
<!-- Insert Component Library Showcase Screenshot Here -->

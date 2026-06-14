---
title: Manual Placement (Shortcodes & Blocks)
description: How to place NotifyBay forms anywhere using Gutenberg blocks or shortcodes.
---

By default, NotifyBay automatically places the "Notify Me" and "Track Price" buttons on your WooCommerce single product pages. However, you may want to place these forms in custom locations—like a landing page, a blog post, or a custom sidebar.

NotifyBay provides two easy ways to do this: **Gutenberg Blocks** and **Shortcodes**.

## 1. Using Gutenberg Blocks

If you are using the WordPress Block Editor (Gutenberg), NotifyBay includes native blocks that you can drag and drop anywhere.

<!-- Insert Gutenberg Block Search Screenshot Here -->

### How to use:
1.  Open any Page or Post in the WordPress editor.
2.  Click the **+ (Toggle Block Inserter)** button.
3.  Search for **"NotifyBay"**.
4.  You will see two blocks:
    *   **NotifyBay Waitlist:** Adds the "Notify Me" form.
    *   **NotifyBay Wishlist:** Adds the "Track Price" button.
5.  **Optional:** In the block settings sidebar (on the right), you can enter a **Product ID**. If left at `0`, the block will automatically detect the ID of the current page (useful if you are using a custom product template).

## 2. Using Shortcodes

For users using the Classic Editor, Elementor, Divi, or other page builders, NotifyBay provides two powerful shortcodes.

### The Waitlist Shortcode
To show the back-in-stock notification form:
```text
[notifybay_waitlist]
```

### The Wishlist Shortcode
To show the price-drop notification button:
```text
[notifybay_wishlist]
```

### Advanced: Placing on Non-Product Pages
If you are placing a form on a regular Page or Blog Post that isn't a WooCommerce product, you must tell the shortcode which product to track by using the `id` attribute.

**Example:** To show a waitlist form for product ID `123` on your homepage:
```text
[notifybay_waitlist id="123"]
```

## Finding the Product ID
If you're not sure what your Product ID is, you can find it easily:
1.  Go to **Products > All Products** in your WordPress dashboard.
2.  Hover your mouse over the product name.
3.  The ID will appear in small text (e.g., `ID: 123`).

---

## Which Method Should I Use?
- **For standard pages:** Use the **Gutenberg Blocks** for a visual, easy-to-use experience.
- **For Page Builders (Elementor, Beaver Builder):** Use the **Shortcodes** inside a "Shortcode" or "Text" widget.
- **For Widget sidebars:** Use the **Shortcodes** inside a standard "Text" or "Custom HTML" widget.

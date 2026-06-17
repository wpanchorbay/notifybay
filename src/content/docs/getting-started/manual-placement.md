---
title: Manual Placement (Blocks & Shortcodes)
description: Take full control over your store layout. Learn how to place NotifyMe and Track Price forms exactly where you want them using native Gutenberg Blocks or Shortcodes.
---

By default, NotifyBay automatically places the Sales Recovery forms on your standard WooCommerce single product pages. However, modern stores often use custom landing pages, blog posts, or unique theme layouts that require more flexibility.

NotifyBay provides two professional ways to manually place your forms: **Native Gutenberg Blocks** and **Dynamic Shortcodes**.

---

## 1. Using Gutenberg Blocks

If you are using the modern WordPress Block Editor (Gutenberg), NotifyBay includes dedicated blocks that look and feel like a native part of your editing experience.

### How to Add a Block:
1.  Open any Page or Post in the WordPress editor.
2.  Click the **+ (Toggle Block Inserter)** button at the top left.
3.  Search for **"NotifyBay"**.

![Searching for NotifyBay Blocks](/notifybay/assets/screenshots/manual-placement-block-search.png)

4.  Select the block you need:
    *   **NotifyBay Waitlist:** Adds the "Notify Me" restock form.
    *   **NotifyBay Wishlist:** Adds the "Track Price" heart/button.

### Configuring the Block:
Once the block is placed, you can customize it using the settings sidebar on the right. 

**Dynamic Product Search:** 
Instead of looking up IDs manually, you can search for a product title directly inside the block settings.
- **Current Page Product:** By default, the block automatically detects the product if it's placed on a product page.
- **Target Specific Product:** Use the search box to find and select any product from your store to target it specifically.

![Block Sidebar Settings](/notifybay/assets/screenshots/manual-placement-block-settings.png)

---

## 2. Using Shortcodes

Shortcodes are a flexible alternative that work inside the Classic Editor, Sidebar Widgets, and popular page builders like **Elementor**, **Divi**, or **Beaver Builder**.

### The Restock (Waitlist) Shortcode
Use this to display the back-in-stock subscription form:
```text
[notifybay_waitlist]
```

### The Price Drop (Wishlist) Shortcode
Use this to display the "Track Price" or "Add to Wishlist" button:
```text
[notifybay_wishlist]
```

![Shortcode in Text Editor](/notifybay/assets/screenshots/manual-placement-shortcode-example.png)

### Customizing the Shortcode
If you are placing the shortcode on a page that isn't the product itself, you must tell the shortcode which product to watch using the `id` attribute.

**Example:** To show a waitlist form for Product #123 on your homepage:
```text
[notifybay_waitlist id="123"]
```

---

## Finding Your Product ID

You will need the Product ID whenever you are using Shortcodes on a non-product page.

1.  In your WordPress dashboard, go to **Products > All Products**.
2.  Hover your mouse over the title of the product you want to track.
3.  The **ID** will appear in small gray text immediately below the title (e.g., `ID: 123`).

![Locating the Product ID](/notifybay/assets/screenshots/manual-placement-product-id.png)

---

## Summary: Which Method is Best?

| Placement Need | Recommended Method | Why? |
| :--- | :--- | :--- |
| **Standard Pages & Posts** | **Gutenberg Blocks** | Visual, easy to search/select products, and no code required. |
| **Page Builders** | **Shortcodes** | Best compatibility with Elementor, Divi, etc. |
| **Sidebar Widgets** | **Shortcodes** | Works perfectly inside "Text" or "Shortcode" widgets. |
| **Custom Theme Code** | **PHP Function** | Developers can use `echo do_shortcode('[notifybay_waitlist]');`. |

> [!TIP]
> After manually placing a form, always visit the page as a guest (Incognito mode) to ensure the button or form renders exactly as you intended.

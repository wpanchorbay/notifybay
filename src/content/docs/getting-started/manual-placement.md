---
title: Manual Placement (Shortcodes)
description: Take full control over your store layout. Learn how to place NotifyMe and Track Price forms exactly where you want them using Shortcodes.
---

By default, NotifyBay automatically places the Sales Recovery forms on your standard WooCommerce single product pages. However, modern stores often use custom landing pages, blog posts, or unique theme layouts that require more flexibility.

NotifyBay provides dynamic **Shortcodes** to help you place your forms exactly where you want them.

---

## 1. Using Shortcodes

Shortcodes are the most flexible placement method. They work inside the Standard Block Editor, the Classic Editor, Sidebar Widgets, and popular page builders like **Elementor**, **Divi**, or **Beaver Builder**.

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

### How to Add to a Page:
1.  Open any Page or Post in the WordPress editor.
2.  Add a **Shortcode Block** (or a standard Paragraph block).
3.  Paste the shortcode.

![Shortcode in Text Editor](/notifybay-docs/assets/screenshots/manual-placement-shortcode-example.png)

---

## 2. Customizing the Shortcode

If you are placing the shortcode on a page that isn't the product itself (like a "Coming Soon" landing page), you must tell the shortcode which product to watch using the `id` attribute.

**Example:** To show a waitlist form for Product #123 on your homepage:
```text
[notifybay_waitlist id="123"]
```

---

## Finding Your Product ID

You will need the Product ID whenever you are placing a NotifyBay form on a non-product page.

1.  In your WordPress dashboard, go to **Products > All Products**.
2.  Hover your mouse over the title of the product you want to track.
3.  The **ID** will appear in small gray text immediately below the title (e.g., `ID: 123`).

![Locating the Product ID](/notifybay-docs/assets/screenshots/manual-placement-product-id.png)

---

## Summary: Which Method is Best?

| Placement Need | Recommended Method | Why? |
| :--- | :--- | :--- |
| **Standard Pages & Posts** | **Shortcode Block** | Simple copy-paste into any block area. |
| **Page Builders** | **Shortcodes** | Best compatibility with Elementor, Divi, etc. |
| **Sidebar Widgets** | **Shortcodes** | Works perfectly inside "Text" or "Shortcode" widgets. |
| **Custom Theme Code** | **PHP Function** | Developers can use `echo do_shortcode('[notifybay_waitlist]');`. |

> [!TIP]
> After manually placing a form, always visit the page as a guest (Incognito mode) to ensure the button or form renders exactly as you intended.

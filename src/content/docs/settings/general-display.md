---
title: General & Display Settings
description: Configuring the core behavior and appearance of NotifyBay.
---

The settings panel is your command center for tailoring the plugin to your specific store needs. Navigate to **NotifyBay > Settings** to access these options. The options are divided into logical tabs to help you easily find what you need.

## General Tab

The General tab controls the fundamental behavior and rules for your waitlists and wishlists.

<img src="/notifybay-docs/assets/screenshots/settings-general.png" alt="NotifyBay General Settings Tab" data-lightbox="true" />

### Core Features
*   **Enable Wishlist:** You can toggle the Wishlist (Price Drop) functionality on or off. If disabled, only the Waitlist (Back-in-Stock) functionality will be active. This allows you to use NotifyBay purely as a stock notification tool if desired.

### Compliance & Security
*   **Double Opt-In:** When enabled, guest users will receive an initial verification email asking them to confirm their address before their subscription becomes active.
    *   *Why use this?* It is highly recommended for GDPR and CAN-SPAM compliance. It ensures that the person requesting the notification actually owns the email address, helping you maintain a clean, high-quality email list and preventing malicious bots from spamming your forms. Only verified leads will be added to your notification queue.

### Inventory Logic
*   **Backorder Behavior:** Choose whether the "Notify Me" form should appear for products that allow backorders in WooCommerce.
    *   *Waitlist only if backorders disabled:* The waitlist form only appears if the product is strictly out of stock and cannot be purchased.
    *   *Show waitlist regardless of backorders:* Users can join a waitlist even if they could theoretically place a backorder. Useful if you want to gauge interest without forcing an immediate purchase.
    *   *Never show waitlist for backorderable items:* Completely hides the waitlist functionality if backordering is permitted.

---

## Display Tab

The Display tab (labeled "Appearance" in the settings) allows you to integrate the frontend buttons seamlessly into your store's design and configure social proof.

<img src="/notifybay-docs/assets/screenshots/settings-display.png" alt="NotifyBay Display and Appearance Settings" data-lightbox="true" />

### Waitlist Display
*   **Button Text:** Customize the text shown on the waitlist button (e.g., change "Notify Me" to "Join the Waitlist" or "Alert Me").
*   **Button CSS Class:** Add custom CSS classes to the Waitlist button so it automatically adopts your theme's native styling (e.g., `btn btn-primary`).
*   **Success Message:** The text displayed to the user immediately after they successfully submit the waitlist form.
*   **Social Proof (FOMO):** Enable this to show how many other people are waiting for this product. This creates urgency (Fear Of Missing Out).
    *   *FOMO Template:* Customize the text, using `{count}` as a placeholder (e.g., "Join {count} others waiting for this!").
    *   *Minimum Threshold:* To prevent negative social proof, the FOMO message will only display if the waitlist count is equal to or higher than this number (e.g., set to 5 so it only shows if at least 5 people are waiting).

### Wishlist Display
*(Only visible if the Wishlist feature is enabled in the General tab)*
*   **Button Text & CSS Class:** Similar to the waitlist, customize the text and styling of the "Add to Wishlist" button.
*   **Archive Visibility:** Choose whether the wishlist heart icon/button should appear on shop and category pages, allowing users to wishlist items without clicking into the single product page.
*   **Success Message:** The text displayed after an item is successfully added to the wishlist.

### Custom Styles
*   **Additional CSS:** A built-in code editor where you can add custom CSS to fine-tune the look and feel of the plugin's frontend elements without needing to edit your theme's stylesheet. Do not include `<style>` tags.

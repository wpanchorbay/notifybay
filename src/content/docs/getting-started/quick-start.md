---
title: Quick Start Guide
description: Get NotifyBay running on your WooCommerce store in 5 minutes with our foolproof 3-step setup.
---

Once you have [installed](/notifybay-docs/getting-started/installation/) NotifyBay, you can get it up and running on your storefront in just a few minutes. This guide walks you through the absolute essentials to start recovering revenue today.

---

## Step 1: Activate Your Core Modules

First, decide which notification features you want to offer your customers.

1.  Navigate to **NotifyBay > Settings** in your WordPress admin sidebar.
2.  On the **General** tab, find the **Feature Selection** section.
3.  Ensure **Waitlist (Back-in-Stock)** is toggled ON to capture intent for out-of-stock items.
4.  Toggle **Enable Wishlist** to ON if you want customers to track price drops.

<img src="/notifybay-docs/assets/screenshots/quickstart-general-toggles.png" alt="General Feature Toggles" data-lightbox="true" />

5.  Click **Save Settings** at the bottom of the page.

## Step 2: Configure Your Button Appearance

NotifyBay needs to look like a native part of your store. You can customize the look and placement in the Display tab.

1.  Click the **Display** (Appearance) tab at the top of the Settings screen.
2.  **Placement:** By default, NotifyBay is set to **Automatic**. This works for almost all themes by automatically inserting the form near the "Add to Cart" button.
3.  **Button Styling:**
    *   Change the **Waitlist Button Text** (e.g., "Alert me when in stock!").
    *   Add your theme's primary button class to the **Button CSS Class** field (e.g., `button alt` or `btn-primary`) to ensure a perfect visual match.

<img src="/notifybay-docs/assets/screenshots/quickstart-display-styling.png" alt="Button Styling Settings" data-lightbox="true" />

4.  Click **Save Settings**.

## Step 3: Verify & Send Your First Test

Before going live, it's critical to verify the "Customer-to-Dashboard" flow.

1.  **Open an Incognito Window:** Open your store as a guest visitor.
2.  **Join a Waitlist:** Go to any **Out of Stock** product. You should see your new button. Click it, enter a test email, and submit.
3.  **Check your Dashboard:** Go back to your admin browser tab and navigate to **NotifyBay > Leads**.
4.  **Success:** You should see your test email at the top of the list with an "Active" status.

<img src="/notifybay-docs/assets/screenshots/quickstart-test-lead.png" alt="Successful Test Lead in Dashboard" data-lightbox="true" />

---

### What's Next?
Now that your engine is running, you can:
- [Customize your email templates](/notifybay-docs/settings/email-templates/) to match your brand voice.
- Set up [Double Opt-In](/notifybay-docs/getting-started/configuration/) for better email hygiene.
- Learn how to place forms manually using [Shortcodes or Blocks](/notifybay-docs/getting-started/manual-placement/).

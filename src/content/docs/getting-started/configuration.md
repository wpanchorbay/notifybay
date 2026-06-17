---
title: Configuration
description: Essential setup steps for NotifyBay merchants.
---

Once you have [installed](/notifybay/getting-started/installation/) NotifyBay, there are a few essential settings you should configure to ensure the plugin behaves exactly how you want.

## 1. Enable Features

By default, the **Waitlist (Back-in-Stock)** feature is enabled. If you also want to allow customers to track price drops, you must enable the **Wishlist** feature:

1.  Go to **NotifyBay > Settings**.
2.  In the **General** tab, check the box for **Enable Wishlist**.
3.  Click **Save Settings**.

## 2. Double Opt-In (Highly Recommended)

To maintain a high-quality email list and comply with global privacy laws (like GDPR), we strongly recommend enabling Double Opt-In.

1.  In the **General** tab, find the **Compliance & Security** section.
2.  Enable **Double Opt-In**.
3.  Users will now receive a confirmation email they must click before they are added to your active notification queue.

## 3. Customize Your Buttons

You should make the "Notify Me" and "Track Price" buttons match your store's branding:

1.  Go to the **Display** tab in Settings.
2.  Update the **Button Text** to something that fits your brand voice (e.g., "Join the Waitlist" or "Alert Me on Sale").
3.  If your theme uses specific CSS classes for buttons (like `btn btn-primary`), enter them in the **Button CSS Class** field.

## 4. Set Your "Hurry" Logic

NotifyBay can automatically create urgency by sending a follow-up email when stock is running low.

1.  Go to the **Engine Logic** tab.
2.  Set your **Low Stock Threshold** (e.g., if you set this to `5`, a "Hurry" email will be sent when only 5 items are left).
3.  Ensure the **Hurry Alerts** feature is toggled on.

---

> [!TIP]
> After configuring your settings, we recommend testing the signup process on a single out-of-stock product to ensure everything looks and behaves as expected.

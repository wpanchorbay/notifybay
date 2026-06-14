---
title: Quick Start
description: Get NotifyBay running on your storefront in 3 easy, foolproof steps.
---

Once you have installed and activated NotifyBay, you can get it up and running on your storefront in just a few minutes. We've designed the setup process to be as intuitive as possible.

## Step 1: Configure General Settings

The first step is deciding which features you want to offer to your customers.

1. Navigate to **NotifyBay > Settings** in your WordPress admin sidebar.
2. On the **General** tab, you will see master toggle switches for the plugin's core features:
   - **Enable Back-in-Stock (Waitlist):** Turn this on to allow customers to subscribe to out-of-stock products.
   - **Enable Price Drop (Wishlist):** Turn this on to allow customers to track prices on in-stock products.
3. Configure your basic subscriber preferences:
   - **Require Login:** Decide if only registered/logged-in users can use the features, or if guests can subscribe using just their email address (Guest mode usually results in higher conversions).
   - **Double Opt-in:** If you are strict about GDPR or email hygiene, enable this to require users to click a confirmation link in their email before they are added to the waitlist.
4. Click the **Save Changes** button at the bottom of the page.

## Step 2: Configure Display & Styling

Next, you need to decide where the "Notify Me" buttons should appear on your product pages and how they should look.

1. Click on the **Display** tab located at the top of the Settings area.
2. **Insertion Method:** Choose how the button is added to your page. 
   - *Automatic:* The plugin will attempt to hook into standard WooCommerce locations (e.g., automatically insert after the "Add to Cart" button or out-of-stock message). This works for 90% of standard themes.
   - *Custom Shortcode:* Select this if you are using a page builder (like Elementor or Divi) or a heavily customized theme. You will then manually place the `[notifybay_form]` shortcode exactly where you want it.
3. **Button Customization:** Customize the button text (e.g., change "Notify Me" to "Join the Waitlist"), and adjust the background and text colors to perfectly match your store's branding.
4. Click **Save Changes**.

## Step 3: Test the Frontend Experience

Before announcing the feature to your customers, it is crucial to verify that everything is working perfectly on your live site.

1. Open your website in an **Incognito/Private browsing window** (this ensures you are seeing the site as a regular customer, not an admin).
2. **Test the Waitlist:** Navigate to a product that is currently **Out of Stock**. You should see your newly styled Waitlist button instead of (or alongside) the out-of-stock notice. Click it, enter a test email address, and submit the form.
3. **Test the Price Drop:** Navigate to an **In Stock** product. If you enabled the Price Drop feature, you should see the button allowing you to track the price. Click it, set a target price, and submit.
4. **Verify in Dashboard:** Go back to your regular browser window where you are logged into WordPress. Navigate to **NotifyBay > Leads**. You should see the test email(s) you just submitted listed in the dashboard, along with the requested product and status.

> [!TIP]  
> **Testing Emails:** If you want to see the actual emails sent to customers, manually change the inventory of the out-of-stock product to "In Stock" via the WooCommerce product editor. NotifyBay will detect the change and send a Back-in-Stock notification to the test email you provided!

Congratulations! NotifyBay is now actively capturing leads and helping you recover lost sales.

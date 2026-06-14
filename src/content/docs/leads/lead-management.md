---
title: Lead Management
description: Viewing, searching, and editing your subscribers.
---

Navigate to **NotifyBay > Leads** to access the master table of all your subscribers. This is your central hub for managing the data captured by the plugin.

<!-- Insert Leads Table Screenshot Here -->

## Viewing the Data

The Leads table provides a comprehensive overview of every subscription. It supports pagination, allowing you to easily browse through thousands of leads 20 at a time using the Next and Previous buttons at the bottom of the screen.

The table displays the following columns:
- **Checkbox:** Use this to select one or more leads for bulk actions.
- **Email:** The customer's contact address.
- **Product:** The specific item they are interested in.
- **Type:** Whether it is a Waitlist or Wishlist subscription.
- **Target Price:** The price they are waiting for (if it's a Wishlist lead).
- **Status:** The current state of the subscription.
- **Date:** When they subscribed.
- **Actions:** Quick links to Edit or Delete individual records.

### Status Definitions
Understanding lead statuses helps you track where customers are in the funnel:
- **Active:** The lead is currently waiting for a notification.
- **Pending Verification:** If double opt-in is enabled, the customer has subscribed but hasn't yet clicked the confirmation link in their email.
- **Notified:** An email has been successfully sent to this lead (either back-in-stock or price drop).
- **Converted:** The lead clicked the link in the notification email and successfully purchased the product.
- **Expired:** The subscription exceeded your configured expiration time (e.g., 90 days) and was automatically closed.
- **Failed:** The system attempted to send an email, but it failed (usually due to an invalid email address or server issue).
- **Unsubscribed:** The customer manually opted out of receiving further notifications for this item.

## Searching Leads

If you need to find a specific customer, you don't need to manually click through pages.
1. Use the **Search by email...** input box located at the top right of the Leads interface.
2. Enter the full or partial email address.
3. Click the **Search** button. The table will update to show only matching records.

## Editing a Lead

Occasionally, a customer might contact you to change their target price or update their email address. You can do this manually from the dashboard.

1. Locate the lead in the table (use the search bar if necessary).
2. Click the **Edit** button in the Actions column.
3. A modal will appear allowing you to modify the following details:
   - **Email Address:** Correct any typos in the customer's email.
   - **Status:** Manually update their stage in the funnel (e.g., force a lead to be 'Active' again).
   - **Price at Subscription:** Record of the product's price when they signed up (if applicable).
4. Click **Save** to apply the changes.

<!-- Insert Edit Lead Modal Screenshot Here -->

---
title: Email Templates
description: Customizing the messages your customers receive.
---

The Email Templates tab allows you to craft the perfect message to bring customers back to your store. You can customize the subject line and body text for all automated messages sent by NotifyBay.

<!-- Insert Settings - Email Templates Tab Screenshot Here -->

## Email Identity

Before customizing individual templates, you must set your global sender identity:
*   **From Name:** The name that will appear in the customer's inbox (e.g., "My Store Team" or "John from CoolStore").
*   **From Email:** The email address used to send the notifications (e.g., "sales@yourstore.com"). This should be an address configured with your domain to ensure high deliverability.

## Notification Types

You can customize the content for four distinct types of emails:

1.  **Restock Notifications:** Sent to waitlist subscribers when inventory is replenished.
2.  **Price Drop Alerts:** *(If Wishlist is enabled)* Sent to wishlist subscribers when a product's price goes on sale.
3.  **Urgency (Hurry) Alerts:** *(If enabled in Engine Logic)* A follow-up email sent when stock levels are running critically low after an initial restock notification. This leverages FOMO to drive immediate action.
4.  **Verification Emails:** *(If Double Opt-In is enabled)* Sent when a guest user first subscribes to confirm their email address.

## Customizing Content & Variables

You can use dynamic placeholders (tags) in your email templates. These placeholders will be automatically replaced with the correct information when the email is sent. You can write your body content using standard text or HTML.

### Common Variables

*   `{product_name}` - The name of the product the user is interested in.
*   `{customer_name}` - The full name of the customer (if known).
*   `{customer_first_name}` - The first name of the customer (if known).
*   `{buy_link}` - A direct link back to the product page where they can complete their purchase.
*   `{unsubscribe_link}` - A link allowing the user to remove themselves from the notification list.

### Specialized Variables

*   `{stock_qty}` - The exact current stock quantity. *Available in Restock and Urgency alerts.*
*   `{verify_url}` - The secure link the user must click to confirm their subscription. *Only available in Verification emails.*

> [!TIP]  
> Always include a clear call-to-action (CTA) in your email body! For marketing emails, urging the customer to click `{buy_link}` is crucial. For verification emails, you MUST include the `{verify_url}` or the user will never be able to confirm their subscription.

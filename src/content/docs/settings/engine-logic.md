---
title: Engine Logic
description: Controlling exactly when notifications are sent and managing background automation.
---

The Engine Logic tab defines the powerful background rules that dictate when emails are dispatched, how stock is allocated, and how revenue is tracked.

## Waitlist Automation (Fair-Play)

If you have 1,000 people on a waitlist but only restock 10 items, emailing everyone simultaneously causes frustration when 990 people click through only to find the item sold out again.

*   **Fair-Play Restock:** When enabled, the engine will only notify a batch of people equal to the actual units restocked.
*   **Notification Multiplier:** Knowing that not everyone will purchase, you can set a ratio. A multiplier of "2" means the system will email 20 people if 10 units are restocked.
*   **Reservation Window:** How long (in hours) stock is considered "reserved" for a notified user. If a user doesn't purchase within this window, the system assumes they aren't interested and will notify the next batch of users in the queue.

## Waitlist Expiry Logic

To protect your sender reputation and avoid emailing users who have moved on:
*   **Auto-Expire Leads:** Automatically remove users from the waitlist after a certain number of days if no restock occurs.
*   **Frontend Options:** You can define a comma-separated list of expiry options (e.g., "30, 60, 90") that customers can select from when they sign up.
*   **Default Expiry:** Set the default duration applied if the user doesn't explicitly choose one.

## Sales Attribution

*   **Conversion Window (Days):** The period of time after an email is sent during which a purchase is attributed to NotifyBay. If you set this to 7 days, any purchase of the notified product by that user within 7 days of the email will be counted in the plugin's "Revenue Recovered" dashboard stats.

## Stock Control

*   **Minimum Restock Threshold:** By default, a notification is sent as soon as stock goes above 0. However, if you often have slight inventory errors or returns, you might want to wait until stock reaches `5` before triggering alerts, ensuring you can actually fulfill the orders.

## Urgency Alerts

*   **Hurry Logic:** Sends an automated follow-up email to notified users if stock levels drop below a critical point. This creates psychological urgency for leads who haven't purchased yet.
*   **Urgency Threshold:** The stock level that triggers the "Hurry" alert (e.g., trigger when stock drops below 3 units).
*   **Urgency Delay:** The minimum time (in hours) to wait after the initial restock email before a hurry alert can be sent.

## Admin Notifications

*   **Owner Alerts:** Enable this to receive an email notification as the store administrator whenever a new shopper joins a waitlist or wishlist, helping you gauge real-time product demand.

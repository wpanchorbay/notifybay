---
title: Advanced & System Status
description: Troubleshooting background jobs and advanced technical options.
---

If you run into issues with emails not sending, the Advanced and System Status tabs provide the diagnostic tools you need.

## System Status Tab

The System Status tab provides a real-time look into the plugin's background engine and your server environment. If you contact support, they will likely ask for this information.

### Background Engine Status (Action Scheduler)
NotifyBay uses WooCommerce's built-in Action Scheduler to process emails in the background so it doesn't slow down your website.
*   **Pending:** Emails waiting to be sent in the next background batch.
*   **In-Progress:** Emails actively being processed right now.
*   **Complete:** Emails successfully sent.
*   **Failed:** Emails that the system attempted to send but couldn't (usually due to a server configuration issue).

### Lead Health
*   **Failed Leads:** Subscribers whose notifications permanently failed.
*   **In Processing:** Subscribers currently locked while the system determines if they should receive an email based on fair-play logic.

### Environment Information
Quickly verify your PHP, WordPress, and WooCommerce versions. Older versions of PHP may prevent the background engine from running correctly.

---

## Advanced Tab

The Advanced tab contains technical options for maintenance and troubleshooting.

### Debug Mode
*   **Enable developer logging:** When enabled, NotifyBay will log technical data during execution to help troubleshoot background jobs, email sending, and API calls. 
*   *Note:* These logs are written to the native WooCommerce log system (`WooCommerce > Status > Logs`). You should only enable this when actively troubleshooting, as it can generate large files over time.

### Deep Uninstall
*   **Delete all tables and settings on plugin deletion:** By default, NotifyBay preserves your data if you deactivate and delete the plugin (in case you want to reinstall later). If you want to permanently wipe all Waitlist/Wishlist leads, custom database tables, and settings when uninstalling the plugin, check this box.
*   **DANGEROUS:** Once this is checked and the plugin is deleted, the data cannot be recovered unless you have a full database backup.

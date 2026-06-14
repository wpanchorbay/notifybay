---
title: Installation
description: How to install and activate NotifyBay on your site.
---

Installing NotifyBay on your WordPress site is a quick and straightforward process, similar to installing any standard WordPress plugin.

## Requirements

Before installing, ensure your server and WordPress environment meet these minimum requirements for optimal performance:
- **WordPress:** Version 5.6 or higher.
- **WooCommerce:** (Required for functionality) Version 5.0 or higher. The plugin integrates deeply with WooCommerce products, inventory, and pricing.
- **PHP:** Version 7.4 or higher is recommended for security and speed (minimum 7.0).

## Installation Steps (via WordPress Admin)

This is the most common and easiest method to install the plugin.

1. **Download the Plugin:** Obtain the NotifyBay `.zip` file from your account dashboard or the provider's email. Save it to an easy-to-find location on your computer.
2. **Navigate to Plugins:** Log into your WordPress admin dashboard and go to **Plugins > Add New Plugin** in the left-hand sidebar.
3. **Upload Plugin:** Click the **Upload Plugin** button at the top of the screen next to the "Add Plugins" title.
4. **Select the File:** Click the **Choose File** button and select the NotifyBay `.zip` file you downloaded in step 1.
5. **Install:** Click the **Install Now** button. WordPress will extract and install the plugin files.
6. **Activate:** Once the installation completes successfully, click the **Activate Plugin** button.

Upon successful activation, you will see a new **NotifyBay** menu item added to your WordPress admin sidebar, usually positioned below the standard WooCommerce menus.

## Alternative Installation (via FTP/SFTP)

If you are unable to install the plugin via the WordPress dashboard, you can upload it manually.

1. Extract the downloaded `.zip` file on your computer. You should now have a folder named `notifybay`.
2. Connect to your web server using an FTP client (like FileZilla or Cyberduck).
3. Navigate to the `/wp-content/plugins/` directory on your server.
4. Upload the extracted `notifybay` folder into the `plugins` directory.
5. Log into your WordPress admin dashboard, navigate to **Plugins > Installed Plugins**, locate NotifyBay in the list, and click **Activate**.

## Troubleshooting Installation

> [!WARNING]  
> If you encounter an error stating "The uploaded file exceeds the upload_max_filesize directive in php.ini", you will need to contact your hosting provider to increase your PHP upload limit, or use the Alternative Installation (FTP) method described above.

**Plugin activated, but no NotifyBay menu?**
- Ensure that WooCommerce is installed and activated. NotifyBay relies on WooCommerce to function and may not initialize correctly if WooCommerce is missing.
- Check if another plugin is causing a menu conflict. Try temporarily deactivating other plugins to see if the menu appears.

**"Are you sure you want to do this?" error during upload:**
- This usually means your server's upload limit is too low, or the security token expired. Try the FTP installation method or contact your host to increase the `post_max_size` and `upload_max_filesize` limits.

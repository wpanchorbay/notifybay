---
title: Installation
description: How to install and set up NotifyBay.
---

This guide will walk you through setting up NotifyBay for your new project.

## Requirements

Before you begin, ensure your environment meets the following requirements:
- **WordPress:** 5.6 or higher
- **PHP:** 7.0 or higher
- **Node.js:** 18 or higher

## 1. Clone the Repository

First, clone the plugin repository into your WordPress `wp-content/plugins` directory.

```bash
git clone <repo_url> your-plugin-name
cd your-plugin-name
```

## 2. White-labeling

NotifyBay includes a handy script to rename the boilerplate to your custom plugin name.

Run the `rename.sh` script (or manually search and replace) to update the following strings throughout the codebase:

- `NotifyBay` → `YourNamespace`
- `WP_BOILERPLATE_` → `YOUR_PLUGIN_`
- `notifybay` (slug) → `your-plugin-slug`
- `notifybay` (snake) → `your_plugin_slug`
- `notifyBay` (JS) → `yourPlugin`
- `NotifyBay` (UI text) → `Your Plugin Title`
- `notifybay-` (Tailwind prefix) → `yourprefix-`

> [!CAUTION]  
> Make sure to update the Tailwind prefix carefully so you don't accidentally break the pre-flight guard!

## 3. Install Dependencies

You need to install both PHP and Node.js dependencies.

```bash
# Install NPM dependencies
npm install

# Install Composer dependencies
composer install
```

## 4. Development & Production

NotifyBay uses `@wordpress/scripts` for its build pipeline.

### Development Mode

To start the hot-reloading development server, run:

```bash
npm run start
```

> [!TIP]  
> Ensure `SCRIPT_DEBUG` is set to `true` in your `wp-config.php` to load the development assets correctly.

### Production Build

When you are ready to ship your plugin, generate the optimized production assets:

```bash
npm run build
```

This will compile your assets into the `/build` directory, creating both modern ES modules and legacy builds for older browsers.

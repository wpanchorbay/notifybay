---
title: Configuration
description: Essential configuration steps for NotifyBay.
---

NotifyBay requires some initial configuration to align it with your specific project requirements.

## 1. Branding & Constants

Open `notifybay.php` and update the primary constants:

- `NOTIFYBAY_VERSION`: Set your current plugin version.
- `NOTIFYBAY_FILE`: Points to the main plugin file.
- `NOTIFYBAY_PATH`: Base filesystem path.
- `NOTIFYBAY_URL`: Base URL for assets and scripts.

## 2. Composer & Autoloading

Ensure your `composer.json` is updated with your own vendor name. After changing it, run:

```bash
composer dump-autoload
```

## 3. Frontend Environment

The React SPA reads its configuration from the WordPress backend. However, for local development with Vite, you may need to adjust the `proxy` or `base` path in `frontend/vite.config.ts`.

## 4. REST API Namespace

The default REST API namespace is `notifybay/v1`. You can customize this in `app/Core/Api/NamespaceManager.php` (if applicable) to match your desired API structure.

---
title: Core Concepts
description: Core PHP architecture concepts in NotifyBay.
---

NotifyBay is built on modern PHP principles, bringing object-oriented programming (OOP) and maintainability to WordPress plugin development.

## PSR-4 Autoloading

NotifyBay uses Composer to handle autoloading. All classes inside the `app/` directory follow the PSR-4 autoloading standard.

This means that the namespace of a class must match its directory path, and the class name must match the file name.

**Example:**
- Namespace: `\NotifyBay\Api\SettingsController`
- File Path: `app/Api/SettingsController.php`

Because of this, you never need to manually `require` or `include` class files. Just ensure you use the correct namespace, and Composer will load the file automatically.

## The Base Singleton (`Base.php`)

To prevent multiple instances of core classes and to provide a structured way to hook into WordPress, NotifyBay uses a base singleton class pattern.

Most core classes will extend a foundational `Base.php` (or similar core class) that automatically registers WordPress hooks. If a class has a method like `init()`, the core bootstrap will automatically call it when the plugin loads.

## Bootstrapping (`notifybay.php`)

The entry point of the plugin is `notifybay.php`. This file does very little on its own. Its main responsibilities are:
1. Defining fundamental constants (like paths and URLs).
2. Requiring the Composer autoloader (`vendor/autoload.php`).
3. Calling the core `Plugin::get_instance()` to boot up the application.

This keeps the root file clean and delegates all the actual logic to the `app/` directory.

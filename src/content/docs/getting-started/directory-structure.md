---
title: Directory Structure
description: An overview of the NotifyBay directory structure.
---

NotifyBay is highly structured to separate concerns and maintain a scalable codebase.

Here is an overview of the most important directories and files:

```text
notifybay/
├─ app/                     # PHP backend
│  ├─ Admin/                # Admin-specific PHP classes
│  ├─ Api/                  # REST API Controllers
│  ├─ Core/                 # Core plugin bootstrapping and base classes
│  ├─ Data/                 # Data transfer objects or similar structures
│  ├─ Database/             # DbManager and Migrations
│  ├─ Helper/               # Utility PHP functions/classes
│  ├─ Models/               # Data Models
│  └─ functions.php         # Global helper functions
├─ bin/                     # CLI utilities (like make-resource)
├─ config/                  # Registration files (api, core, migrations)
├─ src/                     # React/TS SPA Frontend
│  ├─ components/
│  │   ├─ classics/         # Native‑style WordPress components
│  │   └─ common/           # Modern Tailwind components
│  ├─ pages/                # Admin dashboard routes/pages
│  ├─ store/                # Context API state management
│  ├─ styles/               # SCSS & Tailwind guard
│  ├─ utils/                # API helpers, types, custom hooks
│  ├─ App.tsx               # Main Router & layout wrapper
│  └─ index.tsx             # React entry point
├─ assets/                  # Images and icons
├─ languages/               # i18n translation files
├─ vendor/                  # Composer dependencies (do not edit)
├─ notifybay.php            # Main plugin bootstrap file
├─ uninstall.php            # Cleanup routines when the plugin is deleted
├─ rename.sh                # Global find‑replace script for white-labeling
├─ package.json             # NPM dependencies and scripts
├─ composer.json            # PHP dependencies and autoloading config
├─ tsconfig.json            # TypeScript configuration
├─ tailwind.config.js       # Tailwind CSS configuration
├─ postcss.config.js        # PostCSS configuration
└─ webpack.config.js        # Webpack build configuration
```

## Key Areas Explained

### `/app`
This directory contains all the PHP classes. It is PSR-4 autoloaded, meaning the namespace of a class maps directly to its folder path. For example, `\NotifyBay\Api\SettingsController` lives in `app/Api/SettingsController.php`.

### `/src`
This directory contains the entire React SPA. Everything inside here is compiled by Webpack into the `/build` directory. You should spend most of your frontend development time here.

### `/config`
Instead of having a massive `functions.php` file, NotifyBay uses configuration arrays to register things. You'll find files here to register API endpoints, migrations, and core plugin hooks.

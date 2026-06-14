---
title: Introduction
description: An introduction to the NotifyBay boilerplate.
---

Welcome to the **NotifyBay** documentation. 

NotifyBay is a modern, production‑ready WordPress plugin boilerplate that bridges classic WordPress development with a full‑featured React and TypeScript admin UI. It provides a highly structured, scalable foundation for building complex WordPress plugins.

## Key Features

- **Robust PHP Backend:** Built with object-oriented programming (OOP), PSR‑4 autoloading, and a singleton base class.
- **REST API Infrastructure:** Comes with permission‑checked base controllers.
- **React/TypeScript SPA:** A modern Single Page Application architecture for the admin dashboard.
- **Dual Component Libraries:** Includes `common` (Tailwind) and `classics` (WordPress native styling) component libraries.
- **Dynamic Cron Manager:** Easily schedule and manage background tasks.
- **Resource Generator CLI:** Scaffold models, migrations, and API controllers instantly via the command line.
- **Settings API & Database Manager:** Full abstraction for WordPress settings and custom database tables.

## Architecture Overview

NotifyBay splits its responsibilities cleanly between the frontend and the backend:

1.  **Frontend (React SPA):** The admin UI is built entirely in React. It uses `react-router-dom` for navigation and communicates with the server asynchronously.
2.  **Backend (WP REST API):** The PHP backend registers custom REST API endpoints. The React SPA consumes these endpoints to fetch and save data.
3.  **Bootstrapping:** When the plugin loads, PHP uses `wp_localize_script` to pass essential configuration (like nonce, API URLs, and base URLs) to the React frontend.

> [!NOTE]  
> See the `Architecture Diagram` below (once captured) for a visual representation.

<!-- Insert Architecture Diagram Here -->

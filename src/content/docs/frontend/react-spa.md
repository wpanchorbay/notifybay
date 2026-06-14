---
title: React SPA Architecture
description: Overview of the frontend React architecture.
---

The NotifyBay admin interface is built as a React Single Page Application (SPA). This provides a fast, app-like experience without the page reloads typical of classic WordPress admin pages.

## Routing

Navigation within the plugin is handled entirely on the client side using `react-router-dom`.

The main routing configuration can be found in `src/App.tsx`. When a user clicks a link in the plugin's sidebar, React Router intercepts the click and renders the appropriate component without making a full request to the server.

## Data Hydration & Localization

Because the React app needs to know about the WordPress environment (like the REST API URL, nonce for security, and current user capabilities), data is passed from PHP to React when the page loads.

This is done using the native WordPress function `wp_localize_script()`.

When the React app mounts (in `src/index.tsx`), it reads this localized data object from the global `window` object to initialize its state.

## State Management

NotifyBay uses the React Context API for global state management. This is sufficient for most plugin needs and avoids the heavy boilerplate of Redux.

The context files are located in `src/store/` and are wrapped around the main application in `App.tsx`.

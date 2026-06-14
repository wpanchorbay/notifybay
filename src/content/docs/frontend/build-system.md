---
title: Build System
description: Understanding the Webpack build process.
---

NotifyBay leverages `@wordpress/scripts` to handle its build pipeline. This package abstracts away the complex Webpack configuration typically required for React and TypeScript projects.

## Commands

All build commands are defined in `package.json` and are run via npm.

- `npm run start`: Starts the development server. It watches your files for changes and automatically rebuilds the assets. It does not minimize the code, making debugging easier.
- `npm run build`: Compiles the project for production. It minimizes the code and strips out development-only warnings.

## Dual Build Output

When you run `npm run build`, `@wordpress/scripts` is configured to output two sets of assets in the `/build` directory:

1.  **Modern Build:** Uses ES modules and modern JavaScript features. This is smaller and faster, and is served to modern browsers.
2.  **Legacy Build:** Transpiled to support older browsers that lack support for modern features.

WordPress automatically detects browser capabilities and serves the appropriate bundle.

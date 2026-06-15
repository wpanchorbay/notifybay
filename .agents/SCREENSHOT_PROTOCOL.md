# Standardized Spotlight Screenshot Procedure

When capturing a sectional screenshot for the NotifyBay documentation, you MUST follow this exact sequence to ensure visual consistency across all images.

## 1. Environment Preparation
*   **Browser Window:** Ensure the Chrome DevTools MCP is targeting a standard `1440x900` viewport.
*   **Page State:** Navigate to the correct URL and perform a hard reload (`mcp_chrome-devtools_navigate_page { type: 'reload' }`) to clear any lingering DOM manipulation from previous captures.

## 2. UI Cleaning & Spotlight Injection (JavaScript Execution)
Use `mcp_chrome-devtools_evaluate_script` to run the following code. This code will clean the UI (hiding both frontend and backend sidebars), inject the spotlight, and **return the cropping coordinates**.

```javascript
() => {
    // A. UI Cleaning
    const hideSelectors = ['#wpadminbar', '#adminmenumain', '#adminmenuwrap', '#secondary'];
    hideSelectors.forEach(selector => {
        const el = document.querySelector(selector);
        if (el) el.style.display = 'none';
    });
    
    // Reset layout shifts from admin menu
    const wpcontent = document.querySelector('#wpcontent');
    if (wpcontent) wpcontent.style.marginLeft = '0';
    
    document.body.style.overflow = 'hidden';
    document.documentElement.style.marginTop = '0';

    // B. Locate and Center Target
    const targetSelector = '.target-class-name'; // YOU MUST REPLACE THIS BEFORE EXECUTING
    const el = document.querySelector(targetSelector);
    if (!el) throw new Error(`Target ${targetSelector} not found`);
    
    el.scrollIntoView({ behavior: 'instant', block: 'center' });

    // C. Calculate Padding & Coordinates
    const rect = el.getBoundingClientRect();
    const padding = 15; // Standard padding

    const t = Math.max(0, rect.top - padding);
    const l = Math.max(0, rect.left - padding);
    const r = Math.min(window.innerWidth, rect.right + padding);
    const b = Math.min(window.innerHeight, rect.bottom + padding);
    
    const width = r - l;
    const height = b - t;

    // D. Create Full-Page Overlay
    const overlay = document.createElement('div');
    overlay.id = 'notifybay-spotlight-overlay';
    overlay.style.position = 'fixed';
    overlay.style.top = '0';
    overlay.style.left = '0';
    overlay.style.width = '100%';
    overlay.style.height = '100%';
    overlay.style.backgroundColor = 'rgba(0, 0, 0, 0.75)'; // 75% Black
    overlay.style.zIndex = '999999';
    overlay.style.pointerEvents = 'none';

    // E. Cut the "Hole" using clip-path
    overlay.style.clipPath = `polygon(
      0% 0%, 0% 100%, 100% 100%, 100% 0%, 0% 0%, 
      ${l}px ${t}px, ${r}px ${t}px, ${r}px ${b}px, ${l}px ${b}px, ${l}px ${t}px
    )`;

    document.body.appendChild(overlay);

    // F. Elevate Target Element
    el.style.position = 'relative';
    el.style.zIndex = '1000000';
    el.style.backgroundColor = '#ffffff'; // Ensure solid background
    
    // Return coordinates for ImageMagick cropping
    return { width, height, x: l, y: t };
}
```

## 3. Capture
*   **Tool:** Use `mcp_chrome-devtools_take_screenshot`.
*   **Scope:** Capture the viewport (do NOT use `fullPage: true`, do NOT use `uid`).
*   **Output:** Save directly to `public/assets/screenshots/<filename>.png`.

## 4. Crop (Post-Processing)
You MUST crop the saved screenshot using the coordinates returned by the JavaScript execution.
*   **Tool:** Use `run_shell_command`
*   **Command:** `mogrify -crop {width}x{height}+{x}+{y} +repage public/assets/screenshots/<filename>.png`
*(Replace `{width}`, `{height}`, `{x}`, and `{y}` with the values returned in Step 2).*

## 5. Verification
Verify the image was cropped successfully and is not empty.
*   **Tool:** Use `run_shell_command`
*   **Command:** `identify public/assets/screenshots/<filename>.png`
Ensure the output shows the correct dimensions (matching the crop width and height) and that the file exists.
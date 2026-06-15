# Standardized Spotlight Screenshot Procedure

When capturing a sectional screenshot for the NotifyBay documentation, you MUST follow this exact sequence to ensure visual consistency across all images.

## 1. Environment Preparation
*   **Browser Window:** Ensure the Chrome DevTools MCP is targeting a standard `1440x900` viewport.
*   **Page State:** Navigate to the correct URL and perform a hard reload (`mcp_chrome-devtools_navigate_page { type: 'reload' }`) to clear any lingering DOM manipulation from previous captures.

## 2. UI Cleaning
Before applying any effects, you must strip away non-essential UI elements to keep the screenshot focused.
*   **Hide WordPress Admin Bar:** `document.getElementById('wpadminbar').style.display = 'none';`
*   **Hide Theme Sidebars:** (e.g., Storefront secondary column) `document.getElementById('secondary').style.display = 'none';`
*   **Expand Main Content:** `document.getElementById('primary').style.width = '100%';`
*   **Disable Scrolling:** `document.body.style.overflow = 'hidden';`
*   **Reset Top Margin:** `document.documentElement.style.marginTop = '0';`

## 3. The "Spotlight" Injection (JavaScript Execution)
Do not use CSS borders or box-shadows. You MUST inject a full-page overlay with a `clip-path` mask.

```javascript
// A. Locate and Center Target
const el = document.querySelector('.target-class-name'); // Replace with specific target
el.scrollIntoView({ behavior: 'instant', block: 'center' });

// B. Calculate Padding
const rect = el.getBoundingClientRect();
const padding = 15; // Standard padding

// C. Create Full-Page Overlay
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

// D. Cut the "Hole" using clip-path
const t = rect.top - padding;
const l = rect.left - padding;
const r = rect.right + padding;
const b = rect.bottom + padding;

overlay.style.clipPath = `polygon(
  0% 0%, 0% 100%, 100% 100%, 100% 0%, 0% 0%, 
  ${l}px ${t}px, ${r}px ${t}px, ${r}px ${b}px, ${l}px ${b}px, ${l}px ${t}px
)`;

document.body.appendChild(overlay);

// E. Elevate Target Element
el.style.position = 'relative';
el.style.zIndex = '1000000';
el.style.backgroundColor = '#ffffff'; // Ensure solid background
el.style.border = 'none'; // Explicitly remove any borders
```

## 4. Capture & Save
*   **Tool:** Use `mcp_chrome-devtools_take_screenshot`.
*   **Scope:** Capture the viewport (do NOT use `fullPage: true`).
*   **Output:** Save directly to `public/assets/screenshots/<filename>.png`.
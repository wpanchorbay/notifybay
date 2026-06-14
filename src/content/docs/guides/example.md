---
title: Example Guide
description: A boilerplate example of a guide page.
---

This is an example guide page. You can use standard Markdown and MDX features.

## Code Blocks

You can write standard Markdown code blocks:

```js
function helloWorld() {
  console.log("Hello, Boilerplate!");
}
```

## Callouts

You can use Starlight's built-in aside elements:

:::tip
This is a helpful tip!
:::

:::danger
Watch out for this!
:::

## Images

Place screenshot files in `public/assets/screenshots/`. They are served at `{BASE_PATH}/assets/screenshots/your-image.png`.

### Border + lightbox (click to enlarge)

Use a raw `<img>` tag with `data-lightbox="true"`. All content images get a rounded border automatically.

<img src="/docs-boilerplate-starlight/assets/screenshots/example-screenshot.png" alt="Example screenshot with border and lightbox" data-lightbox="true" />

```html
<img
  src="/docs-boilerplate-starlight/assets/screenshots/example-screenshot.png"
  alt="Example screenshot with border and lightbox"
  data-lightbox="true"
/>
```

### Border only (no lightbox)

Standard Markdown image syntax gets the auto-border. Lightbox is opt-in only.

![Example screenshot with border only](/docs-boilerplate-starlight/assets/screenshots/example-screenshot.png)

```markdown
![Example screenshot with border only](/docs-boilerplate-starlight/assets/screenshots/example-screenshot.png)
```

### No border, no lightbox

Add `data-no-border` to strip the border and radius.

<img src="/docs-boilerplate-starlight/assets/screenshots/example-screenshot.png" alt="Example screenshot with no border" data-no-border />

```html
<img
  src="/docs-boilerplate-starlight/assets/screenshots/example-screenshot.png"
  alt="Example screenshot with no border"
  data-no-border
/>
```

### Lightbox but no border

Combine both attributes for a borderless zoomable image.

<img src="/docs-boilerplate-starlight/assets/screenshots/example-screenshot.png" alt="Example screenshot with lightbox but no border" data-lightbox="true" data-no-border />

```html
<img
  src="/docs-boilerplate-starlight/assets/screenshots/example-screenshot.png"
  alt="Example screenshot with lightbox but no border"
  data-lightbox="true"
  data-no-border
/>
```

### Behaviour summary

| Syntax | Border + radius | Click opens lightbox |
|---|---|---|
| `![alt](src)` — standard Markdown | ✅ yes | ❌ no |
| `<img data-lightbox="true">` | ✅ yes | ✅ yes |
| `<img data-no-border>` | ❌ no | ❌ no |
| `<img data-lightbox="true" data-no-border>` | ❌ no | ✅ yes |

The lightbox closes on: clicking the dark backdrop, clicking the **×** button, or pressing **Escape**.

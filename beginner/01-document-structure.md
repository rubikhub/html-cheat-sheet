# HTML Document Structure

> Tags inside `<head>` — configure the browser, define metadata, and load resources. Not rendered in the viewport.

---

## Metadata & Document Info

### `<!DOCTYPE html>`

- **Type:** Declaration
- Declares HTML5 document type. Must be the first line. Puts browser in **standards mode**.

```html
<!DOCTYPE html>
```

### `<html>`

- **Type:** Root
- Root element wrapping all page content. The **lang** attribute sets language for screen readers and SEO.

```html
<html lang="en">
  ...
</html>
```

### `<head>`

- **Type:** Container
- Contains all metadata — title, charset, viewport, stylesheets, scripts, favicons, and SEO tags.

```html
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>My Page</title>
</head>
```

### `<title>`

- **Type:** Metadata
- Sets the page title shown in browser tabs, bookmarks, and search engine results. Critical for **SEO**.

```html
<title>My Website — Home</title>
```

### `<meta>`

- **Type:** Metadata
- Key-value metadata: **charset**, **viewport** (mobile responsive), **description** (search snippets), **robots**, **Open Graph** (social media previews).

```html
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<meta name="description" content="A comprehensive HTML reference" />
<meta property="og:title" content="HTML Reference" />
```

### `<base>`

- **Type:** Metadata
- Sets a **base URL** for all relative links. Useful in email templates and CMS pages.

```html
<base href="https://example.com/" target="_blank" />
```

---

## Resource Linking

### `<link>`

- **Type:** Resource
- Links external resources: **stylesheets** (rel="stylesheet"), **favicon** (rel="icon"), **preconnect** to CDNs, **preload** fonts/images, **canonical URL** for SEO.

```html
<link rel="stylesheet" href="/css/main.css" />
<link rel="icon" href="/favicon.ico" />
<link rel="preconnect" href="https://fonts.googleapis.com" />
```

### `<style>`

- **Type:** Resource
- Embeds **CSS** directly in HTML. Used for **critical CSS**, email templates, and web components with Shadow DOM.

```html
<style>
  body {
    margin: 0;
    font-family: sans-serif;
  }
</style>
```

---

## Scripting

### `<script>`

- **Type:** Scripting
- Embeds/references **JavaScript**. Use **defer** (recommended), **async** (analytics), or **type="module"** (ES6 imports).

```html
<script src="/js/app.js" defer></script>

<script type="module">
  import { createApp } from "./app.js";
</script>
```

### `<noscript>`

- **Type:** Scripting
- Shows fallback content when **JavaScript is disabled**. Essential for progressive enhancement.

```html
<noscript>
  <p>Please enable JavaScript to use this application.</p>
</noscript>
```

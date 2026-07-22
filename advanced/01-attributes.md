# HTML Attributes

> Every HTML attribute — global, form, media, table, and scripting. Each with use cases, applicable tags, values, and code examples.

---

## Global Attributes

> Usable on ALL elements

### Identity & Classification

#### `id`

- **Type:** Global
- **Unique identifier**. Used by CSS (`#id`), JS (`getElementById`), and **anchor links** (#section-id). Must be unique per page.
- **Value:** Any string

```html
<div id="hero">Welcome</div>
<a href="#hero">Scroll to hero</a>
```

#### `class`

- **Type:** Global
- **Space-separated class list** for CSS styling and JS selection. Most common attribute in HTML.
- **Value:** Space-separated tokens

```html
<p class="highlight large">Styled text</p>
```

#### `style`

- **Type:** Global
- **Inline CSS**. Overrides external stylesheets. Use for **dynamic JS styling** and **email templates**.
- **Value:** CSS declarations

```html
<p style="color:red;font-size:20px">Red text</p>
```

### Behavior & Interaction

#### `hidden`

- **Type:** Global
- **Removes from rendering** and accessibility tree. Element still in DOM for JS toggling.
- **Value:** Boolean

```html
<div hidden>Invisible</div>
<p>Only this is rendered</p>
```

#### `tabindex`

- **Type:** Global
- **Keyboard navigation order**. **0** = DOM order (rec). **-1** = JS focus only.
- **Value:** Integer

```html
<button tabindex="0">Tabbable</button>
```

#### `accesskey`

- **Type:** Global
- **Keyboard shortcut**. Browser-dependent (Alt+key). Use sparingly.
- **Value:** Single character

```html
<input accesskey="s" placeholder="Alt+S" />
```

#### `autofocus`

- **Type:** Global
- **Auto-focus on page load**. Only one per page. For search bars, login forms.
- **Value:** Boolean

```html
<input autofocus placeholder="Focused on load" />
```

#### `contenteditable`

- **Type:** Global
- **Makes content editable**. "true" = editable. For rich text editors, CMS editing.
- **Value:** "true" | "false" | ""

```html
<p contenteditable="true">Click to edit</p>
```

#### `draggable`

- **Type:** Global
- **Enables drag-and-drop**. Works with ondragstart, ondrop events.
- **Value:** "true" | "false"

```html
<div draggable="true">Drag me!</div>
```

#### `inert`

- **Type:** Global
- **Removes from tab order and interaction**. Skips screen readers.
- **Value:** Boolean

```html
<div inert>Cannot be focused</div>
```

### Text Direction & Language

#### `dir`

- **Type:** Global
- **Text direction**. "ltr" = left-to-right, "rtl" = right-to-left, "auto" = browser detect.
- **Value:** "ltr" | "rtl" | "auto"

```html
<p dir="rtl">Arabic text</p>
<p dir="ltr">English text</p>
```

#### `lang`

- **Type:** Global
- **Language of content** (BCP 47). Critical for accessibility, SEO, CSS `:lang()`.
- **Value:** BCP 47 tag

```html
<p lang="fr">Bonjour le monde</p>
<p lang="es">Hola mundo</p>
```

#### `translate`

- **Type:** Global
- **Controls translation**. "no" = keep original text.
- **Value:** "yes" | "no"

```html
<p translate="no">Do not translate</p>
```

### Custom Data & ARIA

#### `data-*`

- **Type:** Global
- **Custom data attributes**. Store private data. Access via element.dataset. For JS hooks, analytics.
- **Value:** data-{name}="value"

```html
<div data-user-id="42" data-role="admin">...</div>
<script>
  el.dataset.userId; // "42"
</script>
```

#### `role`

- **Type:** Global
- **ARIA role** for accessibility. "button", "navigation", "dialog", "alert", "tab", "search".
- **Value:** "button" | "navigation" | "dialog" | "alert" | ...

```html
<div role="button" tabindex="0">Click</div>
<div role="alert">Error!</div>
```

#### `aria-*`

- **Type:** Global
- **ARIA states/properties**: aria-label, aria-hidden, aria-expanded, aria-describedby, aria-live.
- **Value:** aria-{property}="value"

```html
<button aria-label="Close">x</button>
<div aria-hidden="true">Skipped</div>
<p aria-live="polite">Announced when changed</p>
```

#### `slot`

- **Type:** Global
- **Shadow DOM slot**. Assigns element to a named `<slot>` in a web component.
- **Value:** Slot name

```html
<my-card>
  <span slot="title">Title</span>
  <p slot="body">Body</p>
</my-card>
```

#### `part`

- **Type:** Global
- **Shadow DOM part** — exposes elements for external CSS via `::part()`.
- **Value:** Space-separated part names

```html
<div part="container">...</div>
<style>
  my-comp::part(container) {
    background: red;
  }
</style>
```

### Popover & Input Hints

#### `popover`

- **Type:** Global
- **Popover API**. "auto" = light dismiss + top layer. "manual" = close programmatically.
- **Value:** "auto" | "hint" | "manual"

```html
<button popovertarget="pop1">Toggle</button>
<div id="pop1" popover="auto">Content</div>
```

#### `inputmode`

- **Type:** Global
- **Virtual keyboard type**: "numeric", "decimal", "tel", "email", "url", "search", "none".
- **Value:** "none" | "text" | "decimal" | "numeric" | "tel" | "search" | "email" | "url"

```html
<input inputmode="numeric" placeholder="Number pad" />
```

#### `enterkeyhint`

- **Type:** Global
- **Virtual keyboard enter key**: "enter", "done", "go", "next", "search", "send".
- **Value:** "enter" | "done" | "go" | "next" | "search" | "send"

```html
<input enterkeyhint="search" />
```

#### `autocapitalize`

- **Type:** Global
- **Mobile auto-capitalization**: "off", "none", "sentences", "words", "characters".
- **Value:** "off" | "none" | "sentences" | "words" | "characters"

```html
<input autocapitalize="off" />
```

#### `spellcheck`

- **Type:** Global
- **Spell/grammar checking**. Disable for code, technical names.
- **Value:** "true" | "false"

```html
<input spellcheck="false" value="const x = 1" />
```

#### `nonce`

- **Type:** Global
- **CSP nonce** — one-time token for Content Security Policy.
- **Value:** Base64 string

```html
<script nonce="abc123">
  ...
</script>
```

---

## Form Attributes

### Input Types & Values

#### `type`

- **Type:** Input
- **Input type** — determines rendering and validation. Types: text, password, email, number, tel, url, search, date, datetime-local, time, month, week, color, range, file, checkbox, radio, hidden, submit, reset, button.

```html
<input type="text" />
<input type="email" placeholder="user@mail.com" />
<input type="number" min="0" max="100" />
<input type="date" />
<input type="color" />
<input type="range" />
```

#### `value`

- **Type:** Input, Option, Button, Li, Data
- **Default/initial value**. For inputs: pre-filled text. For options: data sent to server.
- **Value:** String

```html
<input type="text" value="Default text" />
<option value="react">React</option>
```

#### `placeholder`

- **Type:** Input, Textarea
- **Hint text** when empty. Disappears on focus. Not a label replacement — use `<label>`.
- **Value:** String

```html
<input placeholder="Search..." />
```

#### `name`

- **Type:** Input, Select, Textarea, Button, Form, Meta
- **Form field name** — key in form data sent to server. Same name on radios = mutually exclusive.
- **Value:** String

```html
<input name="email" type="email" />
<input type="radio" name="plan" value="basic" />
<input type="radio" name="plan" value="pro" />
```

#### `disabled`

- **Type:** Input, Select, Textarea, Button, Fieldset, Optgroup, Option
- **Disables the control**. Greyed out, not focusable, not submitted.
- **Value:** Boolean

```html
<input disabled placeholder="Cannot type" />
<button disabled>Cannot click</button>
```

#### `readonly`

- **Type:** Input, Textarea
- **Read-only** — can see and focus but not edit. Value IS submitted (unlike disabled).
- **Value:** Boolean

```html
<input readonly value="Cannot edit" />
```

#### `checked`

- **Type:** Input[type=checkbox], Input[type=radio]
- **Pre-selects checkbox/radio**. Boolean attribute.
- **Value:** Boolean

```html
<input type="checkbox" checked /> Checked
<input type="radio" name="x" checked /> Selected
```

#### `selected`

- **Type:** Option
- **Pre-selects dropdown option**.
- **Value:** Boolean

```html
<select>
  <option>Choose...</option>
  <option selected>Pre-selected</option>
</select>
```

### Validation

#### `required`

- **Type:** Input, Select, Textarea
- **Must be filled** before submit. Browser shows validation error if empty.
- **Value:** Boolean

```html
<input required type="email" placeholder="Required" />
```

#### `pattern`

- **Type:** Input
- **Regex validation**. Must match pattern. Shows title as error message.
- **Value:** Regex string

```html
<input pattern="[0-9]{3}-[0-9]{4}" title="Format: 123-4567" />
```

#### `minlength` / `maxlength`

- **Type:** Input, Textarea
- **Character count limits**. Browser validates on submit.
- **Value:** Integer

```html
<input minlength="3" maxlength="50" />
```

#### `min` / `max`

- **Type:** Input[type=number], Input[type=date], Input[type=range], Meter, Progress
- **Numeric/date range limits**. For numbers: min/max values. For dates: date range.
- **Value:** Number | Date

```html
<input type="number" min="0" max="100" value="50" />
<input type="range" min="0" max="100" />
```

#### `step`

- **Type:** Input[type=number], Input[type=date], Input[type=range]
- **Increment step**. step="1" = integers, step="0.01" = decimals.
- **Value:** Number | "any"

```html
<input type="number" step="0.01" placeholder="0.01 increments" />
<input type="number" step="5" placeholder="0, 5, 10, 15..." />
```

#### `multiple`

- **Type:** Input[type=email], Input[type=file], Select
- **Multiple values**. Email: comma-separated. File: multi picker. Select: Ctrl+Click.
- **Value:** Boolean

```html
<input type="file" multiple />
<select multiple>
  ...
</select>
```

#### `novalidate`

- **Type:** Form, Button[type=submit]
- **Disables browser validation**. Form submits even if fields fail.
- **Value:** Boolean

```html
<form novalidate>
  <input required />
  <button type="submit">Skips validation</button>
</form>
```

### Form Submission

#### `action`

- **Type:** Form
- **Server endpoint URL**. Where form data is sent on submit.
- **Value:** URL

```html
<form action="/api/submit" method="POST">
  <input name="email" type="email" />
  <button type="submit">Send</button>
</form>
```

#### `method`

- **Type:** Form
- **HTTP method**. "GET" = data in URL (search). "POST" = data in body (submissions).
- **Value:** "GET" | "POST" | "dialog"

```html
<form method="GET" action="/search">
  <input name="q" placeholder="Search..." />
  <button type="submit">Search</button>
</form>
```

#### `enctype`

- **Type:** Form
- **Form encoding**. "multipart/form-data" for file uploads.
- **Value:** "application/x-www-form-urlencoded" | "multipart/form-data" | "text/plain"

```html
<form enctype="multipart/form-data" method="POST">
  <input type="file" name="avatar" />
  <button type="submit">Upload</button>
</form>
```

#### `target`

- **Type:** A, Area, Form
- **Where to open**. "\_self" = same tab, "\_blank" = new tab.
- **Value:** "\_self" | "\_blank" | "\_parent" | "\_top"

```html
<a href="/page" target="_blank" rel="noopener"> Opens safely in new tab </a>
```

#### `formaction` / `formmethod` / `formtarget` / `formnovalidate`

- **Type:** Input[type=submit], Button[type=submit]
- **Override form attrs per button**. Multiple submit buttons pointing to different endpoints.
- **Value:** Overrides action/method/target/novalidate

```html
<form action="/save" method="POST">
  <button formaction="/save">Save Draft</button>
  <button formaction="/publish">Publish</button>
</form>
```

### Input Appearance & Hints

#### `size`

- **Type:** Input, Select
- **Visible width**. Character width for inputs. Number of visible options for select.
- **Value:** Integer

```html
<input size="20" placeholder="20 chars wide" />
```

#### `accept`

- **Type:** Input[type=file], Form, Button
- **Allowed file types**. MIME types or extensions.
- **Value:** MIME types or extensions

```html
<input type="file" accept="image/*" />
<input type="file" accept=".jpg,.png,.gif" />
```

#### `autocomplete`

- **Type:** Input, Form, Select, Textarea
- **Browser autofill**: "on"/"off", "email", "username", "current-password", "cc-number", "street-address".
- **Value:** "on" | "off" | "email" | "username" | "current-password" | ...

```html
<input autocomplete="email" type="email" />
<input autocomplete="current-password" type="password" />
```

#### `list`

- **Type:** Input
- **Links to `<datalist>`** for autocomplete suggestions.
- **Value:** Datalist id

```html
<input list="colors" placeholder="Pick or type..." />
<datalist id="colors">
  <option value="Red"></option>
  <option value="Green"></option>
  <option value="Blue"></option>
</datalist>
```

#### `wrap`

- **Type:** Textarea
- **Text wrapping on submit**. "soft" = as-is. "hard" = with line breaks (needs rows).
- **Value:** "soft" | "hard"

```html
<textarea wrap="hard" rows="4">...</textarea>
```

#### `form`

- **Type:** Input, Select, Textarea, Button, Fieldset, Output
- **Associates control with form** outside its ancestor.
- **Value:** Form id

```html
<form id="myform" action="/submit">
  <button type="submit">Submit</button>
</form>
<input name="field" form="myform" />
```

#### `rows` / `cols`

- **Type:** Textarea
- **Visible dimensions**. rows = lines, cols = character width. CSS preferred.
- **Value:** Integer

```html
<textarea rows="4" cols="40"></textarea>
```

---

## Link & Anchor Attributes

### `href`

- **Type:** A, Area
- **Destination URL**. Supports relative paths, anchors (#id), mailto:, tel:, javascript:.
- **Value:** URL

```html
<a href="/about">About page</a>
<a href="#section">Jump to section</a>
<a href="mailto:hi@example.com">Email us</a>
```

### `rel`

- **Type:** A, Area, Form, Link
- **Relationship to linked resource**. "noopener" for security, "nofollow" for SEO, "preload" for performance.
- **Value:** Space-separated tokens

```html
<a href="https://example.com" rel="noopener noreferrer">External</a>
<link rel="stylesheet" href="/css/main.css" />
```

### `download`

- **Type:** A, Area
- **Download instead of navigate**. Value = suggested filename.
- **Value:** Filename string (optional)

```html
<a href="/files/report.pdf" download="report.pdf">Download PDF</a>
```

### `hreflang`

- **Type:** A, Area, Link
- **Language of linked resource**. Used by browsers/search engines for language-specific results.
- **Value:** BCP 47 tag

```html
<a href="/fr/" hreflang="fr">Version Française</a>
```

---

## Media Attributes

### `src`

- **Type:** Img, Video, Audio, Script, Source, Iframe, Embed
- **Source URL** of the media resource.
- **Value:** URL

```html
<img src="photo.jpg" alt="Description" /> <video src="movie.mp4"></video>
```

### `alt`

- **Type:** Img, Area
- **Alternative text** for images. Required for accessibility and SEO. Empty alt="" = decorative.
- **Value:** String

```html
<img src="logo.png" alt="Company Logo" /> <img src="decorative.png" alt="" />
```

### `srcset`

- **Type:** Img, Source
- **Responsive image set**. Multiple images for different viewports/pixel densities.
- **Value:** Comma-separated image descriptors

```html
<img
  srcset="small.jpg 480w, large.jpg 1024w"
  src="fallback.jpg"
  alt="Responsive image"
/>
```

### `sizes`

- **Type:** Img, Source
- **Viewport-based sizes** for srcset. Tells browser which image to pick.
- **Value:** Media query + width pairs

```html
<img
  srcset="small.jpg 480w, large.jpg 1024w"
  sizes="(max-width: 600px) 480px, 1024px"
  src="fallback.jpg"
  alt="Responsive image"
/>
```

### `loading`

- **Type:** Img, Iframe
- **Loading behavior**. "lazy" = defer offscreen loading (performance). "eager" = immediate (default).
- **Value:** "lazy" | "eager"

```html
<img src="photo.jpg" alt="Description" loading="lazy" />
```

### `width` / `height`

- **Type:** Img, Video, Iframe, Canvas
- **Intrinsic dimensions**. Prevents layout shift (CLS). CSS can override.
- **Value:** Integer (pixels)

```html
<img src="photo.jpg" alt="Description" width="400" height="300" />
```

### `autoplay`

- **Type:** Video, Audio
- **Auto-play on load**. Most browsers block autoplay without muted.
- **Value:** Boolean

```html
<video autoplay muted loop>
  <source src="bg.mp4" type="video/mp4" />
</video>
```

### `controls`

- **Type:** Video, Audio
- **Show browser default controls** (play, pause, volume, fullscreen).
- **Value:** Boolean

```html
<video controls>
  <source src="video.mp4" type="video/mp4" />
</video>
```

### `loop`

- **Type:** Video, Audio
- **Loop playback**. Common for background videos and ambient audio.
- **Value:** Boolean

```html
<video loop muted autoplay>
  <source src="bg.mp4" type="video/mp4" />
</video>
```

### `muted`

- **Type:** Video, Audio
- **Muted by default**. Required for most autoplay policies.
- **Value:** Boolean

```html
<video muted autoplay>
  <source src="bg.mp4" type="video/mp4" />
</video>
```

### `poster`

- **Type:** Video
- **Thumbnail image** shown before video plays.
- **Value:** URL

```html
<video poster="thumbnail.jpg" controls>
  <source src="video.mp4" type="video/mp4" />
</video>
```

### `crossorigin`

- **Type:** Img, Video, Audio, Script
- **CORS request mode**. "anonymous" = no credentials, "use-credentials" = with credentials.
- **Value:** "anonymous" | "use-credentials"

```html
<img src="image.jpg" crossorigin="anonymous" />
```

### `sandbox`

- **Type:** Iframe
- **Security restrictions** for iframes. Restricts scripts, forms, popups, and more.
- **Value:** Space-separated tokens

```html
<iframe
  src="https://example.com"
  sandbox="allow-scripts allow-same-origin"
></iframe>
```

### `allow`

- **Type:** Iframe
- **Feature policy**. Controls which features the iframe can use (camera, microphone, etc.).
- **Value:** Feature policy string

```html
<iframe
  src="https://example.com"
  allow="camera; microphone; fullscreen"
></iframe>
```

---

## Table Attributes

### `colspan`

- **Type:** Td, Th
- **Span multiple columns**. Number of columns the cell should span.
- **Value:** Integer

```html
<tr>
  <td colspan="2">Spans two columns</td>
</tr>
```

### `rowspan`

- **Type:** Td, Th
- **Span multiple rows**. Number of rows the cell should span.
- **Value:** Integer

```html
<tr>
  <td rowspan="2">Spans two rows</td>
  <td>Row 1</td>
</tr>
<tr>
  <td>Row 2</td>
</tr>
```

### `scope`

- **Type:** Th
- **Header scope** for accessibility. "col" = column header, "row" = row header.
- **Value:** "col" | "row" | "colgroup" | "rowgroup"

```html
<th scope="col">Name</th>
<th scope="row">Total</th>
```

### `headers`

- **Type:** Td
- **Associated headers** for complex tables. Space-separated header cell IDs.
- **Value:** Space-separated IDs

```html
<th id="name">Name</th>
<td headers="name">John</td>
```

### `span` (colgroup/col)

- **Type:** Col, Colgroup
- **Number of columns** to affect. Default is 1.
- **Value:** Integer

```html
<colgroup>
  <col span="2" style="background:#f5f5f5" />
  <col />
</colgroup>
```

---

## Scripting Attributes

### `defer`

- **Type:** Script
- **Execute after HTML parsing**. Preserves DOM order. Recommended for most scripts.
- **Value:** Boolean

```html
<script src="app.js" defer></script>
```

### `async`

- **Type:** Script
- **Execute immediately when loaded**. No order guarantee. Use for analytics/third-party.
- **Value:** Boolean

```html
<script src="analytics.js" async></script>
```

### `type`

- **Type:** Script
- **MIME type or module**. "module" = ES6 imports. Omit for classic scripts.
- **Value:** MIME type | "module"

```html
<script type="module">
  import { createApp } from "./app.js";
</script>
```

### `integrity`

- **Type:** Script, Link
- **Subresource Integrity hash**. Verifies fetched resource hasn't been tampered with.
- **Value:** Base64-encoded hash

```html
<script
  src="https://cdn.example.com/lib.js"
  integrity="sha384-..."
  crossorigin="anonymous"
></script>
```

### `nomodule`

- **Type:** Script
- **Fallback for old browsers**. Script only runs if browser doesn't support ES modules.
- **Value:** Boolean

```html
<script nomodule src="legacy.js"></script>
```

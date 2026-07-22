# Inline Elements

> Elements that flow within text without starting on a new line — for formatting, linking, and data.

---

## Text Formatting & Emphasis

### `<span>`

- **Type:** Inline
- Generic inline container — for **styling** and **JS targeting**. The inline equivalent of `<div>`.

```html
<p>
  This is normal text with a
  <span class="highlight">highlighted span</span>
  inline.
</p>
```

### `<strong>`

- **Type:** Inline
- **Strong importance/urgency**. Renders bold. Screen readers add emphasis. Use for warnings and critical info.

```html
<p>
  <strong>Warning:</strong>
  Do not operate heavy machinery.
</p>
```

### `<em>`

- **Type:** Inline
- **Stress emphasis** — changes sentence meaning. Renders italic. Unlike `<i>`, it affects how text is read aloud.

```html
<p>This is <em>really</em> important — the emphasis changes the meaning.</p>
```

### `<b>`

- **Type:** Inline
- Visual attention **without semantic importance**. Bold. For product names, keywords, labels.

```html
<p>The <b>iPhone 15 Pro</b> features a titanium design.</p>
```

### `<i>`

- **Type:** Inline
- **Alternate voice/mood** — technical terms, foreign words, thoughts. Italic without stress emphasis.

```html
<p>The term <i>schadenfreude</i> is borrowed from German.</p>
```

### `<u>`

- **Type:** Inline
- **Underline** — annotation for proper names or misspellings. Be careful — underlines suggest links.

```html
<p>The <u>Python</u> programming language was created by Guido van Rossum.</p>
```

### `<mark>`

- **Type:** Inline
- **Highlighted text** — yellow bg by default. For search result matches and keyword highlighting.

```html
<p>Search results for "HTML": Learn <mark>HTML</mark> fundamentals.</p>
```

### `<small>`

- **Type:** Inline
- **Fine print** — copyright, disclaimers, legal text, photo credits.

```html
<p>
  All rights reserved.
  <small>&copy; 2026 Company Name</small>
</p>
```

### `<sub>`

- **Type:** Inline
- **Subscript** — chemical formulas (H₂O), math indices (x₁).

```html
<p>Water: H<sub>2</sub>O Math: x<sub>1</sub>, x<sub>2</sub></p>
```

### `<sup>`

- **Type:** Inline
- **Superscript** — exponents (mc²), ordinals (1st), trademarks.

```html
<p>Einstein: E=mc<sup>2</sup> 1<sup>st</sup> place · 2<sup>nd</sup> place</p>
```

### `<q>`

- **Type:** Inline
- **Short inline quotation**. Browser adds quotation marks automatically.

```html
<p>
  As Einstein said,
  <q>imagination is more important than knowledge</q>.
</p>
```

---

## Editorial & Text Changes

### `<s>`

- **Type:** Inline
- **Strikethrough** — no longer relevant. Common for **original prices** on sale items ($99.99 → $49.99).

```html
<p>
  Price:
  <s>$99.99</s>
  <strong>$49.99</strong>
</p>
```

### `<del>`

- **Type:** Inline
- **Deleted text** — formal revision. Paired with `<ins>` for changelogs, diffs, and version control.

```html
<p>
  <del>Old feature removed</del>
</p>
```

### `<ins>`

- **Type:** Inline
- **Inserted text** — underlined by default. Paired with `<del>` for revision tracking.

```html
<p>
  <ins>New feature added</ins>
</p>
```

---

## Code & Technical

### `<code>`

- **Type:** Inline
- **Code snippet** — monospace. Essential in every developer tutorial and documentation page.

```html
<p>
  Use <code>console.log()</code>
  for debugging.
</p>
```

### `<samp>`

- **Type:** Inline
- **Sample output** — terminal output, error messages, program responses.

```html
<p>Output: <samp>Hello World</samp></p>
```

### `<kbd>`

- **Type:** Inline
- **Keyboard input** — shortcut keys. Raised-button look. Used in VS Code, Figma, GitHub docs.

```html
<p>
  Press <kbd>Ctrl</kbd>+<kbd>C</kbd>
  to copy.
</p>
```

### `<var>`

- **Type:** Inline
- **Variable** — math expressions, programming parameters. Renders italic.

```html
<p>Let <var>x</var> = 10, then <var>x</var> * 2 = 20</p>
```

---

## Data, Links & Time

### `<a>`

- **Type:** Inline
- **Hyperlink** — the most fundamental web element. Supports **targets** (\_blank), **download**, **anchors** (#id), **mailto:**, **tel:**.

```html
<a href="https://example.com">Link</a>
<a href="#section-id">Anchor</a>
<a href="https://example.com" target="_blank"> External ↗ </a>
```

### `<abbr>`

- **Type:** Inline
- **Abbreviation** — title attribute shows full form on hover. Important for accessibility and SEO.

```html
<p>
  The <abbr title="HyperText Markup Language"> HTML </abbr> spec is maintained
  by WHATWG.
</p>
```

### `<time>`

- **Type:** Inline
- **Machine-readable date/time** — ISO 8601 format. Used for article dates, event schedules, timestamps.

```html
<p>
  Published on
  <time datetime="2026-07-13"> July 13, 2026 </time>
</p>
```

### `<data>`

- **Type:** Inline
- **Machine-readable value** — product IDs, SKU numbers, barcodes attached to display text.

```html
<p>
  Product:
  <data value="SKU-12345">Premium Widget</data>
</p>
```

### `<bdi>`

- **Type:** Inline
- **Bi-directional isolation** — prevents RTL text from breaking LTR layout.

```html
<ul>
  <li>English: <bdi>John</bdi></li>
  <li>Arabic: <bdi>ياسر</bdi></li>
</ul>
```

### `<bdo>`

- **Type:** Inline
- **Bi-directional override** — forces text direction (ltr/rtl).

```html
<p>
  <bdo dir="rtl"> This text is forced right-to-left </bdo>
</p>
```

### `<wbr>`

- **Type:** Inline
- **Word break opportunity** — suggests where a line break is allowed for long words/URLs.

```html
<p>
  https://example.com/this/is/a/very/
  <wbr />long/path/that/breaks/well
</p>
```

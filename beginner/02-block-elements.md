# Block-Level Elements

> Elements that start on a new line and take full width — the structural building blocks of web pages.

---

## Sectioning & Layout

### `<div>`

- **Type:** Block
- Generic block container — the backbone of CSS layouts. Used for **page wrappers**, **card grids**, **hero sections**, **modals**, and **component containers** in React/Vue.

```html
<div class="container">
  <p>I am a div — I start on a new line and take full width.</p>
</div>
```

### `<header>`

- **Type:** Block
- Introductory content at top of page/section. Contains **logo**, **nav menu**, **search bar**. Can be used inside each `<article>` too.

```html
<header>
  <h1>My Website</h1>
  <nav>...</nav>
</header>
```

### `<nav>`

- **Type:** Block
- Major **navigation blocks** — main menu, sidebar TOC, breadcrumbs, pagination. Screen readers offer shortcut to skip to content.

```html
<nav>
  <a href="/">Home</a>
  <a href="/products">Products</a>
  <a href="/contact">Contact</a>
</nav>
```

### `<main>`

- **Type:** Block
- The **unique, primary content** of the page — only one per page. Excludes header, footer, sidebar. Critical for **accessibility** and **SEO**.

```html
<main>
  <h2>Primary Content</h2>
  <p>Only one &lt;main&gt; per page.</p>
</main>
```

### `<section>`

- **Type:** Block
- **Thematic grouping** with a heading — "Features", "Pricing", "Testimonials", "FAQ". More semantic than `<div>`.

```html
<section>
  <h2>Features</h2>
  <p>Content for this section...</p>
</section>
```

### `<article>`

- **Type:** Block
- **Self-contained content** that could be distributed independently — blog posts, news articles, product cards, forum posts, user comments.

```html
<article>
  <h2>Blog Post Title</h2>
  <p>Author, Date — fully self-contained</p>
</article>
```

### `<aside>`

- **Type:** Block
- **Tangentially related content** — sidebars, callout boxes, pull quotes, ads, related articles panel.

```html
<aside>
  <h3>Related Articles</h3>
  <p>Sidebar or callout content</p>
</aside>
```

### `<footer>`

- **Type:** Block
- Page/section footer — **copyright**, **contact info**, **social links**, **privacy policy**, secondary navigation.

```html
<footer>
  <p>&copy; 2026 Company Name</p>
  <nav>
    <a href="/privacy">Privacy</a>
    <a href="/terms">Terms</a>
  </nav>
</footer>
```

### `<hgroup>`

- **Type:** Block
- Groups a **heading + subtitle/tagline**. Used in hero sections and article headers.

```html
<hgroup>
  <h1>HTML Reference</h1>
  <p>A comprehensive guide</p>
</hgroup>
```

---

## Headings

### `<h1>` — `<h6>`

- **Type:** Block
- **Section headings**. h1 = main topic (one per page), h2 = sections, h3 = subsections. Critical for **SEO** and **accessibility**. Never skip levels.

```html
<h1>Page Title</h1>
<h2>Section</h2>
<h3>Subsection</h3>
<h4>Minor Heading</h4>
<h5>Detail Heading</h5>
<h6>Lowest Heading</h6>
```

---

## Text Content

### `<p>`

- **Type:** Block
- **Paragraph** — the most used text container. Creates spacing above and below for readable text blocks.

```html
<p>
  This is a paragraph — the building block of all readable content on webpages.
</p>
```

### `<hr>`

- **Type:** Block
- **Thematic break** — horizontal line separating content topics.

```html
<p>Above the line</p>
<hr />
<p>Below the line</p>
```

### `<pre>`

- **Type:** Block
- **Preformatted text** — preserves spaces and line breaks. Essential for **code blocks** in documentation and tutorials.

```html
<pre>
const x = 10;
const y = 20;
console.log(x + y);
</pre>
```

### `<blockquote>`

- **Type:** Block
- **Quotation from another source** — indented. Used for testimonials, quotes, and cited passages.

```html
<blockquote>
  "A customer testimonial or quoted passage from another source."
</blockquote>
```

### `<address>`

- **Type:** Block
- **Contact information** for the page/article author — email, address, social links.

```html
<address>
  Written by
  <a href="mailto:author@example.com">John Doe</a><br />
  123 Web Dev Street, Internet City
</address>
```

### `<figure>`

- **Type:** Block
- Self-contained content (image, chart, code) with optional **`<figcaption>`** caption. Used for product images, infographics, diagrams.

```html
<figure>
  <img src="chart.png" alt="Sales chart" />
  <figcaption>Fig 1. — Caption describing the content</figcaption>
</figure>
```

---

## Lists

### `<ul>`

- **Type:** Block
- **Unordered (bulleted) list**. Standard pattern for **navigation menus**, **feature lists**, **category links**.

```html
<ul>
  <li>Free Shipping</li>
  <li>24/7 Support</li>
  <li>Money-Back Guarantee</li>
</ul>
```

### `<ol>`

- **Type:** Block
- **Ordered (numbered) list**. Supports **type** (A/a/I/i), **start**, **reversed**. Used for steps, rankings, countdowns.

```html
<ol>
  <li>Create project folder</li>
  <li>Run npm init</li>
  <li>Install dependencies</li>
</ol>
```

### `<dl>` + `<dt>` + `<dd>`

- **Type:** Block
- **Description list** — term/description pairs. Used for glossaries, FAQs, product specs, metadata displays.

```html
<dl>
  <dt>Battery Life</dt>
  <dd>Up to 30 hours playback</dd>
  <dt>Weight</dt>
  <dd>250 grams</dd>
</dl>
```

### `<menu>`

- **Type:** Block
- **Interactive item list** — toolbar actions, context menus. Visually identical to `<ul>` by default.

```html
<menu>
  <li>Cut</li>
  <li>Copy</li>
  <li>Paste</li>
</menu>
```

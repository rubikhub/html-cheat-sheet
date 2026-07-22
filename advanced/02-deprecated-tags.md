# Deprecated / Removed from HTML5

> Tags no longer valid in HTML5 — use CSS and modern alternatives instead.

---

## Do Not Use — CSS Equivalents Exist

### `<font>`

- → Use CSS `color`, `font-size`, `font-family`.

```html
<!-- ✗ Don't -->
<font color="red" size="5">Big red text</font>

<!-- ✓ Do -->
<span style="color:red;font-size:1.5rem"> Big red text </span>
```

### `<center>`

- → Use CSS `text-align: center`.

```html
<!-- ✗ Don't -->
<center>Centered text</center>

<!-- ✓ Do -->
<p style="text-align:center">Centered text</p>
```

### `<marquee>`

- → Use CSS `@keyframes` + `animation`.

```html
<!-- ✗ Don't -->
<marquee>Scrolling text</marquee>

<!-- ✓ Do -->
<style>
  @keyframes scroll {
    from {
      transform: translateX(100%);
    }
    to {
      transform: translateX(-100%);
    }
  }
  .scroll-text {
    animation: scroll 5s linear infinite;
  }
</style>
<p class="scroll-text">Scrolling text</p>
```

### `<blink>`

- → Use CSS animation.

```html
<!-- ✗ Don't -->
<blink>Flashing text</blink>

<!-- ✓ Do -->
<style>
  @keyframes blink {
    50% {
      opacity: 0;
    }
  }
  .blink-text {
    animation: blink 1s step-end infinite;
  }
</style>
<p class="blink-text">Flashing text</p>
```

### `<frame>` / `<frameset>`

- → Use `<iframe>` or CSS Grid/Flexbox.

```html
<!-- ✗ Don't -->
<frameset cols="25%,75%">
  <frame src="nav.html">
  <frame src="main.html">
</frameset>

<!-- ✓ Do -->
<div style="display:grid;grid-template-columns:1fr 3fr">
  <nav>Navigation</nav>
  <main>Content</main>
</div>
```

### `<acronym>`

- → Use `<abbr>`.

```html
<!-- ✗ Don't -->
<acronym title="HyperText Markup Language"> HTML </acronym>

<!-- ✓ Do -->
<abbr title="HyperText Markup Language"> HTML </abbr>
```

### `<big>`

- → Use CSS `font-size`.

```html
<!-- ✗ Don't -->
<big>Larger text</big>

<!-- ✓ Do -->
<span style="font-size:1.3em"> Larger text </span>
```

### `<tt>`

- → Use `<code>` or CSS `font-family: monospace`.

```html
<!-- ✗ Don't -->
<tt>Monospace text</tt>

<!-- ✓ Do -->
<code>Monospace text</code>
<span style="font-family:monospace"> Monospace text </span>
```

### `<strike>`

- → Use `<del>` or `<s>`.

```html
<!-- ✗ Don't -->
<strike>Old price</strike>

<!-- ✓ Do -->
<s>$99.99</s>
<del>Removed text</del>
```

### `<dir>`

- → Use `<ul>`.

```html
<!-- ✗ Don't -->
<dir>
  <li>Item 1</li>
  <li>Item 2</li>
</dir>

<!-- ✓ Do -->
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
```

# Interactive & Web Component Elements

> Built-in interactive UI components and web component primitives.

---

## Native Interactive

### `<details>`

- **Type:** Block
- **Expandable/collapsible accordion** — no JS needed. Used for FAQ sections, filter panels, code toggles.

```html
<details>
  <summary>Click to expand FAQ</summary>
  <p>Hidden content revealed on click.</p>
</details>
```

### `<dialog>`

- **Type:** Block
- **Modal dialog** — show()/showModal()/close(). No library needed for modals and popups.

```html
<dialog id="my-dialog">
  <h3>Modal Dialog</h3>
  <p>No library needed.</p>
  <button onclick="this.closest('dialog').close()">Close</button>
</dialog>
<button onclick="my-dialog.showModal()">Open</button>
```

### `<template>`

- **Type:** N/A
- **Inert HTML blueprint** — not rendered until cloned via JavaScript. Used in web components and dynamic UI.

```html
<template id="card-template">
  <div class="card">
    <h3></h3>
    <p></p>
  </div>
</template>

<script>
  const template = document.getElementById("card-template");
  const clone = template.content.cloneNode(true);
</script>
```

### `<slot>`

- **Type:** N/A
- **Content projection placeholder** in web components — receives external content into shadow DOM.

```html
<!-- Web component definition -->
<template>
  <div class="wrapper">
    <slot name="header">Default header</slot>
    <slot>Default content</slot>
  </div>
</template>

<!-- Usage -->
<my-card>
  <span slot="header">Custom Title</span>
  <p>Custom body content</p>
</my-card>
```

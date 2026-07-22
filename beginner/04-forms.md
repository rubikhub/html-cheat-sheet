# Forms & Controls

> Input controls, form containers, and everything needed to collect user data.

---

## Input Elements

### `<input>`

- **Type:** Inline-Block
- Most versatile form element. Types: **text**, **password**, **email**, **number**, **tel**, **url**, **search**, **date**, **time**, **color**, **range**, **file**, **checkbox**, **radio**, **hidden**, **submit**, **reset**, **button**. Used in every web form — login, checkout, search, settings.

```html
<input type="text" placeholder="Search..." />
<input type="email" placeholder="user@example.com" />
<input type="password" placeholder="Password" />
```

### `<input type="checkbox">`

- **Type:** Inline-Block
- **Multi-select toggle** — terms agreement, filter controls, settings toggles, batch selectors.

```html
<label> <input type="checkbox" /> I agree to the Terms </label>
```

### `<input type="radio">`

- **Type:** Inline-Block
- **Single-select group** — pricing plans, payment methods, shipping options, sort order.

```html
<label><input type="radio" name="plan" checked /> Basic</label>
<label><input type="radio" name="plan" /> Pro</label>
<label><input type="radio" name="plan" /> Enterprise</label>
```

### `<input type="range">`

- **Type:** Inline-Block
- **Slider** — volume, brightness, price filters, zoom controls.

```html
<input type="range" min="0" max="100" value="60" />
```

### `<input type="color">`

- **Type:** Inline-Block
- **Color picker** — design tools, customization panels, brand color selectors.

```html
<input type="color" value="#ffffff" />
```

### `<input type="date">`

- **Type:** Inline-Block
- **Date picker** — booking forms, appointments, event creation, age inputs.

```html
<input type="date" />
```

### `<select>` + `<option>` + `<optgroup>`

- **Type:** Inline-Block
- **Dropdown menu** — country pickers, category filters, sort options, language selectors.

```html
<select>
  <option value="">Select framework...</option>
  <optgroup label="Frontend">
    <option>React</option>
    <option>Vue</option>
    <option>Svelte</option>
  </optgroup>
</select>
```

### `<textarea>`

- **Type:** Inline-Block
- **Multi-line text input** — comment boxes, contact forms, review forms, code editors.

```html
<textarea rows="3" placeholder="Write here..."></textarea>
```

### `<button>`

- **Type:** Inline-Block
- **Clickable button** — CTAs ("Sign Up Free", "Add to Cart"), form submits, toggles, icon buttons. Supports HTML content inside.

```html
<button>Primary</button> <button type="button">Secondary</button>
```

### `<datalist>`

- **Type:** Inline-Block
- **Autocomplete suggestions** for `<input>` — search suggestions, tag inputs, location pickers.

```html
<input list="colors" placeholder="Type a color..." />
<datalist id="colors">
  <option value="Red"></option>
  <option value="Green"></option>
  <option value="Blue"></option>
</datalist>
```

### `<progress>`

- **Type:** Inline-Block
- **Progress bar** — file uploads, downloads, multi-step forms, course completion.

```html
<progress value="65" max="100">65%</progress>
```

### `<meter>`

- **Type:** Inline-Block
- **Scalar gauge** — disk usage, battery level, relevance scores. Color changes based on thresholds.

```html
<meter value="0.75" min="0" max="1" low="0.3" high="0.8" optimum="0.9">
  75%
</meter>
```

### `<output>`

- **Type:** Inline-Block
- **Calculation result** — calculators, real-time totals, conversion results.

```html
<form onoutput="result.value=a.value*b.value">
  <input id="a" type="number" value="6" />
  &times;
  <input id="b" type="number" value="7" />
  =
  <output name="result">42</output>
</form>
```

---

## Form Layout Containers

### `<form>`

- **Type:** Block
- **Form container** — collects and submits data. **action** = server endpoint, **method** = GET (search/filters) or POST (submissions). Used for login, checkout, contact, search forms.

```html
<form action="/submit" method="POST">
  <label>Name</label>
  <input type="text" name="name" />
  <button type="submit">Send</button>
</form>
```

### `<fieldset>`

- **Type:** Block
- **Groups related controls** with a visual border. Essential for **accessibility** — screen readers announce the group name.

```html
<fieldset>
  <legend>Shipping Address</legend>
  <label>Street</label>
  <input type="text" name="street" />
</fieldset>
```

### `<label>`

- **Type:** Inline/Block
- **Accessible label** for form controls. Clicking focuses the input. Critical for **accessibility** — never skip labels.

```html
<label for="email">Email Address</label>
<input type="email" id="email" name="email" />
```

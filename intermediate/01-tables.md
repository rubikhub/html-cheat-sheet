# Table Elements

> Structured tabular data with rows, columns, headers, and footers.

---

## Table Structure

### `<table>`

- **Type:** Table
- **Tabular data** — rows & columns. Children: `<caption>`, `<thead>`, `<tbody>`, `<tfoot>`, `<tr>`, `<th>`, `<td>`, `<colgroup>`/`<col>`. Used for data tables, pricing comparisons, schedules. Not for layout — use CSS Grid/Flexbox instead.

```html
<table>
  <caption>
    Product Comparison
  </caption>
  <thead>
    <tr>
      <th>Feature</th>
      <th>Basic</th>
      <th>Pro</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Storage</td>
      <td>10GB</td>
      <td>100GB</td>
    </tr>
    <tr>
      <td>Support</td>
      <td>Email</td>
      <td>24/7</td>
    </tr>
  </tbody>
</table>
```

### `<caption>`

- **Type:** Block
- **Table title** — describes the table's purpose. Required for accessibility — screen readers announce it.

```html
<table>
  <caption>
    Monthly Revenue
  </caption>
  ...
</table>
```

### `<thead>`

- **Type:** Header Group
- **Table header rows** — groups header cells. Browsers render above `<tbody>` and repeat on page breaks for print.

```html
<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Role</th>
    </tr>
  </thead>
  ...
</table>
```

### `<tbody>`

- **Type:** Row Group
- **Table body rows** — contains the main data rows. The default container for `<tr>` if `<thead>`/`<tfoot>` aren't used.

```html
<table>
  ...
  <tbody>
    <tr>
      <td>React</td>
      <td>Frontend</td>
    </tr>
    <tr>
      <td>Node.js</td>
      <td>Backend</td>
    </tr>
  </tbody>
  ...
</table>
```

### `<tfoot>`

- **Type:** Footer Group
- **Table footer rows** — summaries, totals, notes. Rendered before `<tbody>` in source order for print.

```html
<table>
  ...
  <tfoot>
    <tr>
      <td colspan="2">2 frameworks listed</td>
    </tr>
  </tfoot>
</table>
```

### `<tr>`

- **Type:** Table Row
- **Table row** — contains `<th>` or `<td>` cells. Each `<tr>` defines one horizontal row.

```html
<tr>
  <td>React</td>
  <td>198K stars</td>
</tr>
```

### `<th>`

- **Type:** Table Cell
- **Header cell** — bold and centered by default. Use **scope** (col/row) for accessibility. Defines what the column or row is about.

```html
<tr>
  <th scope="col">Framework</th>
  <th scope="col">Stars</th>
</tr>
```

### `<td>`

- **Type:** Table Cell
- **Data cell** — contains the actual data. Supports **colspan** and **rowspan** for spanning multiple columns/rows.

```html
<tr>
  <td>React</td>
  <td colspan="2">198K stars</td>
</tr>
```

---

## Table Columns

### `<colgroup>` + `<col>`

- **Type:** Column Group
- **Column styling** — applies styles to entire columns without per-cell markup. Use **span** to affect multiple columns.

```html
<table>
  <colgroup>
    <col style="background:#f5f5f5" />
    <col span="2" />
  </colgroup>
  <tbody>
    <tr>
      <td>First column styled</td>
      <td>Normal</td>
      <td>Normal</td>
    </tr>
  </tbody>
</table>
```

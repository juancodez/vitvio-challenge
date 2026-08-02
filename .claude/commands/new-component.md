# /new-component

Creates a new UI component scaffold for Bit.Bio.

## Usage
`/new-component <ComponentName>`

## What it does
1. Creates `src/components/<component-name>/` folder
2. Creates `index.html` with semantic markup
3. Creates `styles.css` with CSS custom properties from `design-tokens.json`
4. Adds a usage note to this command file

## Template
```html
<!-- src/components/ComponentName/index.html -->
<div class="bb-component-name">
  <!-- content -->
</div>
```
```css
/* src/components/ComponentName/styles.css */
.bb-component-name {
  font-family: var(--font-sans);
  color: var(--color-neutral-900);
}
```

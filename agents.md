# AGENTS.md

## Architecture

This is a single static HTML page (`index.html`) — no framework, no build step, no bundler. All CSS lives in a `<style>` block in the `<head>`, and all JS lives in a `<script>` block before `</body>`. There is nothing to compile; the file is deployed as-is.

## Bilingual content pattern

The site supports Serbian (default) and English via a CSS/data-attribute toggle, not routing or duplicate pages:

- Every piece of translatable text is duplicated: one element/attribute with `data-sr` and a sibling with `data-en`.
- `html[data-lang="en"]` CSS rules flip visibility between the two.
- A language switch in the top-right corner sets `document.documentElement.setAttribute('data-lang', ...)`.
- When adding new copy, always add both a `data-sr` and a `data-en` version — an element with only one will show as blank (or never hide) in the other language.

## Images

Image locations are declared as `.img-slot` divs with a `style="background-image:url('images/...')"` and a `data-label` describing what should go there. No real photography has been supplied yet, so these render as dashed placeholder boxes. To add real images, drop files into `images/` at the exact paths already referenced in the markup (e.g. `images/logo.png`, `images/hero.jpg`, `images/proizvod-1.jpg`) — no markup changes needed.

## Order form

The order form (`#poruci`) uses Netlify Forms (`data-netlify="true"` + hidden `form-name` field + honeypot field). Submissions appear in the Netlify UI under Forms — there is no custom backend or database. To add a field, add the corresponding `<input>`/`<select>` inside the form; Netlify's build-time HTML parser picks up new fields automatically, no extra registration needed.

The "pickup or delivery" radio toggles the address fields via a small inline script (`#address-block` / `.show` class) — keep that logic in sync if the fulfillment options change.

## Adding a product

Copy one `.prod` block inside `.prod-grid` (a commented example template is left in `index.html` right after the existing products) and update the image, name (`data-sr`/`data-en`), specs, description, and status. The grid layout auto-adjusts to any number of products.

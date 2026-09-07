# Vasiljević Distillery — Budin Barrel

A single-page bilingual (Serbian/English) marketing and ordering site for Vasiljević Distillery, a family-run brandy (rakija) producer from Smederevo, Serbia. The site tells the brand story, showcases the current product range, and lets visitors submit an order or cooperation inquiry directly through a form.

## Key technologies

- Plain HTML, CSS, and vanilla JavaScript — no build step or framework
- Netlify Forms for serverless order submissions (no backend code required)
- Google Fonts (Cinzel, EB Garamond)

## Structure

- `index.html` — the entire site: markup, styles, and scripts in one file
- `images/` — placeholder folder for product and brand photography (logo, hero shot, product labels, etc.). Currently empty; the page renders dashed placeholder boxes until real images are added at the paths referenced in `index.html` (e.g. `images/logo.png`, `images/hero.jpg`).

## Running locally

No build tools are required. Either:

- Open `index.html` directly in a browser, or
- Use the Netlify CLI for full local emulation, including Netlify Forms:

```bash
netlify dev --port 8889
```

Then visit `http://localhost:8889`.

## Deploying

Push to the connected Netlify site. Netlify Forms is auto-detected from the `data-netlify="true"` form in `index.html`; no extra configuration is needed.

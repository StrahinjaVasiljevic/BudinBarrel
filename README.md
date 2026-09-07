# 🥃 Budin Barrel — Vasiljević Distillery

Premium bilingual landing page for **Budin Barrel**, a Serbian craft rakija brand produced by **Vasiljević Distillery**.

The website is designed to present the distillery's heritage, production process, product portfolio, and ordering system through an elegant luxury-inspired user experience.

---

## ✨ Features

- 🇷🇸 Serbian / 🇬🇧 English language switch
- Responsive design for desktop and mobile devices
- Luxury winery & distillery inspired aesthetic
- Scroll animations using Intersection Observer
- Sticky navigation with scroll progress indicator
- Interactive flip cards for product presentation
- Netlify-ready order form
- Pickup / Delivery order options
- Dynamic address fields
- Fully static HTML/CSS/JavaScript implementation
- No external frameworks required

---

## 📂 Project Structure

```text
/
│
├── index.html
├── images/
│   ├── logo.png
│   ├── hero.jpg
│   ├── mapa.jpg
│   ├── burad.jpg
│   ├── proces.jpg
│   ├── proizvod-1.jpg
│   ├── proizvod-2.jpg
│   ├── proizvod-3.jpg
│   └── proizvod-4.jpg
│
└── README.md
```

---

## 🖼 Required Images

The website expects the following assets inside the `images/` directory:

| File | Description |
|--------|--------|
| logo.png | Distillery logo |
| hero.jpg | Main hero image |
| mapa.jpg | 45th parallel map section |
| burad.jpg | Barrel feature background |
| proces.jpg | Production process image |
| proizvod-1.jpg | Limited Release Šljivovica |
| proizvod-2.jpg | Limited Release Kajsija |
| proizvod-3.jpg | Suva Šljiva Limited Edition |
| proizvod-4.jpg | Degustaciona kolekcija |

---

## 🚀 Deployment

### GitHub Pages

1. Create a new repository.
2. Upload all project files.
3. Push to GitHub.
4. Open:

```text
Settings → Pages
```

5. Under **Source**, select:

```text
Deploy from a branch
```

6. Choose:

```text
main → /root
```

7. Save.

Your website will be published automatically.

---

## 📦 Netlify Forms Support

The order form is configured for Netlify Forms:

```html
<form
  class="order-form"
  name="porudzbina"
  method="POST"
  data-netlify="true"
  netlify-honeypot="bb-field">
```

When deployed on Netlify, submissions are collected automatically without additional backend setup.

---

## 🌍 Languages

The site supports:

- Serbian (default)
- English

Language switching is handled using:

```html
data-sr
data-en
```

and

```javascript
document.documentElement.setAttribute('data-lang', lang);
```

---

## 🎨 Design Highlights

- Cinzel typography for luxury branding
- EB Garamond typography for reading comfort
- Burgundy, gold and cream color palette
- Oak barrel inspired aesthetics
- Grain texture overlay
- Glassmorphism panels
- Smooth scrolling experience

---

## 🥃 Product Line

Current products:

- Limited Release Šljivovica
- Limited Release Kajsija
- Suva Šljiva Limited Edition
- Degustaciona kolekcija

Each product uses a flip-card interface with:

- Product image
- Specifications
- Description
- Direct ordering link

---

## ➕ Adding a New Product

Duplicate any existing `.prod` block inside:

```html
<div class="prod-grid">
```

Then update:

- Product image
- Product name
- Alcohol percentage
- Bottle volume
- Product description

The grid automatically adjusts to additional items.

---

## 📱 Browser Support

Tested for modern browsers:

- Google Chrome
- Microsoft Edge
- Mozilla Firefox
- Safari
- Mobile Chrome
- Mobile Safari

---

## ⚠️ Alcohol Notice

This website promotes alcoholic beverages.

Consumption is intended exclusively for persons aged **18+**.

Please consume responsibly.

---

## © Copyright

© 2026 Budin Barrel · Vasiljević Distillery

All rights reserved.

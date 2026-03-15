# chrislyntang.com — Personal Website

A fully responsive personal branding website for Chrislyn Tang. Built as a single `index.html` file — no build tools, no dependencies, deploys anywhere.

## Features

- **Home** — Hero section, about strip, topic cards, featured articles
- **Articles** — Filterable article feed (Gardening / Business Consulting / Technology) with full article reader
- **Shop** — Product catalogue with live cart, drawer checkout, and filter by category
- **Responsive** — Mobile-first, works on all screen sizes
- **No dependencies** — Pure HTML, CSS, JavaScript. No npm, no bundler.

---

## How to Deploy (GitHub Pages)

1. Push `index.html` to your repo's `main` branch (root directory or `/docs`)
2. Go to **Settings → Pages**
3. Source: `Deploy from a branch` → `main` → `/ (root)`
4. Your site will be live at `https://chrislyntang.github.io/<repo-name>`

---

## How to Add a New Article

Open `index.html` and find the `ARTICLES` array near the bottom inside `<script>`. Add a new object:

```javascript
{
  id: 'art13',               // unique ID
  cat: 'garden',             // 'garden' | 'business' | 'tech'
  catLabel: 'Gardening',     // display label
  icon: '🌾',                // emoji for thumbnail
  thumbClass: 'thumb-moss',  // 'thumb-moss' | 'thumb-terra' | 'thumb-slate'
  title: 'Your Article Title',
  date: 'Jun 2025',
  readTime: '4 min read',
  body: `
    <p>Your first paragraph here...</p>
    <h3>A subheading</h3>
    <p>More content...</p>
    <blockquote>A memorable quote.</blockquote>
  `
}
```

That's it — the article will appear in the feed and be filterable immediately.

---

## How to Add a New Shop Product

Find the `PRODUCTS` array and add:

```javascript
{
  id: 'p13',
  cat: 'garden',             // 'garden' | 'business' | 'tech'
  catLabel: 'Garden',
  name: 'Product Name',
  icon: '🌻',
  imgBg: '#e8f0e8',          // background colour for product image area
  price: 19.90,
  desc: 'Short product description.',
  badge: 'New'               // or null for no badge
}
```

---

## Connecting a Real Checkout

The cart is fully functional (add, remove, adjust quantities). To connect a real payment processor:

### Option A — Stripe
Replace the `checkout()` function with a call to your Stripe Checkout session endpoint.

### Option B — Shopify Buy Button
Replace the products array with Shopify's storefront API and use their Buy SDK.

### Option C — Gumroad
Link each product's "Add to cart" button directly to a Gumroad product URL.

---

## Customising Content

| What | Where in the file |
|---|---|
| Your name / tagline | `<h1 class="hero-h">` and `<p class="hero-sub">` |
| Your photo | Replace the `<img src="...">` in the hero section |
| About text | `.about-strip-text` paragraphs |
| LinkedIn URL | `href="https://www.linkedin.com/in/chrislyntang/"` |
| Footer tagline | `.footer-tagline` |
| Colour scheme | CSS `:root` variables at the top of `<style>` |

---

## Colour Variables

| Variable | Default | Usage |
|---|---|---|
| `--terracotta` | `#b5543a` | Accents, CTAs, business category |
| `--moss` | `#3d5a3e` | Gardening category |
| `--slate` | `#2e3f52` | Technology category |
| `--cream` | `#faf8f3` | Page background |
| `--ink` | `#1a1a18` | Primary text + dark sections |

---

## File Structure

```
/
└── index.html    ← entire website (HTML + CSS + JS)
└── README.md
```

If you want to split into multiple files later, the CSS can be extracted to `style.css` and the script to `main.js` — just add `<link rel="stylesheet" href="style.css">` and `<script src="main.js"></script>` in the appropriate places.

---

## License

© Chrislyn Tang. All rights reserved.

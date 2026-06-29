# Jeevan Shakti Herbs — Website

A premium, fully responsive landing website for **Jeevan Shakti Herbs**,
built around the flagship product **Magic Fat Cutter**. Pure HTML, CSS and
JavaScript — no frameworks, no build step. Upload as-is to GitHub Pages,
Netlify, Vercel, or any static host.

## What's inside

```
jeevan-shakti/
├── index.html          → all page content, SEO meta, schema markup
├── style.css            → design system + every section's styling
├── script.js             → all interactivity (nav, theme, animations, forms)
├── assets/images/        → empty by default (see its own README.md)
└── README.md             → this file
```

## Design language

The site uses an "herbarium ledger" direction rather than a generic
wellness template: a deep forest palette, a warm turmeric-gold accent
(the brand's greens stay primary, gold is used sparingly for CTAs and
highlights), a serif display face (Fraunces) paired with Poppins for
body text, and specimen-label styling (thin rule + small-caps eyebrow)
used throughout for product and ingredient callouts.

All product, packaging, and lifestyle visuals are the client's real
product photography (bottle shots, box shots, and lifestyle scenes),
stored in `assets/images/`. Small UI icons (FAQ accordion, gallery zoom
icon, benefit icons, etc.) remain inline SVG, since those are decorative
UI elements rather than product imagery. See `assets/images/README.md`
for a full map of which photo is used where, and how to swap any of them
out later.

## Features included

- Glassmorphism sticky navbar with smooth scroll, active-link highlighting, and a mobile hamburger menu
- Animated hero with floating leaves, a typing-effect headline, and a scroll indicator
- Light/dark mode toggle (persisted in `localStorage`)
- Custom cursor on desktop pointer devices (auto-disabled on touch)
- Scroll-reveal animations on every section (IntersectionObserver-based)
- Animated counters in the hero and About section
- Product showcase with feature chips, suggested-usage and storage-info specimen labels
- Benefits grid, "Why Choose Us" grid
- Gallery with hover zoom, lightbox viewer (click, arrow keys, swipe-friendly)
- Auto-playing testimonial slider with manual dot navigation
- FAQ accordion (single-open behavior)
- Contact form with inline client-side validation (name, phone, email, message)
- Embedded Google Map for the Moradabad office
- Floating WhatsApp, Call, and Back-to-Top buttons
- SEO: meta description/keywords, Open Graph, Twitter Card, canonical tag, and JSON-LD schema (Organization, Product, FAQPage)
- Accessibility basics: skip link, visible focus states, aria-labels on icon buttons, `prefers-reduced-motion` support

## Before you publish — required edits

1. **Social links** — In both the Contact section and the Footer of
   `index.html`, search for `REPLACE_WITH_INSTAGRAM_HANDLE` and
   `REPLACE_WITH_FACEBOOK_PAGE` and replace them with your real profile
   URLs. They're commented in the HTML so they're easy to find.

2. **Domain** — The `<link rel="canonical">` tag and all Open
   Graph/Twitter `og:url` / `og:image` tags in the `<head>` currently use
   a placeholder domain (`https://www.jeevanshaktiherbs.com/`). Update
   these to your real domain once you have one.

3. **Contact form backend** — The form currently validates input in the
   browser and shows a success message, but it does **not** send email
   anywhere yet (a static site has no server to send from). To actually
   receive submissions, connect it to a form backend such as Formspree,
   Getform, or Netlify Forms — each typically just needs your form's
   `action` attribute changed to a URL they give you. Until then, treat
   WhatsApp and the phone/email links as the live contact channels.

4. **Open Graph image (optional polish)** — Social share previews
   currently reuse `lifestyle-flatlay-marble.jpeg`, which works fine but
   isn't cropped to the ideal 1200×630px social-preview ratio. If you
   want a tighter-looking preview on WhatsApp/Facebook/Twitter, add a
   dedicated 1200×630px image to `assets/images/` and point the
   `og:image` / `twitter:image` tags at it. See `assets/images/README.md`.

## Customizing colors

Every color in the site is a CSS variable at the top of `style.css`:

```css
:root {
  --primary-green: #2E7D32;
  --light-green: #66BB6A;
  --accent-green: #8BC34A;
  --turmeric: #C98A2C;     /* the one warm accent — CTAs, highlights */
  --forest-deep: #14301A;  /* dark sections, footer, navbar text in dark mode */
  --parchment: #F6F3EA;    /* main background */
  ...
}
```

Change a value once here and it updates everywhere the color is used —
buttons, icons, cards, dark mode, all of it.

## Local preview

No build tools needed. From inside the project folder, run any static
server, for example:

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080` in your browser. Opening `index.html`
directly by double-clicking also works for most features, though some
browsers restrict certain behaviors (like the Google Map iframe) when
loaded via `file://` — a local server avoids that.

## Deploying

This is a static site — there is no build step. Drag-and-drop or push
the whole folder to any of the following and you're live:

- **GitHub Pages**: push to a repo, enable Pages on the `main` branch, root folder.
- **Netlify**: drag the folder into the Netlify dashboard, or connect the repo.
- **Vercel**: import the repo, framework preset "Other," no build command needed.

## Browser support

Built with modern CSS (Grid, Flexbox, `backdrop-filter`, CSS custom
properties) and vanilla ES6+ JavaScript. Tested against current
Chrome, Edge, Firefox, and Safari. `backdrop-filter` (the glass navbar
effect) gracefully degrades to a solid background on the rare browser
that doesn't support it.

---

**Disclaimer copy reminder:** This site presents Magic Fat Cutter as an
Ayurvedic wellness supplement and avoids making medical claims, per the
brief. If you add new copy later, keep this in mind — avoid words like
"cure," "treat," or guaranteed results, and keep the suggested-usage
section pointing people to the product label and a healthcare
professional rather than giving dosage instructions yourself.

# VITHAL TECHNOLOGY — Corporate Website

A complete, static, 20-page corporate website for **VITHAL TECHNOLOGY** —
built with plain HTML5, CSS3 and vanilla JavaScript. No backend, no build
step, no framework. Ready to deploy directly on **GitHub Pages**.

---

## 1. Folder structure

```
VITHAL-TECHNOLOGY/
│
├── index.html            Home
├── about.html             About Vithal Technology
├── services.html          Technology Services
├── ai.html                AI & AI Agent Development
├── software.html          Software, Website & App Development
├── cybersecurity.html     Cyber Security Services
├── robotics.html          Robotics & Automation
├── manufacturing.html     Technology Manufacturing
├── products.html          Products
├── contact.html           Contact / Get a Quote
├── portfolio.html, careers.html, blog.html, case-studies.html,
│   team.html, testimonials.html, pricing.html, faq.html,
│   privacy-policy.html, terms.html     (10 additional pages)
├── 404.html               Custom "page not found" page
├── README.md              This file
├── robots.txt             Search engine crawling rules
├── sitemap.xml            Sitemap for search engines
├── favicon.ico            Browser tab icon
│
├── css/
│   ├── style.css           Core design system, layout & components
│   ├── responsive.css      Mobile / tablet breakpoints
│   └── animations.css      Keyframes & scroll-reveal animations
│
├── js/
│   ├── main.js             Mobile nav, scroll progress, back-to-top, counters
│   ├── animations.js       Scroll-reveal controller
│   ├── whatsapp.js         WhatsApp enquiry button logic
│   └── contact.js          Contact form validation + WhatsApp/email submit
│
└── assets/
    ├── logo.png             Main brand logo (used in header, footer, favicon, loader)
    ├── qr-placeholder.png    Placeholder QR (see section 12)
    ├── favicon.png           Favicon source image
    ├── hero/                 Put homepage hero imagery here (optional)
    ├── services/             Service-related imagery
    ├── ai/                   AI page imagery
    ├── software/             Software page imagery
    ├── cybersecurity/        Cyber security page imagery
    ├── robotics/             Robotics page imagery
    ├── manufacturing/        Manufacturing page imagery
    └── products/             Product photos (see section 8 below)
```

All internal links use **relative paths** (`css/style.css`, `js/main.js`,
`assets/logo.png`), so the site works correctly whether it's opened from
the root of a domain or from a GitHub Pages project subfolder
(`https://USERNAME.github.io/REPOSITORY-NAME/`).

---

## 2. Deploy to GitHub Pages — step by step

### Step 1 — Create a GitHub repository
1. Go to [github.com/new](https://github.com/new).
2. Name the repository, e.g. `VITHAL-TECH` (or anything you like).
3. Keep it **Public** (GitHub Pages on the free plan requires a public repo,
   unless you have GitHub Pro/Enterprise).
4. Click **Create repository**.

### Step 2 — Upload all files
**Option A — Web upload (easiest):**
1. Open your new repository on GitHub.
2. Click **Add file → Upload files**.
3. Drag in **everything inside this `VITHAL-TECHNOLOGY` folder** (not the
   folder itself — its *contents*: `index.html`, `css/`, `js/`, `assets/`,
   etc. should sit at the repository root).
4. Commit the upload.

**Option B — Git command line:**
```bash
cd VITHAL-TECHNOLOGY
git init
git remote add origin https://github.com/USERNAME/REPOSITORY-NAME.git
git add .
git commit -m "Initial launch of Vithal Technology website"
git branch -M main
git push -u origin main
```

### Step 3 — Confirm the folder structure on GitHub
Make sure `index.html`, `css/`, `js/`, `assets/`, `about.html`, etc. are all
visible at the **root** of the repository — not nested inside an extra
subfolder.

### Step 4 — Enable GitHub Pages
1. In your repository, go to **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Under **Branch**, select **main** and folder **/ (root)**.
4. Click **Save**.

### Step 5 — Select the deployment branch
This is done in the same step above — `main` / root is correct for this
project since there is no build step (no `dist/` or `docs/` folder needed).

### Step 6 — Open the live website
GitHub will show a message like:
> Your site is live at `https://USERNAME.github.io/REPOSITORY-NAME/`

It usually takes **1–2 minutes** after the first deploy. Open that URL —
the homepage (`index.html`) loads automatically.

### Step 7 — Update the sitemap and robots.txt with your real URL
Open `robots.txt` and `sitemap.xml` and replace every instance of:
```
https://USERNAME.github.io/REPOSITORY-NAME/
```
with your actual GitHub Pages URL. Also update the `SITE_URL` used for the
canonical/Open Graph tags if you regenerate the site from source (see
section 9).

### Step 8 — Updating the website later
Any time you want to make a change:
1. Edit the file(s) locally.
2. Commit and push again:
   ```bash
   git add .
   git commit -m "Update homepage copy"
   git push
   ```
3. GitHub Pages redeploys automatically within a minute or two.
   (If using the web upload method, just upload the changed files again.)

---

## 3. How to replace the logo

1. Replace `assets/logo.png` with your new logo file (keep the filename
   `logo.png`, or update every `<img src="assets/logo.png">` reference
   across all 11 HTML files if you rename it).
2. For best results, use a **square, transparent PNG**, at least 200×200px.
3. Also update `assets/favicon.png` and regenerate `favicon.ico` (any free
   online favicon generator, or Photoshop/GIMP export, works).

---

## 4. How to replace images

Every product/section image is currently a **clearly labelled placeholder**
(a dark panel with text like `AI CCTV CAMERA — place product photo here`).
No broken external image URLs are used anywhere on the site.

To add your own images:
1. Drop the image file into the matching `assets/<section>/` folder
   (e.g. `assets/products/ai-cctv-camera.jpg`).
2. In the relevant HTML file, find the placeholder block:
   ```html
   <div class="product-media"><span class="ph-label">AI CCTV CAMERA — place product photo here</span></div>
   ```
3. Replace it with a real `<img>` tag:
   ```html
   <div class="product-media"><img src="assets/products/ai-cctv-camera.jpg" alt="AI CCTV Camera" loading="lazy"></div>
   ```
4. Keep `loading="lazy"` for performance on pages with several images.

---

## 5. How to change the WhatsApp number

WhatsApp links are centralised in **one place**:

Open `js/whatsapp.js` and edit the top line:
```js
var VITHAL_WHATSAPP_NUMBER = "917498846061";
```
Use the full number with country code, **no `+`, no spaces, no dashes**.

Also update the matching constant used as a fallback in `js/contact.js`
(`917498846061`) so the contact form's "Send via WhatsApp" button matches.

---

## 6. How to change the email address

The email address appears in three places — update all three:
1. `js/contact.js` → the `mailto:` line inside the email submit handler.
2. Every page's footer → search for `vithaltechnology@gmail.com`.
3. `contact.html` → the "Email" entry in the contact info panel.

Tip: use your code editor's **Find & Replace across files** to change every
instance of `vithaltechnology@gmail.com` at once.

---

## 7. How to add a new service

1. Open `services.html`.
2. Find the `SERVICES` grid section (look for `<div class="grid grid-3 reveal">`
   under "ALL SERVICES").
3. Copy one `<div class="card service-card">…</div>` block and edit the
   icon, title and description.
4. If the service deserves its own dedicated page (like AI, Software,
   Cyber Security, Robotics or Manufacturing do), duplicate one of those
   HTML files as a starting template and add a matching link to the
   navigation menu (`<nav class="main-nav">`) in **every** HTML file, plus
   the footer's "SERVICES" column.

---

## 8. How to update products

1. Open `products.html`.
2. Each product is one `<div class="product-card">` block containing an
   image/placeholder, name, description and a WhatsApp enquiry button:
   ```html
   <div class="product-card">
     <div class="product-media"><span class="ph-label">PRODUCT NAME — placeholder</span></div>
     <div class="product-body">
       <h3>Product Name</h3>
       <p>Short description of the product.</p>
       <a href="#" class="btn btn-whatsapp btn-block" data-whatsapp="Product Name">Enquire on WhatsApp</a>
     </div>
   </div>
   ```
3. To add a new product, copy this block, change the text, and set
   `data-whatsapp="Your Product Name"` — this is the text that gets
   inserted into the pre-filled WhatsApp message automatically.
4. To remove a product, delete its `<div class="product-card">…</div>` block.

---

## 9. Regenerating the site from source (optional, for developers)

This site was generated from a small Python templating script so that the
shared header, footer and `<head>` metadata stay perfectly consistent
across all 20 pages. If you're comfortable with Python, the generator
files are included:

```
generator/build_site.py       Shared header/footer/head templates
icons.py             Inline SVG icon set + hero visual
content.py           Homepage content + shared helper functions
content_*.py         One file per page's unique content
run_build.py         Runs the generator and writes every HTML file
```

To regenerate after editing a `content_*.py` file:
```bash
cd generator && python3 run_build.py
```

**You do not need Python to run or deploy the website** — the generated
`.html`, `.css` and `.js` files are the actual deliverable and work as
plain static files. The generator is provided only for convenience if you
want to make bulk edits later.

---

## 10. Performance & SEO notes

- Every page has a unique `<title>`, meta description, Open Graph tags and
  semantic heading structure (H1 → H2 → H3).
- `robots.txt` and `sitemap.xml` are included — update the placeholder URL
  in both once your GitHub Pages URL is live (see Step 7 above).
- Images should be compressed and use `loading="lazy"` where added.
- Fonts (Space Grotesk, Inter, IBM Plex Mono) load from Google Fonts via
  `<link>` tags in the `<head>` — remove these and self-host if you need a
  fully offline-capable build.
- All CSS/JS is hand-written and unminified for readability. For a
  production performance boost, run them through a minifier before your
  final deploy.

---

## 11. Support

Questions about this build:
- WhatsApp: +91 74988 46061
- Email: vithaltechnology@gmail.com

© 2026 Vithal Technology. All Rights Reserved.

---

## 12. New in v2 (design refresh + 20 pages)

- **Navigation**: Services and Company dropdowns; FAQ, Privacy Policy and Terms are linked from the footer.
- **Search** (magnifier in header, or Ctrl/Cmd+K): finds pages by name.
- **Light/Dark theme toggle**: remembered in the visitor's browser.
- **QR code**: `assets/qr-placeholder.png` points to the placeholder URL. After deploying, generate a QR for your real URL (any free QR generator) and replace this file.
- **Newsletter box**: the site has no backend, so it only shows a notice. Connect Mailchimp / Formspree etc. to make it live.
- **Social links**: Facebook, LinkedIn, X and Telegram currently link to `#`. Replace the `#` values in the footer (search `aria-label="Facebook"` etc.) or in `SOCIAL_LINKS` in `build_site.py`.
- **Placeholder content**: Testimonials, Blog posts, Portfolio client slot, Team members and Pricing are clearly marked placeholders — no fake reviews or prices. Replace with real content.
- **Legal pages**: Privacy Policy and Terms are general templates; have them reviewed by a legal professional.
- Address shown in footer: Kalmeshwar, Nagpur, Maharashtra 441501.

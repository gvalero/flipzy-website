# Reading Companion — Landing Page

A single-page "fake door" landing page to validate demand for **Reading Companion**, an interactive voice-narration product for children's books (ages 4–10).

## What This Is

This is a **demand validation test**. The product currently exists as an Alexa Skill, and this page tests whether parents care enough to sign up for a waitlist. There is no app to download yet.

The page collects email addresses via a waitlist signup form so we can gauge interest before building further.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The complete landing page (HTML + CSS + JS in a single file) |
| `README.md` | This file |

## How to Deploy

### Option 1 — Static file hosting (quickest)

Upload `index.html` to any static host:

- **GitHub Pages:** Push to a repo, enable Pages in Settings → pick the branch/folder.
- **Netlify:** Drag-and-drop the folder at [app.netlify.com/drop](https://app.netlify.com/drop).
- **Vercel:** `npx vercel` in this directory.
- **AWS S3:** Upload to a public S3 bucket with static website hosting enabled.

### Option 2 — Local preview

Open `index.html` directly in a browser, or serve it locally:

```bash
# Python 3
python -m http.server 8000

# Node.js (npx, no install needed)
npx serve .
```

Then visit `http://localhost:8000`.

## Connecting the Waitlist Form

The signup form currently points to a **placeholder** Formspree endpoint:

```
action="https://formspree.io/f/placeholder"
```

To collect real emails, replace `placeholder` with your actual form ID from one of these services:

| Service | Setup |
|---------|-------|
| [Formspree](https://formspree.io) | Create a form → copy the endpoint → paste into `action` |
| [Google Forms](https://forms.google.com) | Create a form → embed or redirect to it |
| [Mailchimp](https://mailchimp.com) | Create a signup form → use their embedded form action URL |

## Updating Social Share Images

Replace the placeholder URLs in the `<meta>` tags near the top of `index.html`:

```html
<meta property="og:image" content="https://your-domain.com/your-image.png">
<meta name="twitter:image" content="https://your-domain.com/your-image.png">
```

Recommended image size: **1200 × 630 px** (PNG or JPG).

## Tech Notes

- **Zero dependencies** — single HTML file with embedded CSS and vanilla JS.
- **Mobile-responsive** — tested for screens from 320 px up.
- **Accessible** — semantic HTML, ARIA labels, `<noscript>` fallback.
- **Animations** — CSS fade-in on scroll via `IntersectionObserver` (graceful fallback for older browsers), hover effects on cards and buttons.

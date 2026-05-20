# Vynestro Holdings — vynestro.com

One-page marketing website for Vynestro Holdings, a private investment firm investing in Technology & Software, Real Estate, and FinTech.

## Stack

- Static HTML / CSS / JS (single file: `index.html`)
- No build step, no dependencies
- Fonts loaded from Google Fonts CDN
- Hosted on Vercel, deployed automatically from `main` branch

## Local preview

Open `index.html` directly in a browser, or run a local static server:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deployment

This repository is connected to Vercel. Any push to `main` triggers a production deploy. Custom domain `vynestro.com` is configured in the Vercel project settings.

## Editing

All content, styles, and scripts live in `index.html`. To change copy, hero text, segment descriptions, or contact details, edit that single file and commit.

## Contact

Form submissions are currently handled client-side only (no backend). To capture leads, swap the `handleSubmit` script for a Formspree, Resend, or Vercel Forms integration.

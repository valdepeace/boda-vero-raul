# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static wedding invitation website for Vero and Raul's wedding (April 4, 2026), deployed at **bodaveroyraul.com**.

No build step — CSS is pre-compiled and served directly. Local development uses VSCode Live Server on port 5501.

## Commands

```bash
# Deploy to GitHub Pages
npm run deploy
```

Primary deployment is via **Vercel** (auto-deploys from main branch). `vercel.json` rewrites all routes to `index.html`.

## Architecture

Single `index.html` with no framework — just jQuery + Bootstrap 3 + vanilla JS.

**Section order in index.html:**
1. Intro overlay (splash screen, auto-hides after 10s)
2. Navigation (fixed top bar)
3. Hero header with countdown timer (`simplyCountdown.js`)
4. Ceremony details + Google Maps link
5. RSVP confirmation (links to Google Form)
6. Transport info
7. Photos (GuestPix QR code)
8. Professional networks (vendor carousels via Swiper 11 CDN)
9. Gifts (Bizum/cash payment info)
10. Footer

**Key files:**
- `index.html` — entire page structure and content
- `sass/style.scss` — all custom styles (~1800 lines), compiled to `css/style.css`
- `js/main.js` — custom JS: mobile menu, parallax, scroll animations, smooth scroll, go-to-top

**CSS editing:** Edit `sass/style.scss`, then manually compile to `css/style.css`. No build watcher is configured — if you only have a CSS change, editing `css/style.css` directly is acceptable for quick fixes.

**Color palette:**
- Primary teal: `#0A837A`
- Accent pink: `#F14E95`
- Accent blue: `#118DF0`

**Fonts (loaded via Google Fonts CDN):** Work Sans (body), Sacramento & Great Vibes (script headings), Cormorant Garamond (serif)

**External CDN dependencies** (not in repo):
- Swiper 11 (carousel in vendor section)
- Google Fonts

# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static wedding invitation website for Vero and Raul's wedding (April 4, 2026), deployed at **bodaveroyraul.com**. Language is Spanish.

No build step — CSS is pre-compiled and served directly. Local development uses VSCode Live Server on port 5501.

## Commands

```bash
# Deploy to GitHub Pages (secondary)
npm run deploy
```

Primary deployment is via **Vercel** (auto-deploys from main branch). `vercel.json` rewrites all routes to `index.html`.

## Architecture

Single `index.html` with no framework — jQuery 2 + Bootstrap 3 + vanilla JS. Based on the fh5co wedding theme (hence `fh5co-` prefixed class names throughout).

**Key files:**
- `index.html` — entire page structure, content, and inline `<script>` block at the bottom with: simplyCountdown config, splash screen logic, IntersectionObserver scroll-fade, Swiper carousel init
- `sass/style.scss` — all custom styles (~1800 lines), compiled to `css/style.css`
- `js/main.js` — mobile menu, parallax (stellar.js), scroll animations (waypoints), smooth scroll, go-to-top
- `css/style.css` — compiled output; **edit directly for quick CSS fixes** since there's no build watcher

**Section order in index.html:**
1. Intro overlay (splash screen, auto-hides after 10s or on click)
2. Navigation (fixed top bar)
3. Hero header with countdown timer (`simplyCountdown.js`)
4. Ceremony details + Google Maps link
5. RSVP confirmation (links to Google Form)
6. Transport info
7. Photos (GuestPix QR code)
8. Professional networks (vendor cards with Swiper carousels)
9. Gifts (Bizum/cash payment info)
10. Footer

## Key Patterns

**Section backgrounds:** Sections use class `fh5co-bg` with an inline `background-image` style + a child `<div class="overlay"></div>` for the darkening layer. Parallax sections also get `data-stellar-background-ratio`.

**Scroll animations:** Add class `animate-box` to any element to trigger waypoint-based fade-in on scroll. Set `data-animate-effect="fadeIn|fadeInLeft|fadeInRight"` (default is `fadeInUp`).

**Section fade transitions:** Sections with class `scroll-fade` fade in/out via IntersectionObserver (adding/removing `in-view` class at 15% threshold).

**Adding a vendor card (Professional Networks):** Each vendor is an `<article class="person-carousel net-{instagram|linkedin|web}">` inside a `col-md-6` in the `#redes-sociales` section. Contains a `<header class="person-head">` (network icon, name, handle, link button) and a `<div class="swiper person-swiper">` with slides. Swiper carousels auto-initialize on desktop only (disabled on mobile via JS media query check).

## Color Palette & Fonts

- Primary teal: `#0A837A` (headings, icons)
- Accent pink: `#F14E95` (`$brand-primary` — buttons, links)
- Accent blue: `#118DF0` (`$brand-secondary`)

Fonts (Google Fonts CDN): Work Sans (body), Sacramento & Great Vibes (script headings), Cormorant Garamond (serif)

## External CDN Dependencies (not in repo)

- Swiper 11 — carousel in vendor section
- Google Fonts

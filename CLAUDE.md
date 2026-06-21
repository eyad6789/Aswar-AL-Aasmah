# Aswar-Website

Single-page bilingual (Arabic/English) marketing site for Aswar AlAsimah, a Baghdad general trading company (tools, electrical materials, furniture). Active; deployed manually to Hostinger shared hosting.

## Stack
- Pure static HTML/CSS/vanilla JS — no build system, no package.json, no framework, no dependencies to install.
- External resources via CDN only: Google Fonts (Tajawal, Plus Jakarta Sans, DM Serif Display) and Font Awesome 6.5.1.
- Apache `.htaccess` for HTTPS redirect, caching, compression, security headers.

## Structure
| Path | Purpose |
|---|---|
| `index.html` | Entry point — the entire site (one page, ~36 KB, sections: hero/about/services/products/why-us/contact) |
| `css/style.css` | All styles (~33 KB), CSS variables at top (navy/gold palette), RTL-aware |
| `js/main.js` | Preloader, navbar, scroll animations, counters, contact form demo, language switcher (~7 KB) |
| `js/translations.js` | `translations` object with `en`/`ar` keys used via `data-i18n` attributes (~18 KB) |
| `assets/` | 8 images (product PNGs, logo); largest is logo.png at 244 KB |
| `.htaccess` | Apache config — force HTTPS, expires headers, 404 → index.html |
| `README.md` | Hostinger deployment walkthrough |

## Commands
- No install/build/test steps — open `index.html` directly or serve: `python3 -m http.server 8000` from the project root. No tests exist.
- Deploy: manual upload of all files to Hostinger `public_html/` (see README.md).

## Conventions & Gotchas
- i18n: every translatable element has `data-i18n="key"`; keys live in `js/translations.js` (`en` and `ar` objects). Default language is Arabic (`lang="ar" dir="rtl"`); switcher persists choice in `localStorage.siteLang` and flips `dir`.
- Contact form is a FAKE demo — `js/main.js` simulates submission with setTimeout; no backend. README suggests Formspree/EmailJS to wire it up.
- Preloader hides only 2s after window load (hardcoded delay in main.js).
- Hardcoded contact data in index.html: WhatsApp +964 771 277 8800, domain aswaraleasima.com.
- Git status shows all files "modified" — these are file-mode (chmod) changes only, 0 content changes.
- `assets/logo.png` (244 KB) is not referenced by index.html; nav logo uses `assets/unnamed-removebg-preview.png`.
- `.htaccess` is a dotfile — easy to miss when copying/deploying.

## Do NOT read (large/irrelevant; also denied in .claude/settings.json)
- `.git/` internals
- Binary image files in `assets/` (check sizes with `ls -la assets/` only)

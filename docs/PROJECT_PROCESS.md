# HOBBYCLUB Website Project — Process Documentation

> A 5-page hobby website built as a school project. Presentation notes and design rationale.

---

## 1. Project Overview

- **Project Type:** School assignment (5-page static website)
- **Tech Stack:** HTML5, CSS3 — *No JavaScript allowed*
- **Goal:** Create a welcoming hub for hobbyists to explore different activities
- **Target Audience:** Beginners interested in gardening, hiking, motorcycling, and travel

---

## 2. Design Choices

### 2.1 Branding & Identity

| Decision | Rationale |
|----------|-----------|
| Rebranded from "HOBBYHUB" → "HOBBYCLUB" | More inclusive, community-focused feel |
| Husky logo (SVG) | Replaces generic crown emoji; adds personality |
| "No JS allowed" footer badge | Pride in pure HTML/CSS — aligns with assignment constraints |

### 2.2 Typography

- **Primary Font:** Slackey (display/headings) — playful, chunky, fits hobby theme
- **Fallback:** Arial (body text) — readability, universal support

### 2.3 Color Palette

```
--color-accent: #f78d65      # Warm orange — energy, creativity
--color-purple: #4a3b78      # Deep purple — imagination
--color-green: #8cc63f       # Fresh green — growth
--color-cyan: #4dcad2        # Bright cyan — modern feel
--color-gold: #deb841        # Gold — premium feel for logo
```

- All colors stored as CSS variables for easy iteration
- High contrast maintained for accessibility

### 2.4 Layout & UX

- **Sticky navigation** — always accessible
- **Card-based hobby selection** — clear visual hierarchy
- **Hero section with illustration shelf** — visual interest without images
- **Mobile-first responsive** — works on phones from the start

---

## 3. Key Features Implemented

### 3.1 Mobile Navigation (CSS-Only)

```css
/* Checkbox hack — no JS required */
.nav-toggle { display: none; }
.nav-toggle:checked + .nav-toggle-label + .nav-links { max-height: 320px; }
```

- Hamburger menu toggles via `<input type="checkbox">`
- Fully functional on mobile without JavaScript

### 3.2 Hero Animation (Home Page)

- Falling icons (yarn, rocket, projector, game controller) using CSS keyframes
- `animation-delay` staggered for natural feel
- Pure CSS — no JS libraries

### 3.3 CSS Architecture

- **Variables:** Centralized color/spacing tokens in `:root` and `.hobby-page`
- **Root-level definitions:** Easy theming — one place to change, whole site updates
- **Responsive breakpoints:** `@media (max-width: 768px)`
- **`clamp()`** for fluid typography and spacing — no abrupt jumps between breakpoints
- **Two-layer CSS split:** `style.css` for home, `sub-template.css` for all sub-pages

### 3.4 Sub-Page Template System

All four hobby sub-pages share a single layout defined in `sub-template.css`:

- **Hero section** — full-width with wave SVG background, large title and tagline
- **Intro section** — two-column grid: text left, image carousel right
- **Image carousel** — pure CSS animation (`@keyframes carousel-scroll`), 3 slides + 3 duplicates for seamless loop; `prefers-reduced-motion` respected
- **Resources section** — overlapping wave design using `::before`/`::after` pseudo-elements and a CSS `linear-gradient` background
- **Embedded video section** — shared responsive iframe wrapper between resources and the getting-started timeline
- **Getting Started timeline** — vertical timeline with colour-coded milestone dots
- **Accessibility:** `prefers-reduced-motion` disables carousel animation for motion-sensitive users; video sections include descriptive headings and `iframe` titles

### 3.5 Per-Page Theme System

Each hobby page has its own CSS file that overrides shared design tokens on a scoped body class (e.g. `body.hobby-gardening`):

| Page | Body Class | Key Palette |
|------|-----------|-------------|
| Gardening | `hobby-gardening` | Soft greens `#c6e6b4` |
| Hiking | `hobby-hiking` | Cool blues `#b8d7de` |
| Motorcycling | `hobby-motorcycling` | Muted purples `#c8c2e9` |
| Travel | `hobby-travel` | Warm peach `#f4c7a7` |

Key overrideable tokens per page:
- `--sub-hero-bg` — hero background colour
- `--sub-hero-bg-image` — hero wave SVG (each page can use a distinct wave asset)
- `--sub-intro-bg`, heading colors, text colors, timeline dot colors, etc.

### 3.6 Custom 404 Page

- Styled to match site branding
- Links back to home and hobby pages

---

## 4. Challenges & Solutions

| Challenge | Solution |
|-----------|----------|
| **No JavaScript allowed** | Leveraged CSS-only solutions: checkbox nav toggle, CSS animations, hover states |
| **Limited assets** | Created custom inline SVGs (yarn, rocket, husky, etc.) — lightweight, scalable |
| **Responsive design** | Flexbox + CSS Grid with mobile-first approach; `clamp()` for fluid typography |
| **Cross-page consistency** | Shared `sub-template.css` with CSS custom property tokens ensures uniform layout |
| **Per-page theming** | Scoped body class overrides (e.g. `body.hobby-gardening`) isolate palette changes |
| **Hero wave image per page** | `--sub-hero-bg-image` token in shared template, overridden per page CSS file |
| **Seamless carousel loop** | Six-slide track (3 real + 3 duplicate) with carefully timed `@keyframes` percentages |
| **Resources wave overlap** | Negative `margin-top` + `::before`/`::after` pseudo-elements create layered wave effect |

---

## 5. File Structure

```
/
├── index.html              # Home page
├── gardening.html          # Gardening sub-page
├── hiking.html             # Hiking sub-page
├── motorcycling.html       # Motorcycling sub-page
├── travel.html             # Travel sub-page
├── 404.html                # Custom 404 page
├── template.html           # Sub-page template (working reference)
├── style.css               # Main / home stylesheet
├── sub-template.css        # Shared sub-page layout & design tokens
├── gardening.css           # Gardening page palette & hero overrides
├── hiking.css              # Hiking page palette & hero overrides
├── motorcycling.css        # Motorcycling page palette & hero overrides
├── travel.css              # Travel page palette & hero overrides
├── checklist.md            # Requirement checklist and priority tracking
├── fonts/
│   └── Slackey/            # Custom display font
├── images/
│   ├── *.svg               # Shared icons (yarn, rocket, husky, etc.)
│   ├── hero-wavy-svg-*.svg # Shared hero wave graphics
│   ├── gardening-sub-hero-wave.svg
│   ├── hiking-sub-hero-wave.svg
│   └── motorcycling-sub-hero-wave.svg
├── docs/
│   ├── PROJECT_PROCESS.md
│   ├── Website Technical Requirements Outline.txt
│   └── website-plan.md
├── layout-options/         # Archived layout explorations
│   ├── template-skillpath.html
│   └── template-skillpath.css
└── reference/              # Design reference images
    └── *.png / *.jpg
```

---

## 6. Lessons Learned

1. **CSS can do more than expected** — animations, interactions, even "state" via checkbox hack
2. **Variables change everything** — refactoring colors later would have been painful without CSS custom properties
3. **SVGs > images** — crisp at any size, tiny file weight; custom wave SVGs add brand character
4. **Planning beats patching** — defining color/spacing tokens upfront saves refactoring time
5. **Scoped body classes enable clean theming** — overriding tokens at `body.hobby-X` level keeps per-page CSS minimal and readable
6. **`clamp()` is underrated** — fluid type and spacing without a single media query; fewer breakpoints to maintain

---

## 7. Current Project Status (April 2026)

### Completed
- [x] Home page (`index.html`) — hero, nav, hobby cards, illustration shelf, footer
- [x] Custom 404 page
- [x] Sub-page template system (`sub-template.css`) — hero, intro, carousel, resources, timeline
- [x] Four hobby sub-pages created: Gardening, Hiking, Motorcycling, Travel
- [x] Per-page CSS files with scoped palette overrides
- [x] Per-page hero wave SVG override via `--sub-hero-bg-image` token
- [x] Page-specific hero wave SVGs for Gardening, Hiking, Motorcycling
- [x] CSS carousel (pure CSS, accessibility-aware)
- [x] Responsive layout across all pages
- [x] Embedded video section added to all four hobby sub-pages
- [x] Motorcycling page updated with a live YouTube embed

### In Progress / Remaining
- [ ] Replace carousel placeholder slides with real photographs
- [ ] Fill in sub-page content (intro text, timeline entries, resource links)
- [ ] Replace placeholder video embeds on Gardening, Hiking, and Travel with final clips
- [ ] Travel page hero wave SVG (currently using shared fallback)
- [ ] Final cross-browser / mobile testing

---

## 8. Future Improvements (If Time Permits)

- [ ] Add page-specific content (not just Lorem Ipsum)
- [ ] Implement dark mode via `prefers-color-scheme`
- [ ] Add hover micro-interactions on hobby cards
- [ ] Add full site navigation to the 404 page

---

## 9. Presentation Talking Points

1. "We built this without a single line of JavaScript"
2. "All animations, interactions, and even the mobile menu work via CSS alone"
3. "Custom SVGs keep the site fast — no heavy images to load"
4. "CSS variables mean we can redesign the whole site by changing a handful of lines"
5. "Each hobby page has its own palette and hero wave — all controlled through per-page CSS tokens"
6. "Everything is responsive — try it on your phone"

---

## 10. Commit History Summary

| Commit | Description |
|--------|-------------|
| `6ce0c56` | Initial project process documentation |
| `889fda1` | Website plan updated: Phase 1 complete |
| `d06b24e` | 404 page added |
| `73f826b` | Sub-page template created (Layout 3+5 combined) |
| `b4e3f2b` | Timeline CSS merged into sub-template |
| `bb6d517` | Resources section redesigned with wave overlap |
| `a0ac645` | Major sub-template CSS overhaul |
| `115bed5` | Layout explorations archived to `layout-options/` |
| `30be5b0` | Sub-template CSS cleaned up |
| `9aef1f1` | Carousel placeholder images added |
| `2ef0c73` | CSS comments added, resource spacing refined |
| `445f4e6` | **Four hobby sub-pages created** (Gardening, Hiking, Motorcycling, Travel); home page topics updated |
| `5fb7c17` | **Per-page CSS files added**; `--sub-hero-bg-image` token introduced for per-page hero wave overrides |

---

*Last updated: April 2026*
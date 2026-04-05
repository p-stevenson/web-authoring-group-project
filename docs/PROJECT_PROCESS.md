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
| Minimal static footer | Keeps the layout clean while leaving legal links as simple placeholders for this assignment |

### 2.2 Typography

- **Primary Font:** Slackey (display/headings) — playful, chunky, fits hobby theme
- **Fallback:** Arial (body text) — readability, universal support
- **Motorcycling override:** Oxanium for headings and Barlow Semi Condensed for resource links — gives the reference page a more mechanical feel without changing the whole site

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
- **Hero section with illustration shelf** — visual interest using lightweight SVG artwork instead of large hero photography
- **Mobile-first responsive** — works on phones from the start
- **Homepage-only flex layout** — keeps the homepage footer at the bottom on tall screens without affecting sub-page layout
- **In-page jump target** — the `READ MORE` button links to `#hobbies`, which is also used as the project's clear CSS `id` selector example

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
- **Image carousel** — pure CSS animation (`@keyframes carousel-scroll`), 3 slides + 3 duplicates for seamless loop; `prefers-reduced-motion` respected; current shared sizing uses a responsive width-based carousel frame
- **Resources section** — overlapping wave design using section overlap, shared SVG wave artwork, and pseudo-elements
- **Embedded video section** — shared responsive iframe wrapper between resources and the getting-started timeline
- **Getting Started timeline** — vertical timeline with colour-coded milestone dots
- **Accessibility:** `prefers-reduced-motion` disables carousel animation for motion-sensitive users; video sections include descriptive headings and `iframe` titles

### 3.5 Per-Page Theme System

Each hobby page has its own CSS file that overrides shared design tokens on a scoped body class (e.g. `body.hobby-gardening`):

| Page | Body Class | Key Palette |
|------|-----------|-------------|
| Gardening | `hobby-gardening` | Soft greens `#c6e6b4` |
| Hiking | `hobby-hiking` | Cool blues `#b8d7de` |
| Motorcycling | `hobby-motorcycling` | Muted purples `#e6e2f7` |
| Travel | `hobby-travel` | Light sky blues `#c7e5f5` |

Key overrideable tokens per page:
- `--sub-hero-bg` — hero background colour
- `--sub-hero-bg-image` — hero wave SVG (each page can use a distinct wave asset)
- `--sub-intro-bg`, heading colors, text colors, timeline dot colors, etc.

Motorcycling and Travel are now the two most complete reference pages. Both use final copy, real resource links, live video embeds, and real carousel imagery. Motorcycling still goes further visually by overriding typography, resource-link styling, and carousel presentation more aggressively than the other pages.

### 3.6 Custom 404 Page

- Styled to match site branding
- Used as the placeholder destination for footer legal links in this assignment version

---

## 4. Challenges & Solutions

| Challenge | Solution |
|-----------|----------|
| **No JavaScript allowed** | Leveraged CSS-only solutions: checkbox nav toggle, CSS animations, hover states |
| **Limited assets** | Reused lightweight SVG asset files and shared wave graphics to keep the site flexible without relying on heavy media |
| **Responsive design** | Flexbox + CSS Grid with mobile-first approach; `clamp()` for fluid typography |
| **Cross-page consistency** | Shared `sub-template.css` with CSS custom property tokens ensures uniform layout |
| **Per-page theming** | Scoped body class overrides (e.g. `body.hobby-gardening`) isolate palette changes |
| **Hero wave image per page** | `--sub-hero-bg-image` token in shared template, overridden per page CSS file |
| **Seamless carousel loop** | Six-slide track (3 real + 3 duplicate) with carefully timed `@keyframes` percentages |
| **Resources wave overlap** | Negative `margin-top` plus shared SVG wave backgrounds create the layered transition between sections |

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
├── style.css               # Main / home stylesheet
├── sub-template.css        # Shared sub-page layout & design tokens
├── gardening.css           # Gardening page palette & hero overrides
├── hiking.css              # Hiking page palette & hero overrides
├── motorcycling.css        # Motorcycling page palette & hero overrides
├── travel.css              # Travel page palette & hero overrides
├── fonts/
│   └── Slackey/            # Custom display font
├── images/
│   ├── *.svg               # Shared icons and wave graphics currently used by the live site
│   ├── *.jpg               # Hobby photos, including motorcycling and travel carousel images
│   ├── hero-wavy-svg-*.svg # Shared wave graphics for the sub-page template
│   ├── gardening-sub-hero-wave.svg
│   ├── hiking-sub-hero-wave.svg
│   ├── motorcycling-sub-hero-wave.svg
│   ├── sub-hero-wave.svg
│   ├── motorcycle-gear.jpg
│   ├── motorcycling-roadcraft.jpg
│   ├── motorcycling-training.jpg
│   ├── travel-1.jpg
│   ├── travel-2.jpg
│   └── travel-3.jpg
├── docs/
│   ├── README.md
│   ├── PROJECT_PROCESS.md
│   ├── checklist.md
│   ├── Website Technical Requirements Outline.txt
│   ├── Travel.txt
│   └── website-plan.md
├── archived-templates/     # Archived template references and layout explorations
│   ├── template.html
│   ├── template-skillpath.html
│   └── template-skillpath.css
└── reference/              # Design reference images
    └── *.png / *.jpg
```

The original template examples are now stored in `archived-templates/`, while the live site pages use the shared sub-template system and a cleaner semantic page structure.

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
- [x] Homepage `READ MORE` button links to the `#hobbies` section
- [x] Homepage layout adjusted so the hobby section stretches and keeps the footer at the bottom on tall screens
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
- [x] Motorcycling page filled out with final intro copy, real Irish/UK/European resource links, and complete timeline text
- [x] Motorcycling carousel updated to use real photography and custom page-level font overrides
- [x] Travel page updated with final intro copy, real travel resource links, a live video embed, and real carousel photography
- [x] Hobby sub-pages now use semantic `<main>` wrappers for primary page content
- [x] Technical checklist updated to match the formal outline for the homepage and motorcycling page
- [x] Unused SVG assets removed from the `images/` folder after a reference audit
- [x] The process documentation and technical checklist have been refreshed to match the latest audited project state

### In Progress / Remaining
- [ ] Replace carousel placeholder slides with real photographs on Gardening and Hiking
- [ ] Fill in Gardening and Hiking content (intro text, timeline entries, resource links)
- [ ] Replace the Gardening and Hiking placeholder video embeds with final clips
- [ ] Confirm FTP upload and post-deployment checks on the live or local server
- [ ] Final cross-browser / mobile testing

---

## 8. Future Improvements (If Time Permits)

- [ ] Complete Gardening and Hiking to the same standard as Motorcycling and Travel
- [ ] Implement dark mode via `prefers-color-scheme`
- [ ] Add hover micro-interactions on hobby cards
- [ ] Replace the remaining Gardening and Hiking placeholder content links with real destinations

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
| `115bed5` | Layout explorations archived to `archived-templates/` |
| `30be5b0` | Sub-template CSS cleaned up |
| `9aef1f1` | Carousel placeholder images added |
| `2ef0c73` | CSS comments added, resource spacing refined |
| `445f4e6` | **Four hobby sub-pages created** (Gardening, Hiking, Motorcycling, Travel); home page topics updated |
| `5fb7c17` | **Per-page CSS files added**; `--sub-hero-bg-image` token introduced for per-page hero wave overrides |
| `45b7c50` | Embedded video section added across the hobby pages |
| `89acdfd` | Motorcycling page content, carousel imagery, and page-specific fonts refined |
| `b9b00ab` | Motorcycling resources link font updated |
| `3abf502` | Homepage `#hobbies` id selector and checklist updates |

Recent workspace updates after the commits listed above include the travel page content pass, checklist alignment against the formal technical outline, SVG asset cleanup, and this documentation refresh.

---

*Last updated: April 2026*
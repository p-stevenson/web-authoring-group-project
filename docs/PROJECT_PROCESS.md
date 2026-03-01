# HOBBYCLUB Website Project — Process Documentation

> A 5-page hobby website built as a school project. Presentation notes and design rationale.

---

## 1. Project Overview

- **Project Type:** School assignment (5-page static website)
- **Tech Stack:** HTML5, CSS3 — *No JavaScript allowed*
- **Goal:** Create a welcoming hub for hobbyists to explore different activities
- **Target Audience:** Beginners interested in knitting, models, cinema, and gaming

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

### 3.2 Hero Animation

- Falling icons (yarn, rocket, projector, game controller) using CSS keyframes
- `animation-delay` staggered for natural feel
- Pure CSS — no JS libraries

### 3.3 CSS Architecture

- **Variables:** Centralized color/spacing tokens
- **Root-level definitions:** Easy theming
- **Responsive breakpoints:** `@media (max-width: 768px)`

---

## 4. Challenges & Solutions

| Challenge | Solution |
|-----------|----------|
| **No JavaScript allowed** | Leveraged CSS-only solutions: checkbox nav toggle, CSS animations, hover states |
| **Limited assets** | Created custom inline SVGs (yarn, rocket, husky, etc.) — lightweight, scalable |
| **Responsive design** | Flexbox + CSS Grid with mobile-first approach; clamp() for fluid typography |
| **Cross-page consistency** | Shared CSS file ensures uniform branding across all 5 pages |

---

## 5. File Structure

```
/
├── index.html          # Home page
├── sewing.html         # Knitting page
├── aeromodelling.html # Models page
├── photography.html   # Cinema page
├── gaming.html        # Gaming page
├── style.css          # Main stylesheet
├── fonts/
│   └── Slackey/       # Custom display font
└── images/
    └── *.svg          # Custom SVG icons
```

---

## 6. Lessons Learned

1. **CSS can do more than expected** — animations, interactions, even "state" via checkbox hack
2. **Variables change everything** — refactoring colors later would have been painful without CSS custom properties
3. **SVGs > images** — crisp at any size, tiny file weight
4. **Planning beats patching** — defining color/spacing tokens upfront saves refactoring time

---

## 7. Future Improvements (If Time Permits)

- [ ] Add page-specific content (not just Lorem Ipsum)
- [ ] Implement dark mode via `prefers-color-scheme`
- [ ] Add hover micro-interactions on hobby cards
- [ ] Create a proper 404 page

---

## 8. Presentation Talking Points

1. "We built this without a single line of JavaScript"
2. "All animations, interactions, and even the mobile menu work via CSS alone"
3. "Custom SVGs keep the site fast — no heavy images to load"
4. "CSS variables mean we can redesign the whole site by changing 15 lines of code"
5. "Everything is responsive — try it on your phone"

---

*Last updated: March 2026*
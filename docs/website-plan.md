# 5-Page Hobby Website Project

## Overview
- **Topic:** Hobbies
- **Tech:** HTML + CSS only (no JavaScript)
- **Pages:** 1 homepage + 4 sub-pages (one per hobby category)
- **Branding:** HOBBYCLUB (rebranded from HOBBYHUB)

---

## Page Structure

### Homepage ✅ DONE
- Hero section with headline + CTA buttons + hobby illustration
- "Like What You See?" divider
- 4 category cards (links to sub-pages)
- Sticky navigation with mobile hamburger menu
- Animated falling icons in hero section
- Stats footer

### Sub-Page Template
- Consistent with homepage styling
- Header (same as homepage)
- Hero/image section specific to the hobby
- Content area for text + images
- Footer (same as homepage)

---

## Sub-Page Topics
1. Knitting (was Sewing)
2. Models (was Aeromodelling)
3. Cinema (was Photography)
4. Gaming

---

## Current Status

### Phase 1: Homepage ✅ COMPLETE
- [x] Review existing index.html and style.css
- [x] Update HTML to match template structure
- [x] Update CSS to match template colors/layout
- [x] Add CSS custom properties (variables)
- [x] Implement mobile hamburger menu (CSS-only checkbox hack)
- [x] Add Slackey display font
- [x] Add hero falling icon animation
- [x] Test in browser

### Phase 2: Sub-Page Template
- [ ] Review reference layouts in `reference/` folder
- [ ] Create reusable HTML structure
- [ ] Create sub-page CSS (or extend main CSS)
- [ ] Ensure consistent header/footer
- [ ] Copy template to each hobby page

### Phase 3: Content
- [ ] Populate each sub-page with content
- [ ] Add appropriate images/SVGs

### Phase 4: Final Review
- [ ] Check all links work
- [ ] Verify responsive behavior
- [ ] Validate HTML/CSS
- [ ] Replace 404 placeholder links with actual pages

---

## Technical Highlights

### CSS-Only Solutions (No JavaScript)
- **Mobile navigation:** Checkbox hack (`<input type="checkbox">` + `:checked` selector)
- **Hero animation:** CSS keyframes with staggered delays
- **Hover effects:** `:hover` states on buttons and cards

### CSS Architecture
- Centralized color/spacing tokens via CSS custom properties
- Mobile-first responsive design
- Fluid typography with `clamp()`

### Custom Assets
- Slackey font (display headings)
- Custom inline SVGs (husky logo, hobby icons)
- Custom 404 page with husky and Slackey font

---

## File Structure
```
/
├── index.html          # Homepage ✅
├── 404.html           # Custom 404 page ✅
├── reference/         # Layout reference materials
│   ├── home-page.png
│   ├── 5-layout-options.png
│   └── hobby-page-rough-draft-001.jpg
├── sewing.html        # Knitting page (placeholder → 404)
├── aeromodelling.html # Models page (placeholder → 404)
├── photography.html   # Cinema page (placeholder → 404)
├── gaming.html        # Gaming page (placeholder → 404)
├── style.css          # Main stylesheet
├── fonts/
│   └── Slackey/       # Custom display font
└── images/
    └── *.svg          # Custom SVG icons
```

---

## Sub-Page Design Reference

Wireframe structure (from `hobby-page-rough-draft-001.jpg`):
1. **Hero** — Hobby title + visual
2. **Intro** — Introduction to the hobby + autoscroll image
3. **Resources** — Images + links to external resources
4. **Comparison** — 3 options (costs, difficulty, barrier to entry)

5 layout variants available in `5-layout-options.png`.

---

## Assets
- `images/` folder - place images here
- `fonts/` folder - custom fonts
- `docs/` folder - project documentation

---

## Notes
- Keep it simple: HTML + CSS only
- Use semantic HTML tags
- All animations and interactions work without JavaScript
- Project process documentation: `docs/PROJECT_PROCESS.md`

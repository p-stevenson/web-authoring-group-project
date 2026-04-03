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
- Shared footer
- `READ MORE` button jumps to the hobbies section
- Homepage-only full-height layout keeps the footer at the bottom on tall screens

### Sub-Page Template
- Consistent with homepage styling
- Header (same as homepage)
- Hero/image section specific to the hobby
- Content area for text + images
- Resources section
- Embedded video section
- Getting Started timeline
- Footer (same as homepage)
- Shared `sub-template.css` layout with per-page theme overrides

---

## Sub-Page Topics
1. Gardening
2. Hiking
3. Travel
4. Motorcycling

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
- [x] Add homepage-only full-height layout so the footer sits at the bottom on tall screens
- [x] Use the `#hobbies` id in CSS and link the `READ MORE` button to it
- [x] Test in browser

### Phase 2: Sub-Page Template
- [x] Review reference layouts in `reference/` folder
- [x] Create reusable HTML structure
- [x] Create sub-page CSS (or extend main CSS)
- [x] Ensure consistent header/footer
- [x] Copy template to each hobby page
- [x] Add embedded video section structure to all hobby pages
- [x] Use a shared carousel layout with theme-level page overrides

### Phase 3: Content
- [x] Finalise `motorcycling.html` as the reference example page
- [x] Add real motorcycling carousel images and real regional resource links
- [x] Replace the motorcycling placeholder video with a live YouTube embed
- [ ] Populate Gardening, Hiking, and Travel with final content
- [ ] Add appropriate images to Gardening, Hiking, and Travel
- [ ] Replace placeholder video embeds on Gardening, Hiking, and Travel with final page-specific videos

### Phase 4: Final Review
- [ ] Check all links work
- [ ] Verify responsive behavior
- [ ] Validate HTML/CSS
- [ ] Replace unnecessary placeholder links in content areas where real destinations should exist

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
- Shared homepage CSS plus `sub-template.css` for the hobby pages
- Per-page overrides via `gardening.css`, `hiking.css`, `travel.css`, and `motorcycling.css`

### Custom Assets
- Slackey font (display headings)
- Custom inline SVGs (husky logo, hobby icons)
- Motorcycling page uses real JPG carousel images and page-specific Google Fonts overrides
- Custom 404 page with husky and Slackey font

---

## File Structure
```
/
├── index.html              # Homepage
├── gardening.html          # Gardening sub-page
├── hiking.html             # Hiking sub-page
├── travel.html             # Travel sub-page
├── motorcycling.html       # Motorcycling sub-page
├── 404.html                # Custom 404 page
├── style.css               # Main stylesheet
├── sub-template.css        # Shared hobby-page layout and video styles
├── gardening.css           # Gardening theme overrides
├── hiking.css              # Hiking theme overrides
├── travel.css              # Travel theme overrides
├── motorcycling.css        # Motorcycling theme overrides
├── checklist.md            # Requirement checklist
├── fonts/
│   └── Slackey/            # Custom display font
├── images/
│   └── *.svg / *.jpg       # Shared icons and images
├── docs/
│   ├── PROJECT_PROCESS.md
│   ├── Website Technical Requirements Outline.txt
│   └── website-plan.md
└── reference/              # Layout reference materials
```

---

## Sub-Page Design Reference

Wireframe structure (from `hobby-page-rough-draft-001.jpg`):
1. **Hero** — Hobby title + visual
2. **Intro** — Introduction to the hobby + autoscroll image
3. **Resources** — Images + links to external resources
4. **Video** — Embedded video tutorial or introduction
5. **Comparison / Getting Started** — 3 stages for beginner progression

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
- Footer placeholder links intentionally point to `404.html` for this project
- Use `motorcycling.html` and `motorcycling.css` as the model when finishing the other three hobby pages
- Project process documentation: `docs/PROJECT_PROCESS.md`

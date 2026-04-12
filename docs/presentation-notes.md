# HOBBYCLUB Presentation Notes

## Scope
- Homepage only
- Motorcycling sub-page only

## Style
- Short cue notes
- A few lines at most
- Written like personal presentation reminders, not a script

## 1. Planning and Purpose

### A. Identify Target Market
- Main audience is beginners or casual hobbyists looking for an easy starting point.
- Homepage is broad and welcoming, so it is aimed at people exploring different interests, not experts.
- Motorcycling page is more specific: learners and new riders who want basic guidance, safety info, and trusted resources.

### B. List the Site Objectives
- Main goal is to introduce different hobbies in a simple, friendly way.
- Homepage is there to grab attention, show the hobby choices clearly, and move users into the site.
- Motorcycling page is meant to inform beginners, stress safety, and point them towards proper training and official resources.

### C. Site Map and Navigation Solution
- Site map is simple: Home page links to Gardening, Hiking, Travel, and Motorcycling pages.
- Every page uses the same top navigation, so the user can move between pages from anywhere.
- On mobile, the nav changes to a hamburger menu using a checkbox and CSS, so it still works without JavaScript.
- Homepage also has a READ MORE jump link down to the hobby cards, which helps users move quickly into the main content.
- Any links that do not have content currently go to a basic 404 page.

### D. Sketches and Initial Design Phase
- During the first couple of group meetings we looked for reference images.
- Created some sketches of the layout based on those.
- Decided on navigation choices and the overall look and feel of the site.

### E. Tools Used for Creation of the Site
- Main build tools were HTML5 and CSS3, because the site was made without JavaScript.
- It was developed in VS Code, with Live Server or local preview used for testing pages.
- Git and GitHub were used for version control and keeping track of changes.
- SVG graphics were edited in Affinity Designer, images were sourced from the internet for visual styling, and YouTube was used for the motorcycling video embed.

## 2. User Interface Design

### A. Contrast
- Contrast helps separate the big sections and makes important actions stand out.
- On the homepage, `style.css` uses the orange hero background and white text, then a dark purple button so the `READ MORE` button is easy to notice.
- On the motorcycling page, `motorcycling.css` sets a light background with darker heading and body colours, and the timeline and resource colours highlight important parts without making the page hard to read.

### B. Repetition
- Repetition keeps the site consistent and easier to follow.
- The same nav bar and footer are repeated on every page, and the homepage hobby cards repeat the same card layout for each topic.
- In code, the shared styles in `style.css` and `sub-template.css` handle repeated structure, while `motorcycling.css` only changes the colours and theme for that page.

### C. Alignment
- Alignment helps the pages feel tidy and easier to scan.
- The homepage and motorcycling page both use centred containers, so the main content lines up instead of looking scattered.
- In code, this comes from shared layout classes like `.nav-container`, `.hobby-container`, `.sub-intro-grid`, and `.resource-links-layout`, plus the repeated `max-width: 1000px` in the CSS.

### D. Proximity
- Proximity helps related content feel grouped together, so users can understand sections faster.
- On the homepage, each hobby icon, heading, and short description is kept close together as one card.
- On the motorcycling page, the heading, intro text, video, resources, and timeline items are grouped in their own sections, and the spacing in `sub-template.css` makes those groups clear.

## 3. Development of the Website

### A. Text
- For text design, the main choice was keeping a clear hierarchy between headings and body text.
- The site uses more playful display fonts for titles, then simpler body text underneath so it stays readable.
- Shared styles use `Slackey` for branding and major headings, while body text uses `Arial`.
- On the motorcycling page, the heading font changes in `motorcycling.css` to `Oxanium`, which helps that page feel more mechanical and distinct without changing the whole layout.
- Responsive text sizing is also used with rules like `clamp()`, which helps text scale better across screen sizes.

### B. Images
- Image design was used more for visual identity and layout balance than for filling every space with photos.
- On the homepage, SVG icons and the hero illustration make the page feel playful and give each hobby a clear visual symbol.
- On the motorcycling page, the carousel images add a more realistic feel.
- Technically, those motorcycling slides use `background-image` inside the shared `.image-carousel` layout, which keeps the image area neat and consistent.

### C. Multimedia
- Multimedia was kept simple so it supports the page instead of taking over it.
- The main media choice on the motorcycling page is the embedded YouTube video, which adds motion and extra information without changing the layout too much.
- In code, the `.sub-video-embed` wrapper and `.sub-video-frame` styles keep the video responsive and fit it into the same card layout as the rest of the page.
- The fixed 16:9 video area is useful because it keeps the embed tidy across different screen sizes.

## 4. Correct Employment of HTML and CSS

### A. Correct HTML Page Structure
- Both pages follow the normal HTML structure: `<!DOCTYPE html>`, `<html lang="en">`, `<head>`, and `<body>`.
- Inside that, the layout is organised with semantic sections like `nav`, `header`, `main`, `section`, and `footer`, which makes the page structure clearer.
- Example: the homepage uses `header` for the hero and `main` for the hobby cards, while the motorcycling page keeps its full page content inside one `<main>` wrapper.

### B. Use of Current HTML Syntax
- The pages use modern HTML5 elements instead of older generic layouts, for example `nav`, `main`, `section`, and `footer`.
- They also use current helpful attributes like `lang`, `aria-label`, `title`, `referrerpolicy`, and `allowfullscreen`.
- A good example is the motorcycling `iframe`, which includes a title and modern embed attributes, and the navigation uses `aria-label` to support accessibility.

## 5. Correct Use of CSS

### A. Classes and IDs as Selectors
- Classes are used for reusable styling, for example `.nav-container`, `.hero`, `.hobby-item`, and `.sub-video-card`.
- IDs are used where one specific section needs a unique target, for example `#hobbies` for the homepage jump link and `#motorcycling-resources` for the motorcycling resources section.
- A stronger technical example is `body.hobby-motorcycling`, which scopes theme changes to one page without rewriting the shared layout.

### B. Font and Text Properties
- `style.css` uses `font-family: 'Slackey', 'Arial', sans-serif;` for headings and branding, which gives the site its playful look.
- Body text uses simpler fonts like `Arial` for readability.
- In `motorcycling.css`, the page heading font changes to `Oxanium`, which is a clear example of page-specific text styling.

### C. Background Properties
- Background colour is used all over the site, for example `.hero { background-color: var(--site-accent-color); }` on the homepage.
- Background images are used in the motorcycling carousel with rules like `.carousel-slide-1 { background-image: url('images/motorcycling-training.jpg'); }`.
- The sub-page hero also uses `background-image` through CSS variables for the wave shape behind the title.

### D. Positioning
- Positioning is used in the homepage hero, for example `.main-nav { position: sticky; top: 0; }` keeps the nav visible while scrolling.
- The falling icons use `position: absolute`, while the hero itself is `position: relative`, so those elements stay inside the hero area.
- The sub-page hero wave also uses relative and absolute positioning to layer the background shape properly.

### E. Borders
- Borders are used to separate and frame content, for example the nav has `border-bottom: 2px solid var(--site-accent-color);`.
- The carousel uses `border: 5px solid white;` and rounded corners, which makes it stand out as a contained element.
- The video card also has `border: 1px solid var(--site-border-light-color);` to define the section without making it too heavy.

### F. Padding and Margins
- Padding is used for internal spacing, for example `.btn { padding: 12px 30px; }` and `.sub-video-card { padding: 28px; }`.
- Margins are used to control spacing between elements, like `.hero-text { margin: 0 auto 30px; }` and `.sub-video-card { margin: 40px 0 0 0; }`.
- A simple example is the hobby icons on the homepage, where `margin: 0 auto 20px;` helps space and centre them neatly.
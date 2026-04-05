# HOBBYCLUB

Static five-page hobby website built for a web authoring assignment using HTML5 and CSS3 only.

## Current Status

- The homepage is in place with sticky navigation, hero animation, hobby cards, and a `READ MORE` jump link to the hobby section.
- The homepage now uses a homepage-only full-height layout so the footer sits at the bottom on taller screens without affecting sub-pages.
- All four hobby sub-pages share the same template structure and include a video section.
- `motorcycling.html` and `travel.html` are the most complete pages and currently act as the strongest reference examples.
- The original template references have been archived to `archived-templates/` and are no longer part of the live site structure.
- Hobby pages now use a semantic `<main>` wrapper for page content.
- The homepage hero animation DOM has been simplified to reduce repeated decorative markup.
- Gardening and Hiking still need final copy, real resource links, real carousel images, and final video embeds.
- The homepage and motorcycling page have been checked against the formal technical requirements outline in `docs/checklist.md`.

## Main Files

- `index.html` - homepage
- `gardening.html`, `hiking.html`, `travel.html`, `motorcycling.html` - hobby sub-pages
- `style.css` - shared site styles and homepage layout
- `sub-template.css` - shared hobby-page layout, carousel, resources, video, and timeline styles
- `gardening.css`, `hiking.css`, `travel.css`, `motorcycling.css` - page-specific theme overrides
- `docs/checklist.md` - technical requirements compliance tracking
- `docs/README.md` - maintenance and editing guide
- `docs/PROJECT_PROCESS.md` - design/process notes
- `docs/website-plan.md` - project planning notes

## Edit Zones On Each Hobby Page

These comment markers already show the safe sections to replace on each hobby page:

- `<!-- EDIT ZONE: HERO (title + tagline) -->`
- `<!-- EDIT ZONE: INTRO COPY + CAROUSEL CONTENT -->`
- `<!-- EDIT ZONE: RESOURCES LINKS + CENTER ICON -->`
- `<!-- EDIT ZONE: EMBEDDED VIDEO -->`
- `<!-- EDIT ZONE: STARTER PATHWAY CONTENT -->`

## Shared Files To Edit Carefully

- `style.css` affects the homepage and shared navigation/footer behaviour.
- `sub-template.css` affects every hobby page.
- `index.html` affects the homepage structure and card links.
- `docs/checklist.md` and the other files in `docs/` affect project documentation and status tracking.

## How To Update Existing Text

1. Open the page you want to edit.
2. Find the relevant edit zone comment.
3. Replace the current heading or paragraph text inside that section.
4. Preview the page and check spacing, line length, and mobile layout.

If you want a finished example to copy from, use `motorcycling.html` first. The original template reference has been archived in `archived-templates/template.html`.

`travel.html` is also a good live reference for a completed page using real resources, carousel imagery, and a final video embed.

## How To Create And Link A New Page

1. Copy the structure from `motorcycling.html` or use `archived-templates/template.html` as a reference.
2. Rename the new file and update the `<title>`, body class, hero text, and linked page-specific CSS file.
3. Add a matching card or link from `index.html`.
4. Add the new page to the navigation list on every live page if you want full site navigation to remain consistent.
5. Preview the new page from the homepage and from the nav menu.

## How To Add Or Replace Images

1. Put the new file in `images/`.
2. Use clear lowercase names with hyphens, for example `images/hiking-trail.jpg`.
3. For carousel slides, update the background-image rules in that page's CSS file instead of changing the carousel HTML.
4. Prefer landscape images that still crop well inside the carousel frame.
5. Keep image sizes reasonable before upload so the pages stay quick to load.

The motorcycling carousel in `motorcycling.css` is the current example of swapping placeholder slides for real images.

`travel.css` is the other live example of a page-specific carousel that already uses real photography.

## How To Replace The Embedded Video

1. Stay inside the `<!-- EDIT ZONE: EMBEDDED VIDEO -->` section.
2. Replace the `iframe` `src`, `title`, and supporting text.
3. Keep the existing wrapper classes so the shared responsive styling still works.
4. Preview from a local server when possible because some providers behave badly from `file://` previews.

## How To Re-Upload Updated Files

1. Connect to the course or hosting server with the provided FTP or SFTP details.
2. Upload only the files you changed, keeping the same folder structure.
3. Overwrite the existing copies on the server.
4. Refresh the live site and test the homepage, navigation, resource links, and video sections.
5. Re-check the mobile menu and embedded media after upload.

## Local Preview

Open `index.html` in Live Server or another local server and move through the site from there. This is better than opening files directly because embedded video often behaves differently when a page is loaded from `file://`.

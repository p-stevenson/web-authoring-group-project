# Website Requirements Checklist

Use this file to track compliance with the Web Authoring technical requirements.

Scope checked in this pass: `index.html`, `motorcycling.html`, shared CSS, and the maintenance documentation files. Items that require a live server or manual interaction remain unchecked until they are confirmed after deployment.

Current result: the homepage and motorcycling sub-page satisfy the source-level HTML, CSS, multimedia, and documentation requirements from the technical outline. Deployment and post-upload testing still need manual confirmation.

## 1. HTML Standards and Structure

- [x] `index.html` and `motorcycling.html` include `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>`.
- [x] Both pages use semantic structure with headings, sections, navigation, links, and a `<main>` content region.
- [x] The homepage navigation links to all four hobby sub-pages.
- [x] The motorcycling page navigation links back to the homepage and the other hobby pages.

## 2. CSS Styling and Layout

- [x] CSS is used consistently through `style.css`, `sub-template.css`, and `motorcycling.css`.
- [x] Both class and id selectors are used, including the homepage `#hobbies` target.
- [x] Typography, colors, backgrounds, borders, padding, and margins are implemented in the checked pages.
- [x] Required positioning techniques are present, including `relative`, `absolute`, and `sticky`.

## 3. Multimedia and Content Integration

- [x] The checked pages include multimedia: the homepage uses animation and the motorcycling page uses an embedded video iframe.
- [x] Images on the checked pages include `alt` text, with decorative homepage icons using empty `alt` values where appropriate.
- [x] Motorcycling uses relevant imagery and carousel images sized with `background-size: cover` and `background-position: center`.
- [x] The motorcycling video includes a descriptive heading, supporting copy, and an iframe `title`.

## 4. Deployment and Functionality

- [ ] Confirm the full site has been uploaded to the required web or local server using FTP.
- [ ] Test homepage and motorcycling internal links after deployment.
- [ ] Test the motorcycling external resource links after deployment.
- [ ] Test the mobile navigation menu after deployment.
- [ ] Confirm the homepage animation and motorcycling embedded video behave correctly after deployment.

## 5. Maintenance Requirements

- [x] Documentation explains how to update existing text.
- [x] Documentation explains how to create and link a new webpage.
- [x] Documentation explains how to insert and resize new images.
- [x] Documentation explains how to re-upload updated files to replace the old server version.

## Notes

- [x] This checklist has been de-duplicated so each technical requirement appears once.
- [x] This compliance pass is intentionally limited to the homepage and motorcycling sub-page.
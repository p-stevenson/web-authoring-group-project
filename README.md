# 5-page-hobby-website

## Team Editing Guide

Each team member can edit their own page file:

- `gardening.html`
- `hiking.html`
- `travel.html`
- `motorcycling.html`

### What To Edit On Your Page

These markers in your html files highlight areas you'll want to edit:

- `<!-- EDIT ZONE: HERO (title + tagline) -->`
- `<!-- EDIT ZONE: INTRO COPY + CAROUSEL CONTENT -->`
- `<!-- EDIT ZONE: RESOURCES LINKS + CENTER ICON -->`
- `<!-- EDIT ZONE: EMBEDDED VIDEO -->`
- `<!-- EDIT ZONE: STARTER PATHWAY CONTENT -->`

### Shared Files (Edit Carefully)

- `style.css`: shared styles for all pages
- `sub-template.css`: shared template styles for all hobby pages
- `index.html`: homepage links/cards to each hobby page
- `checklist.md`: tracks remaining requirement work and priorities

Changes to these files affect everyone.

### Your Personal CSS File

Each hobby page now has its own CSS file loaded after `sub-template.css`:

- `gardening.css`
- `hiking.css`
- `travel.css`
- `motorcycling.css`

Edit variables in your own file to change your page only (font families, font sizes, colors, heading styles, and timeline dot colors).

### Image Tips

- Put new images in `images/`
- Use clear names, for example: `images/gardening-tools.jpg`
- Update your page's carousel/image references only on your own page file

### Video Tips

- Each hobby page now includes an embedded video section
- Replace only the `iframe` on your own page when you are ready to use a real video
- Keep the homepage free of embedded video

### Quick Preview

Open `index.html` in Live Server or your browser and click your hobby card or nav-link to your page to test. Check your page's video section as well as the navigation and layout.


# Editing this README

When you're ready to make this README your own, just edit this file and use the handy template below (or feel free to structure it however you want - this is just a starting point!). Thanks to [makeareadme.com](https://www.makeareadme.com/) for this template.

## Suggestions for a good README

Every project is different, so consider which of these sections apply to yours. The sections used in the template are suggestions for most open source projects. Also keep in mind that while a README can be too long and detailed, too long is better than too short. If you think your README is too long, consider utilizing another form of documentation rather than cutting out information.

## Name
Choose a self-explaining name for your project.

## Description
Let people know what your project can do specifically. Provide context and add a link to any reference visitors might be unfamiliar with. A list of Features or a Background subsection can also be added here. If there are alternatives to your project, this is a good place to list differentiating factors.

## Badges
On some READMEs, you may see small images that convey metadata, such as whether or not all the tests are passing for the project. You can use Shields to add some to your README. Many services also have instructions for adding a badge.

## Visuals
Depending on what you are making, it can be a good idea to include screenshots or even a video (you'll frequently see GIFs rather than actual videos). Tools like ttygif can help, but check out Asciinema for a more sophisticated method.

## Installation
Within a particular ecosystem, there may be a common way of installing things, such as using Yarn, NuGet, or Homebrew. However, consider the possibility that whoever is reading your README is a novice and would like more guidance. Listing specific steps helps remove ambiguity and gets people to using your project as quickly as possible. If it only runs in a specific context like a particular programming language version or operating system or has dependencies that have to be installed manually, also add a Requirements subsection.

## Usage
Use examples liberally, and show the expected output if you can. It's helpful to have inline the smallest example of usage that you can demonstrate, while providing links to more sophisticated examples if they are too long to reasonably include in the README.

## Support
Tell people where they can go to for help. It can be any combination of an issue tracker, a chat room, an email address, etc.

## Roadmap
If you have ideas for releases in the future, it is a good idea to list them in the README.

## Contributing
State if you are open to contributions and what your requirements are for accepting them.

For people who want to make changes to your project, it's helpful to have some documentation on how to get started. Perhaps there is a script that they should run or some environment variables that they need to set. Make these steps explicit. These instructions could also be useful to your future self.

You can also document commands to lint the code or run tests. These steps help to ensure high code quality and reduce the likelihood that the changes inadvertently break something. Having instructions for running tests is especially helpful if it requires external setup, such as starting a Selenium server for testing in a browser.

## Authors and acknowledgment
Show your appreciation to those who have contributed to the project.

## License
For open source projects, say how it is licensed.

## Project status
If you have run out of energy or time for your project, put a note at the top of the README saying that development has slowed down or stopped completely. Someone may choose to fork your project or volunteer to step in as a maintainer or owner, allowing your project to keep going. You can also make an explicit request for maintainers.

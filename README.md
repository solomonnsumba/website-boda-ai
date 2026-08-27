# Boda AI Factory Website

## Overview

Static HTML website for Boda AI Factory, an artificial intelligence and data science organization based in Kampala, Uganda. The site presents the organization's localized research, applied AI work, team, and contact pathways without inventing research metrics, partners, or testimonials. All content is sourced from the organization's own materials or the team's own personal/professional sites.

## Project Structure

- `boda-ai-factory.webfiles/index.html` &mdash; homepage.
- `boda-ai-factory.webfiles/boda-ai-about-us.html` &mdash; mission, vision, and who the organization works with.
- `boda-ai-factory.webfiles/boda-ai-team.html` &mdash; team profiles.
- `boda-ai-factory.webfiles/contact-us.html` &mdash; contact details (email, office address) and how to get in touch.
- `boda-ai-factory.webfiles/our-ai-solutions-*.html` &mdash; the six applied-AI focus areas (agriculture, speech & language, healthcare, infrastructure, finance, business operations), with their original URLs preserved.
- `boda-ai-factory.webfiles/css/site.css` &mdash; the full design system (color/type tokens, layout, and all page components) and responsive rules.
- `boda-ai-factory.webfiles/js/site.js` &mdash; the accessible mobile navigation toggle, shared by every page.
- `boda-ai-factory.webfiles/images/` &mdash; logo, sector illustrations, and team headshots.
- `boda-ai-factory.webfiles/robots.txt` and `sitemap.xml` &mdash; crawler guidance, kept in sync with the page list.
- `boda-ai-factory.webfiles v1/` and the ZIP archives at the repo root are historical Webflow exports, kept on disk for reference but excluded from git via `.gitignore`.

Every page uses the same static HTML/CSS/vanilla-JS stack (no build step, no framework, no third-party JS dependency) so any page can be edited directly and deployed as-is.

## Local Development

From the repository root, serve the static folder with any static server, for example:

```sh
python3 -m http.server 8000 --directory boda-ai-factory.webfiles
```

Open `http://localhost:8000/index.html`.

## Deployment

The project is a static site and can be deployed to GitHub Pages, Netlify, Cloudflare Pages, or any web host by publishing the contents of `boda-ai-factory.webfiles/`. The production domain documented by the current site is `https://www.boda-ai-factory.com/`.

## Updating Content

- Update homepage copy in `index.html`.
- Update organization, mission, and vision content in `boda-ai-about-us.html`.
- Update team profiles and headshots in `boda-ai-team.html` and `images/`.
- Update solution pages in the corresponding `our-ai-solutions-*.html` files.
- Update contact details (email, address) in `contact-us.html` &mdash; the same email/address also appear in the footer of every page and should be kept in sync.
- When adding or removing a page, update the shared nav/footer markup in every `.html` file, and add or remove the corresponding `<url>` entry in `sitemap.xml`.

## Known gaps / content still needed

- No dedicated Open Graph/social preview image (1200&times;630 PNG) exists yet; pages currently omit `og:image` rather than pointing at an SVG that may not render in social previews.
- The contact page uses `mailto:` links rather than a hosted form, since the original Webflow contact form had no working backend once exported as static HTML. Wire up a form service (e.g. Formspree, Netlify Forms) if a native in-page form is wanted.
- The production domain's TLS certificate did not match its hostname at last check (it resolved to a Google Cloud Storage certificate), which will show a browser warning to visitors; this is a hosting/DNS configuration issue outside this repository.

## Domain

Production: `https://www.boda-ai-factory.com/`

# Portfolio Site — Requirements & Preferences

## About Me
- Name: Kanishk Morey
- Role / title: Back End Software Engineer (~14 months experience)
- One-line bio / tagline: Not decided yet — suggest a few options based on role/title
- Location: Indore, India
- Links: GitHub / LinkedIn / email — placeholders for now, will fill in later

## Site Purpose
This is my personal "digital home." It should include:
- Resume/CV page with a downloadable PDF link
- Project showcase (case studies of my work)
- Blog/articles section (technical writing)
- Tool reviews section (my opinions on dev tools, libraries, services)
- Should be easy to extend with new sections later

## Domain & Hosting
- Hosting: GitHub Pages, using `username.github.io` for now
- Future: will move to a custom domain eventually — keep this in mind for config (don't hardcode the github.io URL in places that'd be painful to change later)

## Design Preferences
- Vibe: Minimal/clean, dark-mode-first
- Starting point: Not sure — recommend a good minimal Jekyll theme (or a very lightweight custom build), whichever is easier to maintain long-term
- Font: recommend something clean and readable, dev-portfolio-appropriate
- Primary/brand color: recommend something that works well in dark mode

## Content Structure
- Blog categories/tags: not decided yet — set up the capability, don't force a taxonomy yet
- Tool reviews: no rating system/stars — plain written reviews with pros/cons is fine if needed
- Projects: individual full pages per project (not just cards/list)
- Starting with 0 projects and 0 posts — need placeholder/sample content to learn the format

## Technical Preferences
- I don't know Liquid yet — keep templates readable and add comments explaining what's happening, since I'll be learning from this codebase
- Contact: just an email link, no contact form
- Site search: not needed yet (revisit once there are 15-20+ posts)
- Comments: none for now
- Analytics: add a lightweight privacy-friendly option (Plausible or GoatCounter) — pick one and wire it in

## What I need built
1. Recommended folder/file structure for this Jekyll site
2. `_config.yml` set up with my details above
3. Layouts for: home, resume, project showcase (individual pages), blog post, tool review
4. Minimal dark-mode-first CSS/theme matching the design preferences above
5. GitHub Pages deployment set up (GitHub Actions workflow if needed for any plugins outside the GitHub Pages-safe list)
6. 2-3 sample content files (one blog post, one project page, one tool review) so I can learn the format and structure going forward
7. Brief comments/explanations in Liquid templates since I'm new to Liquid
# How to Use This Site

A working reference for adding content and making changes yourself, without
needing to touch the templates. Keep this file — it's not published as part
of the site (Jekyll only builds `.md` files that live in specific folders
like `_posts/`, or that you explicitly turn into pages; a loose file like
this at the root with no front matter is just ignored).

Every content file starts with a block between two `---` lines called
**front matter**. It's plain YAML (key: value pairs), and it's how you tell
Jekyll which template to use and pass it data. Everything *below* the second
`---` is the actual content, written in Markdown.

---

## Adding a blog post

1. Create a new file in `_posts/` named exactly:
   `YYYY-MM-DD-a-short-title.markdown`
   The date in the filename matters — Jekyll uses it to sort posts and to
   build the URL. The title part just becomes part of the URL slug.

2. Front matter to include:

   ```yaml
   ---
   layout: post          # tells Jekyll to use _layouts/post.html
   title: "Your Title Here"
   date: 2026-08-20 10:00:00 +0530   # publish date/time + timezone offset
   tags: [backend, go]   # optional, plain list — no fixed taxonomy yet
   ---
   ```

   - `layout` — always `post` for blog posts.
   - `title` — shown as the page's `<h1>` and in the `/blog/` listing.
   - `date` — controls sort order and the URL. Must match (or come after)
     the date in the filename.
   - `tags` — optional. Shown on the post itself, but there's no
     tag-browsing page yet (deliberately — not worth building until there
     are enough posts to need it).

3. Write the post body in Markdown below the front matter.
4. It automatically shows up on `/blog/` — that page loops over every file
   in `_posts/`, you don't add it anywhere by hand.

---

## Adding a project

1. Create a new file in `_projects/`, e.g. `_projects/my-cool-api.md`.
   The filename becomes the URL: `/projects/my-cool-api/`.

2. Front matter:

   ```yaml
   ---
   layout: project
   title: "My Cool API"
   summary: "One-line description shown in the /projects/ list and page header."
   stack: [Go, PostgreSQL, Docker]   # optional
   repo_url: "https://github.com/you/my-cool-api"   # optional
   demo_url: "https://example.com"                  # optional
   date: 2026-08-20
   ---
   ```

   - `layout` — always `project`.
   - `title` / `summary` — title and one-liner.
   - `stack` — optional list of technologies, shown as small tags.
   - `repo_url` / `demo_url` — optional links shown under the title. Leave
     either one out entirely and it just won't render (no blank link).
   - `date` — not shown anywhere yet, but harmless to include for your own
     record-keeping / future sorting.

3. Write the case study in Markdown below — the sample project
   (`_projects/sample-project.md`) shows a Problem / What I built / Result
   structure, but that's just a suggestion, not enforced by the template.

4. Shows up automatically on `/projects/`.

---

## Adding a tool review

1. Create a new file in `_reviews/`, e.g. `_reviews/postgresql.md`.
   URL becomes `/reviews/postgresql/`.

2. Front matter:

   ```yaml
   ---
   layout: review
   title: "Tool Review: PostgreSQL"
   verdict: "One-line takeaway shown right under the title."
   pros:
     - "Point one"
     - "Point two"
   cons:
     - "Point one"
     - "Point two"
   date: 2026-08-20
   ---
   ```

   - `verdict` — optional one-liner, styled distinctly at the top.
   - `pros` / `cons` — optional lists, rendered as two columns at the
     bottom of the page. No star ratings, by design — just written
     opinions. Leave either list out if you don't need it.

3. Write your actual review as Markdown in the body.
4. Shows up automatically on `/reviews/`.

---

## Updating your resume

Unlike the other content types, the resume (`resume.md`) is entirely
**data-driven** — you don't write Markdown body content for it, you fill in
YAML fields and the layout (`_layouts/resume.html`) builds the HTML from
them:

```yaml
---
layout: resume
title: Resume
permalink: /resume/
resume_pdf: /assets/resume.pdf   # path to your actual PDF — see note below
role: "Back End Software Engineer"
summary: "A sentence or two about you."
experience:
  - company: "Company Name"
    title: "Your Title"
    period: "Month 20XX – Present"
    points:
      - "A responsibility or system you own."
      - "A concrete outcome you drove."
  # add more entries here for more jobs
skills:
  - "Skill one"
  - "Skill two"
education:
  - school: "Your School"
    degree: "Degree, Field"
    period: "20XX – 20XX"
---
```

Add as many `experience`/`education` entries as you need — each one just
needs those same fields, indented the same way as the example.

**Important:** the "Download PDF" button links to `resume_pdf` (currently
`/assets/resume.pdf`), but that file doesn't exist — nothing generates it
automatically. Export your resume as a PDF yourself and drop it at
`assets/resume.pdf` (create the `assets/` folder if it's not there) for the
button to actually work.

---

## Changing site-wide details

Open `_config.yml` at the project root. Things you'll likely want to update:

- `email`, `github_username`, `linkedin_username` — currently placeholders.
- `tagline` — the line under your name on the home page.
- `goatcounter_code` — your real GoatCounter site code, once you sign up at
  goatcounter.com, to turn on analytics.
- `url` — only change this if you move to a custom domain. Leave `baseurl`
  empty as long as this stays a `username.github.io` root site.

**Note:** `_config.yml` is only read when Jekyll *starts up* — if you're
running `bundle exec jekyll serve` locally, restart it after editing this
file; it won't hot-reload like content changes do.

---

## Changing the look (colors, fonts, spacing)

Everything visual lives in one file: `assets/css/style.css`.

- Colors are defined once at the top as CSS variables (`--bg`, `--text`,
  `--accent`, etc.) inside `:root` — change a value there and it updates
  everywhere that color is used.
- There's a separate block for light mode (`@media (prefers-color-scheme:
  light)`) with its own color values, since the site is dark-by-default but
  auto-switches for visitors whose OS is set to light.
- Fonts are system font stacks (`--font-body`, `--font-mono`) — no
  external font files to manage.

No Jekyll rebuild logic to worry about here beyond the normal one — this
file is plain CSS, copied as-is.

---

## Adding a whole new section (e.g. "Talks", "Now")

This is the one case that needs a bit more than a content file:

1. Decide if it's a *collection* (many individual pages, like projects) or
   a *single page* (like the resume).
2. For a collection: add a new entry under `collections:` in `_config.yml`
   (copy the `projects:`/`reviews:` pattern), then create a matching
   `_layouts/<name>.html` (copy `_layouts/project.html` as a starting
   point) and a `<name>/_<something>` folder for the content files.
3. For a single page: just add a new `.md` file at the root with its own
   `layout:`/`permalink:`, and optionally a link in `_includes/header.html`.

This is the kind of change worth asking for help with rather than guessing
at — the pattern is consistent with what's already here, but it touches
more than one file at once.

---

## Checking your changes before publishing

If you have Ruby/Bundler set up locally:

```
bundle exec jekyll serve
```

Then open `http://localhost:4000` — it rebuilds automatically as you edit
files (except `_config.yml`, which needs a restart). If you don't have a
local Ruby setup, just push to GitHub — the Actions workflow
(`.github/workflows/pages.yml`) builds and deploys on every push to `main`.

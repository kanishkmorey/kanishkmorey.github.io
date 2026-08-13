---
# `_projects/` is a Jekyll "collection" (defined in _config.yml). Each file
# in here becomes its own full page at /projects/<filename>/, using the
# `project` layout (_layouts/project.html) — not just a card in a list.
layout: project
title: "Sample Project"
summary: "One-line summary — shown in the /projects/ list and at the top of this page."
stack: [Go, PostgreSQL, Docker]
repo_url: "https://github.com/kanishkmorey/sample-project"
date: 2026-08-13
---

This is a sample project page — replace it with a real case study once you
have one. `stack`, `repo_url`, and `demo_url` above are all optional; leave
any of them out and that part of the header just won't render (see the
conditional checks in _layouts/project.html).

## Problem

What was broken, slow, or missing before this project existed.

## What I built

The approach, the key decisions, and anything that was genuinely hard or
interesting about building it.

## Result

What changed because of it. Use real numbers if you have them; otherwise
just describe the outcome plainly.

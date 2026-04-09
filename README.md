# Our Last Walk — Website

Landing page and dev blog for the *Our Last Walk* game by Lucky 7.

## Run locally

```sh
npm install
npm run dev      # http://localhost:4321
npm run build    # build to ./dist/
```

## TODO

Search for `TODO` in the codebase to find things that still need to be filled in (eg. Contact info!)

Current known TODOs:
- `src/pages/about.astro` — add avatar photos for each team member
- `src/components/StorySection.astro` — replace placeholder silhouette art with real art

## Adding a new blog post

1. Create a new folder under `src/content/blog/`. Use the format `YYYYMMDD-title` (e.g. `20260501-sprint-4`).
2. Inside the folder, create `index.md` with this frontmatter:

```markdown
---
title: "Your Post Title"
description: "Short description shown on the blog listing."
pubDate: 2026-05-01
author: "Lucky 7"
tags: ["sprint", "unity"]
---

Your content here.
```

3. Place any images in the same folder and reference them in the markdown as `![alt text](./image.png)`.

The new post will appear automatically at `/blog/YYYYMMDD-title`.

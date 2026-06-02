# mumenmusa.github.io

Personal blog of Mumen Musa. Built with [AstroPaper](https://github.com/satnaing/astro-paper).

## Local dev

```bash
pnpm install
pnpm dev
```

Site runs at `http://localhost:4321`.

## Writing a post

Drop a markdown file in `src/content/posts/`. Frontmatter shape:

```yaml
---
author: Mumen Musa
pubDatetime: 2026-06-02T13:00:00Z
title: "Post title"
slug: post-slug
featured: false
draft: false
tags: [tag1, tag2]
description: "One-line summary for SEO + index."
---
```

Push to `main` → GitHub Actions builds and deploys to Pages.

## Stack

- [Astro](https://astro.build) 6
- [AstroPaper](https://github.com/satnaing/astro-paper) theme
- [Tailwind CSS](https://tailwindcss.com) 4
- [PageFind](https://pagefind.app) static search
- Deployed via GitHub Actions to GitHub Pages

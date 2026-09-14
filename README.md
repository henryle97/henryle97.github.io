# henryle97.github.io

Personal site for **Le Van Hoang (Henry)** — Senior AI Engineer, Hanoi, Vietnam.

Built with [Jekyll](https://jekyllrb.com/) and deployed by GitHub Pages'
default build. No Node, no bundler pipeline, no external CSS or JS frameworks.

## Editing content

Almost nothing lives in the templates. To update the site, edit the YAML in
`_data/`:

| File | Drives |
| --- | --- |
| `_data/profile.yml` | Name, role, tagline, links, headline metrics |
| `_data/experience.yml` | The homepage timeline |
| `_data/projects.yml` | The `/projects/` grid |
| `_data/skills.yml` | The capability matrix on `/about/` |

Longer prose lives in `about.md`. Navigation and site metadata are in
`_config.yml`.

To swap the hero monogram for a photo, drop a square image at
`assets/img/profile.jpg` — the hero picks it up automatically and falls back to
the monogram when it isn't there.

## Blog posts

Posts live in `_posts/` as `YYYY-MM-DD-slug.html` (or `.md`) and are listed by
`blog.md`. Front matter:

```yaml
---
title: Running DeepSeek-V4-Flash across four free GPUs
subtitle: One or two lines — used as the card summary and meta description.
dateline: "Optional kicker under the date on the post page"
tags: [inference, gpu]

thumbnail: /assets/img/blog/deepseek-v4-flash.png   # optional
thumbnail-alt: "What the image shows"               # optional, defaults to title
thumbnail-caption: "Credit / context"               # optional, post page only
thumbnail-hero: false                               # optional, card only
---
```

`thumbnail` is optional everywhere. With it, the blog index shows a 16:9 card
image, the post page opens with a hero figure, and the image becomes the
Open Graph / Twitter card (`share-img` still wins if set). Without it, every
one of those falls back to the previous text-only behaviour.

Set `thumbnail-hero: false` to use the image on the index card but not at the
top of the post.

Keep images in `assets/img/blog/` at **16:9, around 1500px wide** — the index
card and the post hero both use that crop, so one export covers all three
placements and nothing reflows as the image loads. Social platforms nominally
prefer 1.91:1, but they accept 16:9 with only slight edge cropping, and 16:9
is the safer choice for a title card with text near the edges.

An image with a different ratio is centre-cropped to fit. If a post needs a
diagram shown whole, put it in the body as a `<figure>` rather than the hero.

Export as JPEG (~q78) and keep it under about 400 KB; the source PNGs off an
image generator are typically 2 MB and don't belong in the repo at that size.

Social platforms reject SVG, so a post with an SVG thumbnail should also set an
explicit PNG/JPG `share-img`.

## Running locally

```bash
bundle install
bundle exec jekyll serve
# http://localhost:4000
```

## Structure

```
_data/                 all editable content
_includes/sections/    hero, metrics, experience, projects, skills
_includes/             head, nav, footer, icons, analytics
_layouts/              base → home / page / default
assets/css/main.css    design tokens + every component style
assets/js/main.js      mobile nav, nav scroll state, scroll reveal
```

## Credits

Originally forked from [Beautiful Jekyll](https://beautifuljekyll.com) by Dean
Attali (MIT). All layouts, includes, and styles have since been rewritten; the
MIT `LICENSE` is retained for that lineage.

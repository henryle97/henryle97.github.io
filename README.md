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

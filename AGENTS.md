# AGENTS.md

Jekyll 4 static site for Friends of Rockville Music (FORM). No custom plugins; GitHub Pages compatible.

## Commands

- Install deps: `bundle install`
- Local dev: `bundle exec jekyll serve` (http://127.0.0.1:4000)
- Build: `bundle exec jekyll build` -> `_site/`
- No test suite. Verification is a clean build plus checking affected output in `_site/`.

## Structure

- Root `*.md` pages: front matter `layout`, `title`, `permalink` (trailing slash, e.g. `/about-us/`).
- `_data/*.yml` holds rotating content; rendered by `_includes/*.html`:
  - `navigation.yml` -> header nav
  - `support_actions.yml` -> home "Support Us!" actions
  - `announcements.yml` -> home news feed
  - `sponsor_tiers.yml` -> sponsorship tiers
  - `meetings.yml`, `groups.yml`, `events/*.yml` -> News and Events calendar
- `_layouts/` (`default`, `home`, `page`); the home hero copy lives in `_includes/home-hero.html` and the sticky "On this page" side rail shared by the home page and interior pages lives in `_includes/rail.html`; single stylesheet `assets/css/style.css`; images in `assets/images/`.
- Maintainer references: `README.md`, `GLOSSARY.md`.

## Conventions

- Keep `_config.yml` plugins to the GitHub Pages-safe subset; do not add custom plugins.
- Terminology must follow `GLOSSARY.md` (FORM; Music Department; Marching Band; Spirit Store; Corporate Sponsorship tiers $1,200/$700/$350; Flocking; Cluster Concert; Instrument Truck).
- Content is a faithful port of the original site, not a pixel clone: preserve copy, headings, tiers, and outbound links; own the layout/markup.
- `_config.yml` `url`/`baseurl` select deployment mode; leave blank until hosting is known.
- `_config.yml` excludes `Gemfile`, `Gemfile.lock`, `README.md`, `GLOSSARY.md`, `AGENTS.md`, `vendor/` from the published site.

## Gotchas

- Data paths (`image`, `link_url`) are absolute site paths; templates apply `relative_url`.
- Markdown pages embed internal links/images as hard-coded absolute paths that are not `relative_url`-filtered; they only work at site root. A project site with `baseurl` requires conversion.
- Broken Liquid or invalid YAML in `_data/` fails the build; rebuild after every edit.
- `_includes/rail.html` builds the "On this page" list by parsing the rendered page HTML (`content`), so a heading change updates the rail automatically - but section headings must be h2 (or h3 on pages with no h2), and page-scoped selectors reach them through `.page-body` / `.home-body`, not `.page` / `.home` directly.

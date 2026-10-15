# Friends of Rockville Music — Jekyll site

A Jekyll version of <https://www.friendsofrockvillemusic.org>, keeping the
original page content, links and images but rendering them in a clean,
responsive, hand-built layout.

## Requirements

- Ruby 3.x
- Bundler 4+ (the committed `Gemfile.lock` records the Bundler it was built with)

## Local development

```bash
bundle install
bundle exec jekyll serve
```

Then open <http://127.0.0.1:4000>.

To produce the static site in `_site/`:

```bash
bundle exec jekyll build
```

## Editing content

Most content lives in ordinary Markdown pages at the repository root
(`about-us.md`, `contact-us.md`, `marching-band.md`, `news-and-events.md`,
`spirit-store.md`, `corporate-sponsorship.md`, `index.md`).

The rotating pieces of the site live in `_data/` so they can be edited without
touching HTML:

| File | Controls |
| --- | --- |
| `_data/navigation.yml` | The top navigation bar |
| `_data/support_actions.yml` | The home page "Support Us!" actions |
| `_data/announcements.yml` | The home page news feed |
| `_data/sponsor_tiers.yml` | The Platinum / Gold / Silver sponsorship tiers |
| `_data/meetings.yml` | FORM meeting heading/detail on the News and Events page |
| `_data/groups.yml` | Event group metadata (titles, intros/outros) on the News and Events page |
| `_data/events/*.yml` | Dated items for each event group on the News and Events page |

The home page hero is the one exception: its kicker, headline, lede and buttons
live in `_includes/home-hero.html` because they sit inside a full-bleed band that
Markdown cannot express.

## Deploying

The site is GitHub Pages compatible (it uses no custom plugins).

- **User / organisation or custom domain:** set `url` in `_config.yml` and leave
  `baseurl` empty.
- **GitHub Pages project site** (`https://<user>.github.io/<repo>`): set `url` to
  `https://<user>.github.io` and `baseurl` to `/<repo>`.

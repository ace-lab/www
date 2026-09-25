# ACE Lab website

Source for the website of the **Algorithms & Computing for Education (ACE) Lab** at UC Berkeley.
It replaces the old WordPress site at <https://acelab.berkeley.edu>.

It's a Jekyll site built on a fork of the [umich-labs](https://github.com/wilsonte-umich/umich-labs) theme,
rebranded with UC Berkeley colors, and deployed with GitHub Pages.

## Where things live

| What | Where |
|---|---|
| Top menu (Active Projects, People, Resources) | `_data/base/navigation.yml` |
| Home page text | `pages/home.md` |
| **Projects**, one Markdown file each | `content/_projects/*.md` |
| **Resources**, one Markdown file each | `content/_resources/*.md` |
| Resource list (section + order on the Resources page) | `_data/resources.yml` |
| People | `pages/people.md` for now; move people into `_data/people.yml` to get cards |
| Images, videos, PDFs from the old site | `assets/uploads/` |
| Paper PDFs | `assets/papers/` |
| Footer | `_data/base/footer.yml` |
| Site title, logo, colors | `_config.yml` and `_sass/_variables.scss` |

### Adding a project

Create `content/_projects/<slug>.md` (the page will be at `/projects/<slug>/`):

```yaml
---
title: My Project
subtitle: One-line summary shown in the banner
description: A couple of sentences shown on the project card.
order: 4           # position on the Projects page
active: true       # true = "Active Projects" (and home page); false = "Other Projects"
card_image: null   # or a path like /assets/uploads/my-figure.png
card_title: null   # shorter title for the card banner, if the title is long
categories:
  - Programming Education
---

Page content in Markdown...
```

### Adding a resource

1. Create `content/_resources/<id>.md` with `title:` and `subtitle:` front matter.
2. Add an entry with the same `id` to `_data/resources.yml`. Its `type` sets the section it appears under on the Resources page.
3. Optionally add it to the Resources dropdown in `_data/base/navigation.yml`.

### Links inside pages

Write internal links as `{{ site.baseurl }}/projects/cbt/` so they still work if the site is served from a sub-path.

### Old URLs

Pages migrated from WordPress have `redirect_from:` front matter (via `jekyll-redirect-from`),
so old links like `/beyond-the-lab/funding/` still work if the old domain is pointed at this site.

## Running locally

Requires Ruby 3.x (see `.ruby-version`).

```sh
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve     # http://localhost:4000
```

## Deploying (GitHub Pages)

1. Push this repo to the `ace-lab` GitHub org. If the repo is named `ace-lab.github.io`, the site is
   served at <https://ace-lab.github.io/> and no `baseurl` is needed. For any other repo name, set
   `baseurl: "/<repo-name>"` in `_config.yml`.
2. In the repo, go to **Settings → Pages → Build and deployment**, choose **Deploy from a branch**, then pick `main` and `/ (root)`.
3. (Later) To serve it at `acelab.berkeley.edu`, add a `CNAME` file and have campus IT point DNS at GitHub Pages.

The only plugins used are ones GitHub Pages supports, so no custom build workflow is needed.

## Credits

Theme: [umich-labs](https://github.com/wilsonte-umich/umich-labs) (MIT), a fork of
[petridish](https://github.com/peterdesmet/petridish). See `LICENSE` and `LICENSE-petridish`.

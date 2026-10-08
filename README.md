# Chulapa 101

A ready-to-use personal blog with a small content structure inspired by [Minimal Mistakes' GitHub Pages starter](https://github.com/mmistakes/mm-github-pages-starter), adapted to [Chulapa](https://github.com/dieghernan/chulapa). It includes three sample posts, a paginated home page, About, year, category and tag archives, Fuse.js search and RSS. It uses the predefined Gitdev skin without color or CSS overrides.

[See the live site](https://dieghernan.github.io/chulapa-101/).

## Create and publish your site

You can do everything on GitHub. No installation or terminal is needed.

1. Click [Use this template](https://github.com/dieghernan/chulapa-101/generate) and create your repository.
2. In your new repository, open **Settings > Pages** and choose **GitHub Actions** as the source.
3. Open `_config.yml`, click the pencil icon and change the title, description and author name. Set `repository` to `YOUR-USERNAME/YOUR-REPOSITORY` and `url` to `https://YOUR-USERNAME.github.io`. Commit the changes to your default branch.

The **Actions** tab shows the deployment progress. When it finishes, **Settings > Pages** shows your website address. Future changes to `main` or `master` publish automatically. You do not need to configure a token. The workflow sets your site's base path automatically.

## Add your content

| What to change | File or folder |
| --- | --- |
| Site title, description and your name | `_config.yml` |
| Home page heading and introduction | `index.html` |
| About page | `_pages/about.md` |
| Archive pages | `_pages/archive.md`, `_pages/categories.md` and `_pages/tags.md` |
| Blog posts | `_posts/` |
| Images | `assets/img/` |

For a new post, create a file such as `_posts/2026-01-01-hello.md`. Start it with:

```markdown
---
title: Hello
tags: [journal]
---

This is my first post.
```

Use the publication date in the filename. Posts with a future date remain unpublished until a build runs on or after that date. You can edit or delete the sample posts through GitHub's file editor.

Replace the sample text and the `hello@example.com` contact address on About before publishing your own content. The sample photograph is credited to Quique Olivar on Unsplash in its post. Replace it with your own image and update the alternative text to describe it.

The archive pages use Chulapa's `archive`, `cloudcategory` and `cloudtag` layouts, limited to posts. Post categories and tags link to the corresponding topic. Fuse.js indexes posts and About; archive pages, the home page, search and 404 are excluded to avoid duplicate search results. New pages under `_pages/` are searchable unless their front matter sets `include_on_search: false`.

The home page shows five posts per page. Change `paginate` in `_config.yml` to adjust this; keep the home page named `index.html` because Jekyll's pagination plugin requires it. Navigation, author details and footer links are configured in `_config.yml`. Chulapa supplies the layouts, includes and styles, so the starter does not need local theme overrides.

```text
_config.yml          Site settings and navigation
_pages/              About, archives, search and 404
_posts/              Your blog posts
assets/img/          Your images
index.html           Paginated home page
Gemfile              Local build dependencies
.github/workflows/   Existing deployment workflows
```

## Choose a skin

Change `skin: gitdev` under `chulapa-skin` in `_config.yml` to another [predefined skin](https://dieghernan.github.io/chulapa/skins). No CSS changes are required.

See the [Chulapa documentation](https://dieghernan.github.io/chulapa/docs) for additional features and settings. The starter remains one ordinary Jekyll site with content at the repository root.

## Optional local preview

Local preview is for people who want to edit on their computer. Install Ruby and Bundler, then run these commands from the repository folder:

```sh
bundle install
bundle exec jekyll serve --host localhost --baseurl ""
```

Open <http://localhost:4000>. Restart Jekyll after changing `_config.yml`. The deployment workflow uses Ruby 3.4 and the template uses Jekyll 4.4.

## How deployment works

The original Pages workflow builds the blog with Jekyll and supplies its base path automatically. You can also run it manually from the Actions tab. The existing branch publishing, profiling and cache cleanup workflows are preserved. There are no profile selectors or additional build scripts.

The remote theme follows Chulapa's default branch. A fresh build can pick up theme updates. Your content and configuration remain in this repository. To pin a release, append `@TAG` to `remote_theme` in `_config.yml`.

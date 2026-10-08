# <span class="chulapa">Chulapa</span> 101

A ready-to-use personal blog with a small content structure inspired by [Minimal Mistakes' GitHub Pages starter](https://github.com/mmistakes/mm-github-pages-starter), adapted to [<span class="chulapa">Chulapa</span>](https://github.com/dieghernan/chulapa). It includes three sample posts, a paginated home page, About, year, category and tag archives, Fuse.js search and RSS. It uses the predefined Gitdev skin without color or CSS overrides.

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

The home page shows five posts per page. Change `paginate` in `_config.yml` to adjust this; keep the home page named `index.html` because Jekyll's pagination plugin requires it. Navigation, author details and footer links are configured in `_config.yml`. <span class="chulapa">Chulapa</span> supplies the layouts, includes and styles. Optional customization files are included, ready to edit when you need them.

```text
_config.yml          Site settings and navigation
_pages/              About, archives, search and 404
_posts/              Your blog posts
_includes/custom/    Optional HTML and script hooks
assets/img/          Your images
assets/css/          Optional custom.scss stylesheet
index.html           Paginated home page
Gemfile              Local build dependencies
.github/workflows/   Existing deployment workflows
```

## Choose a skin

Change `skin: gitdev` under `chulapa-skin` in `_config.yml` to another [predefined skin](https://dieghernan.github.io/chulapa/skins). No CSS changes are required.

The configuration follows <span class="chulapa">Chulapa</span>'s full sample, with the same sections, option names and explanatory comments. Unused options stay empty so you can find them when needed. Start with your site details in section A; the blog, navigation, Fuse.js search, pagination and skin are already configured. Do not replace the file with the theme's sample: that sample also configures <span class="chulapa">Chulapa</span>'s own documentation collections.

## Optional customization files

These files follow the extension points also used by [chulapa-gem](https://github.com/dieghernan/chulapa-gem). They contain comments only, so they do not change the selected skin or load extra scripts.

| File | Use |
| --- | --- |
| `_includes/custom/custom_head_before_css.html` | HTML in the head before the theme's stylesheets |
| `_includes/custom/custom_head.html` | Additional head tags, such as favicons |
| `_includes/custom/custom_bottomscripts.html` | Scripts near the end of the page |
| `_includes/custom/giscus.html` | Your Giscus embed script, when comments are enabled |
| `assets/css/custom.scss` | Your CSS or SCSS, loaded after the theme styles |

Keep the YAML front matter at the top of `custom.scss`. To use Giscus, paste your script in its include, set `comments.provider: giscus` in `_config.yml` and set `show_comments: true` on the pages or post defaults that should display comments. Leave these files as they are if you only want to change content or choose a predefined skin.

The theme loads these four custom includes and the custom stylesheet. Other supported extensions use the following paths or settings:

| What to customize | Where to start |
| --- | --- |
| Fonts, skin variables, navbar, author, footer, analytics and search | The commented sections in `_config.yml` |
| Favicons and additional metadata | Add your files under `assets/` and reference them in `custom_head.html` |
| Your JavaScript | Add a file under `assets/js/` and load it from `custom_bottomscripts.html` using `relative_url` |
| A custom skin | Add `_sass/skins/NAME.scss`, then select `skin: NAME`; see the [theming guide](https://dieghernan.github.io/chulapa/docs/03-theming) |
| Page layout, header, TOC, diagrams and SEO | A page's YAML front matter or `defaults` in `_config.yml`; see [page options](https://dieghernan.github.io/chulapa/docs/04-layouts) |
| A theme layout or include | Copy that specific file to the same path in your site; local files override the remote theme |
| Generated Welcomments data | Follow the [comment provider instructions](https://dieghernan.github.io/chulapa/docs/02-config#comments) for `_data/welcomments/` and the required integration |

For example, to load your own script from the bottom hook:

```liquid
<script src="{{ '/assets/js/site.js' | relative_url }}"></script>
```

Create the script before adding the reference. Custom scripts and styles should preserve keyboard access, readable contrast and useful metadata. A local layout or include override must be checked against theme updates because updates do not replace your copy.

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

The remote theme follows <span class="chulapa">Chulapa</span>'s default branch. A fresh build can pick up theme updates. Your content and configuration remain in this repository. To pin a release, append `@TAG` to `remote_theme` in `_config.yml`.

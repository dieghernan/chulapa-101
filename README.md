# Chulapa 101

A ready-to-use personal blog based on [Chulapa's minimal blog example](https://github.com/dieghernan/chulapa/tree/main/examples/personal-blog). Its home page lists recent posts. It includes an about page, search and RSS, using the predefined Gitdev skin without color or CSS overrides.

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
| Home page heading and introduction | `index.md` |
| About page | `_pages/about.md` |
| Blog posts | `_posts/` |
| Images | Create an `assets/img/` folder |

For a new post, create a file such as `_posts/2026-01-01-hello.md`. Start it with:

```markdown
---
title: Hello
---

This is my first post.
```

Use the publication date in the filename. Posts with a future date remain unpublished until a build runs on or after that date. You can edit or delete the sample posts through GitHub's file editor.

## Choose a skin

Change `skin: gitdev` under `chulapa-skin` in `_config.yml` to another [predefined skin](https://dieghernan.github.io/chulapa/skins). No CSS changes are required.

See the [Chulapa documentation](https://dieghernan.github.io/chulapa/docs) for additional features and settings. This starter keeps one sample post and three pages so you can begin with a small site.

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

# Chulapa 101

Create a site with the [Chulapa Jekyll theme](https://github.com/dieghernan/chulapa) using [this template](https://github.com/dieghernan/chulapa-101/generate).

## Getting started

1. Create your repository from the template.
2. Edit `_config.yml`: set your title, description, author and repository.
3. Set `url` to your site origin and `baseurl` to `/repository` for a project site or `""` for a root site. The Pages workflow sets the deployment base path automatically.
4. Replace the sample posts, pages, images and navigation links.
5. Enable GitHub Pages with **GitHub Actions** as its source.

## Run locally

Install Ruby and Bundler, then run these commands from the repository directory:

```sh
bundle install
bundle exec jekyll serve --host localhost --baseurl ""
```

Open <http://localhost:4000>. Restart Jekyll after editing `_config.yml`.
The Pages workflow uses Ruby 3.4 and this template uses Jekyll 4.4.

## Configuration

[`_config.yml`](_config.yml) follows the current Chulapa configuration
structure:

- Site settings, social locales, author and optional JSON-LD publisher.
- Font Awesome, analytics, search and comment providers.
- Navigation, footer, fonts, skins and syntax highlighting.
- Pagination, collections, front matter defaults and Jekyll settings.

Blank settings use theme defaults where available. Replace the sample content
and identity settings before publishing. Image metadata must describe the actual
image.

The template uses Fuse.js search, four posts per blog page and a Markdown
cheatsheet collection. Autotheming is enabled with `lightskyblue` as the primary
color.

## Page options and examples

[`_pages/theme-options.md`](_pages/theme-options.md) demonstrates options
available in Chulapa 2.1.0: independent `seo_title` and `og_title`, a shared
`description`, social image metadata, page language, Open Graph locales,
`og_type: article`, `schema_image` and video metadata.

Use `canonical_url` only when a page should identify a different canonical URL;
ordinary pages use their generated URL. Set `robots: "noindex, follow"` for
pages such as search results, as shown in
[`_pages/search.md`](_pages/search.md). Robots metadata does not remove a page
from the sitemap; use `sitemap: false` when needed.

[`_pages/minimal-header.md`](_pages/minimal-header.md) demonstrates `layout:
minimal` with `show_header: true`.

See the complete [page and snippet reference](https://dieghernan.github.io/chulapa/docs/04-layouts), [site configuration](https://dieghernan.github.io/chulapa/docs/02-config) and [theming guide](https://dieghernan.github.io/chulapa/docs/03-theming).

## Included content

- Sample posts, a paginated blog and year, category and tag archives.
- Markdown and kramdown cheatsheets.
- A Bootstrap component demo and a 404 page.
- Fuse.js search, an Atom feed, an RSS feed and a generated sitemap.
- Custom include hooks in [`_includes/custom/`](_includes/custom/) and CSS in [`assets/css/`](assets/css/).
- Optional Algolia indexing configuration in [`algolia-search.yml`](algolia-search.yml).

## Theme updates

```yaml
remote_theme: dieghernan/chulapa
```

The remote theme follows Chulapa's default branch without pinning a release. A
fresh build downloads the theme from that branch, so rebuilding can pick up
upstream changes even without editing this repository. The examples have been
updated for Chulapa 2.1.0.

Theme updates do not replace this repository's configuration, content or local overrides. Review the [Chulapa changelog](https://github.com/dieghernan/chulapa/blob/main/CHANGELOG.md) when updating. `bundle update` updates Ruby dependencies, not the remote theme version.

# Jericho Stewardship Group

A Jekyll recreation of the Jericho Stewardship Group website, published with GitHub Pages.

## Files

- `index.md` contains the homepage.
- The other root-level Markdown files contain the site pages.
- `_posts/` contains dated blog posts in Markdown.
- `_layouts/` contains the shared templates based on the original site design.
- `_includes/` contains the shared forms, page directory, and blog index.
- `assets/website/` contains the local images and documents from the source site.
- `styles.css` contains the original, unchanged stylesheet.
- `_config.yml` contains the Jekyll and GitHub Pages settings.

Edit the relevant Markdown file to update page content. Each page has YAML front matter with a title and permalink. Add blog posts as `_posts/YYYY-MM-DD-title.md`.

## Local preview

Install Ruby and Bundler, then run these commands from the repository directory:

```bash
bundle install
bundle exec jekyll serve --livereload
```

Open <http://localhost:4000>. Jekyll rebuilds the site when content changes. Press Ctrl+C to stop the server.

To build without a server:

```bash
bundle exec jekyll build
```

Jekyll writes the generated HTML to `_site/`. Do not edit or commit that directory.

## GitHub Pages

Set the repository's Pages source to **GitHub Actions**. The existing `.github/workflows/jekyll-gh-pages.yml` builds and deploys Jekyll after a push to `main`.

The site uses the `github-pages` gem for local compatibility with the deployment environment. Internal links and assets use Jekyll's `relative_url` filter, including for sites with a `baseurl`.

The newsletter form retains its Mailchimp endpoint. The contact form opens the visitor's email application; GitHub Pages does not run the original WordPress form backend.

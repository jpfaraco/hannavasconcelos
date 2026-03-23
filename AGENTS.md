# Repository Guidelines

## Project Structure & Module Organization

This repository is a Jekyll-based marketing and content site. Core configuration lives in `_config.yml` and Ruby dependencies in `Gemfile`.

- `_includes/`: reusable sections such as `hero.html`, `faq.html`, and navigation partials.
- `_layouts/`: page shells for home, landing, post, testimonial, and workplace pages.
- `_posts/`: dated blog content named `YYYY-MM-DD-slug.md`.
- `_faqs/`, `_specialties/`, `_testimonials/`, `_workplaces/`: content collections driven by front matter.
- `_sass/` and `assets/css/main.scss`: SCSS partials and the main stylesheet entrypoint.
- `assets/`: images, fonts, PDFs, and other static files.
- `_site/`: generated output. Treat it as build artifact, not primary source.

## Build, Test, and Development Commands

- `bundle install`: install Ruby gems from `Gemfile`.
- `bundle exec jekyll serve`: run the local dev server at `http://localhost:4000`.
- `bundle exec jekyll build`: generate the production site into `_site/`.
- `bundle exec jekyll serve --drafts`: preview unpublished content when needed.

Restart the server after editing `_config.yml`; Jekyll does not reload that file automatically.

## Coding Style & Naming Conventions

Use 2-space indentation in YAML, Liquid, and SCSS to match the existing files. Keep Markdown front matter minimal and explicit. Name posts with lowercase, hyphenated slugs; keep collection files descriptive, for example `_faqs/vesicula-03-cuidados-pos-operatorio.md`.

Prefer reusable HTML in `_includes/` over duplicating markup in layouts. Add styles as SCSS partials in `_sass/` and import them through `assets/css/main.scss`.

## Testing Guidelines

There is no automated test suite in this repository. Validate changes with:

- `bundle exec jekyll build` to catch Liquid, front matter, and Sass errors.
- Manual review in `bundle exec jekyll serve`, especially for navigation, schema markup, and responsive content blocks.

When editing collections, confirm that front matter keys such as `layout`, `topic`, `order`, and `sitemap` still render correctly.

## Commit & Pull Request Guidelines

Recent history favors short, imperative commit messages, often using Conventional Commit prefixes such as `feat:` and concise refactor summaries. Follow that pattern, for example `feat: add FAQ entries for umbilical hernia`.

Pull requests should include a brief scope summary, affected paths, manual verification steps, and screenshots for layout or styling changes. Link the relevant issue or content request when one exists.

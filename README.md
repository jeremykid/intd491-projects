# INTD 491 Project Showcase

A Jekyll + GitHub Pages scaffold for publishing student projects as semester archives and individual project detail pages.

## Stack

- Jekyll 4
- Minimal Mistakes theme
- GitHub Pages deployment through GitHub Actions
- `_projects/` collection for authoring

## Repo layout

```text
.
├── .github/workflows/pages.yml
├── 2025-fall/index.md
├── 2026-spring/index.md
├── _config.yml
├── _data/navigation.yml
├── _includes/
├── _layouts/
├── _projects/
├── assets/
├── CONTRIBUTING.md
├── Gemfile
└── index.md
```

## Local development

Install dependencies:

```bash
bundle install
```

Run the site locally:

```bash
bundle exec jekyll serve
```

Then open `http://127.0.0.1:4000/`.

Use a modern Ruby 3.x install for local work. The GitHub Pages workflow builds with Ruby `3.3`.

## How the content model works

- Every project lives in `_projects/` as one markdown file.
- Each project must include these front matter fields:
  - `title`
  - `semester`
  - `team`
  - `tags`
  - `repo_url`
  - `demo_url`
  - `poster_image`
  - `short_abstract`
- Each semester archive is a normal page folder such as `2026-spring/index.md`.
- The home page reads semester archive pages and automatically renders cards for matching projects.

## Add a new semester

1. Copy an existing folder such as `2026-spring/`.
2. Rename it to the new slug, for example `2026-fall/`.
3. Update the front matter in `index.md`:
   - `title`
   - `semester`
   - `semester_order`
   - `description`
   - `permalink`
4. Add projects under `_projects/` using the exact same `semester` slug.

## Add a new project

1. Copy `_projects/_TEMPLATE.md` to a new file.
2. Add your poster image under `assets/images/posters/`.
3. Fill in the front matter and body content.
4. Publish it by removing `published: false` or changing it to `published: true`.

See `CONTRIBUTING.md` for the student-friendly version.

## GitHub Pages deployment

The workflow in `.github/workflows/pages.yml`:

- installs the Ruby/Jekyll dependencies from `Gemfile`,
- detects whether the repository is a user site (`username.github.io`) or a project site,
- injects the correct `url` and `baseurl` during the build,
- uploads `_site/` and deploys it to GitHub Pages.

This means the same repo can be pushed directly as either:

- `https://username.github.io/`
- `https://username.github.io/repository-name/`

without editing `_config.yml` by hand for deployment.

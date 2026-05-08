# Repository Guidelines

## Project Structure & Module Organization

This repository is a Hugo static documentation site using the Geekdoc theme. Author-facing content lives in `content/docs/`; add new cheatsheets and documentation pages there as Markdown files. Site-wide Hugo settings are in `config.toml`, deployment settings are in `netlify.toml`, and reusable page defaults are in `archetypes/`. The vendored theme lives under `themes/hugo-geekdoc/`; avoid editing it directly unless the change is intentionally theme-specific. Generated output is written to `public/` and should not be treated as source content. Netlify deploys the site with `hugo`, using the Hugo version configured in `netlify.toml`.

## Build, Test, and Development Commands

- `./dev-in-docker`: runs the local Hugo development server in Docker for previewing content.
- `hugo`: builds the static site into `public/` using the configured Geekdoc theme.
- `./update-hugo`: updates the Hugo version tracked in `netlify.toml`.
- `./update-theme`: updates the Geekdoc theme version.

Run `hugo` before review when changing content structure, front matter, templates, or configuration.

## Coding Style & Naming Conventions

Use standard Markdown with short sections, fenced code blocks, and descriptive link text. Documentation pages should include Hugo front matter with at least `title` and `weight`:

```yaml
---
title: "Markdown"
weight: 30
---
```

Name content files with lowercase, hyphen-separated names such as `bash-history.md` or `json-tools.md`. Keep examples copyable and prefer explicit language tags on code fences, for example ` ```bash ` or ` ```json `. Use Geekdoc shortcodes only when they improve navigation or readability; common examples include `{{< toc >}}`, `hint`, `expand`, and Mermaid diagram shortcodes.

## Testing Guidelines

There is no formal test framework in this repository. Validate changes by building with `hugo` and previewing with `./dev-in-docker` when layout or rendering may be affected. For Markdown-only edits, check front matter, heading hierarchy, tables, and fenced code blocks for valid rendering.

## Commit & Pull Request Guidelines

Recent history uses concise, imperative commit messages, with occasional Conventional Commit prefixes such as `docs:`. Prefer messages like `docs: add markdown cheatsheet`, `bump hugo to 0.155.3`, or `update lf docs`. Pull requests should describe the content or configuration changed, mention any local validation performed, and include screenshots when visual layout, navigation, or theme behavior changes.

## Agent Instructions

Treat this file as the canonical contributor guide for agents working in this repository. Keep edits scoped, preserve existing content style, and do not add attribution lines such as `Co-Authored-By` or `Signed-off-by` to commits.

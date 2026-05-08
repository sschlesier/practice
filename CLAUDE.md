# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Structure

This is a Hugo static documentation site using the Geekdoc theme.

- `content/docs/` — author-facing content (cheatsheets, documentation pages)
- `config.toml` — site-wide Hugo settings
- `netlify.toml` — deployment settings and Hugo version pin
- `archetypes/` — reusable page defaults
- `themes/hugo-geekdoc/` — vendored theme; avoid editing directly unless intentionally theme-specific
- `public/` — generated build output; not source content

## Build & Development Commands

- `./dev-in-docker` — runs Hugo server in Docker for local preview
- `hugo` — builds static site to `public/`
- `./update-hugo` — updates Hugo version in `netlify.toml`
- `./update-theme` — updates the Geekdoc theme

Run `hugo` before review when changing content structure, front matter, templates, or configuration.

## Content & Code Style

New documentation pages go in `content/docs/` as Markdown files. Use lowercase, hyphen-separated filenames such as `bash-history.md` or `json-tools.md`.

Front matter must include at minimum:

```yaml
---
title: "Document Title"
weight: 30
---
```

Use fenced code blocks with explicit language tags on every block, for example ` ```bash ` or ` ```json `. Keep examples short and copyable.

Use Geekdoc shortcodes when they improve navigation or readability: `{{< toc >}}`, `{{< hint >}}`, `{{< expand >}}`, mermaid diagrams via the mermaid shortcode.

## Testing

No formal testing framework. Validate changes by running `hugo` to catch build errors, then preview with `./dev-in-docker` when layout or rendering may be affected. For Markdown-only edits, check front matter, heading hierarchy, tables, and fenced code blocks.

## Commit & PR Guidelines

Use concise, imperative commit messages. Follow Conventional Commit prefixes where they fit: `docs:`, `fix:`, `chore:`. Examples: `docs: add markdown cheatsheet`, `bump hugo to 0.155.3`, `update lf docs`.

PRs should describe what content or configuration changed, mention any local validation performed, and include screenshots when visual layout, navigation, or theme behavior changes.

## Deployment

Site is deployed via Netlify using the `hugo` build command. Hugo version is pinned in `netlify.toml`.

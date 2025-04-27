# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build/Development Commands
- Development: `./dev-in-docker` (runs Hugo server in Docker)
- Build: `hugo` (builds static site to the `public` directory)
- Update Hugo: `./update-hugo` (updates Hugo version in netlify.toml)
- Update Theme: `./update-theme` (updates the Geekdoc theme)

## Testing
- No formal testing framework is used in this repository
- Preview changes locally using the development server

## Code Style Guidelines
- Use consistent frontmatter in Markdown files with `title` and `weight` parameters
- Follow standard Markdown formatting conventions
- For Hugo templates, follow the Geekdoc theme patterns in `themes/hugo-geekdoc`
- Content files should be organized in `content/docs/` directory
- Use Hugo shortcodes where appropriate (mermaid, hint, expand, etc.)
- Mermaid diagrams are supported through shortcodes

## Content Structure
- New documentation pages should be added to `content/docs/`
- Frontmatter should include at minimum:
  ```yaml
  ---
  title: "Document Title"
  weight: 1  # Controls order in navigation
  ---
  ```

## Deployment
- Site is deployed via Netlify using the Hugo build command
- Hugo version is specified in netlify.toml
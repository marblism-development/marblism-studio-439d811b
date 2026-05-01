# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev       # Start dev server at localhost:4321
npm run build     # Build production site to ./dist/
npm run preview   # Preview the production build locally
npm run astro     # Run Astro CLI commands (e.g. astro add, astro check)
```

No lint or test commands are configured yet.

## Architecture

This is an [Astro](https://astro.build) static site project using the basics template.

**Routing:** Every `.astro` file in `src/pages/` becomes a URL route. `index.astro` maps to `/`.

**Component model:** Astro components (`.astro`) use a frontmatter block (between `---` fences) for server-side logic and imports, followed by an HTML template. Styles in `<style>` blocks are scoped to the component by default.

**Layout pattern:** Pages import from `src/layouts/` to wrap content in shared HTML structure. `Layout.astro` provides the base `<html>` shell, `<head>`, and global styles.

**Assets:** SVGs in `src/assets/` are imported directly into components. Static files in `public/` are served at the root path as-is.

**Output:** Astro builds to plain HTML/CSS/JS in `dist/` with zero client-side JS by default — JS is only shipped if a component opts in via Astro's island architecture.

**TypeScript:** Configured in strict mode via `tsconfig.json`. Astro generates types into `.astro/`.

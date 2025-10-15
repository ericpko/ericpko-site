# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is Eric Koehli's minimal dev portfolio website built with Astro using the Chiri theme. It uses **Bun** as the package manager (not npm or pnpm).

## Development Commands

```bash
# Development
bun install          # Install dependencies
bun dev             # Start dev server

# Building
bun build           # Build for production (runs prebuild script first)
bun preview         # Preview production build

# Code Quality
bun lint            # Run ESLint
bun lint:fix        # Fix ESLint errors
bun format          # Format with Prettier
bun format:check    # Check formatting

# Content Management
bun new <title>     # Create new blog post (use _title for drafts)
bun update-theme    # Update theme from upstream repository
```

## Architecture

### Configuration System

**Main config file: `src/config.ts`**
- Exports `themeConfig` object with site info, general settings, date formatting, and post settings
- Controls critical features like `linkCard` which affects build-time adapter configuration

**Build-time configuration: `scripts/toggle-proxy.ts`**
- Runs automatically before builds via the `prebuild` script
- Reads `linkCard` setting from `src/config.ts`
- If `linkCard: false`: disables `src/pages/api/proxy.ts` and comments out adapter in `astro.config.ts`
- If `linkCard: true`: enables proxy and uncomments adapter configuration
- This conditional setup allows the site to work with or without server-side features

**Astro config: `astro.config.ts`**
- Uses `netlify()` adapter (can be changed for other platforms)
- Path alias: `@` maps to `./src`
- Custom remark/rehype plugins for markdown processing

### Content Structure

**Collections defined in `src/content.config.ts`:**
- `posts`: Blog posts from `src/content/posts/*.{md,mdx}`
  - Required frontmatter: `title`, `pubDate`
  - Optional: `image`
  - Files starting with `_` are treated as drafts
- `about`: About page content from `src/content/about/*.md`

### Markdown Processing Pipeline

**Remark plugins (process markdown AST):**
- `remarkMath` - Math notation support
- `remarkDirective` - Custom directives
- `remarkEmbeddedMedia` - Embed external media
- `remarkReadingTime` - Calculate reading time
- `remarkTOC` - Generate table of contents

**Rehype plugins (process HTML AST):**
- `rehypeKatex` - Render math with KaTeX
- `rehypeCleanup` - Clean up HTML output
- `rehypeImageProcessor` - Process images
- `rehypeCopyCode` - Add copy buttons to code blocks

### Component Organization

- `src/components/layout/` - Core layout components (Header, Footer, BaseHead)
- `src/components/ui/` - Reusable UI components (ImageViewer, ThemeToggle, LinkCard, etc.)
- `src/components/widgets/` - Feature widgets (PostList, FormattedDate, About)
- `src/components/examples/` - Example components for MDX usage
- `src/layouts/` - Page layouts (BaseLayout, PostLayout, IndexLayout)

### Theme System

- Supports light/dark mode via system preference or manual toggle
- `src/components/ui/ThemeManager.astro` - Central theme logic
- `src/components/ui/ThemeToggle.astro` - User-facing toggle button
- `src/components/ui/FaviconThemeSwitcher.astro` - Updates favicon based on theme

## Important Notes

### Adapter Configuration

Before deploying to a specific platform, you need to:
1. Install the appropriate adapter: `bun add @astrojs/[netlify|vercel|cloudflare|static]`
2. Update `adapter` in `astro.config.ts`
3. OR set `linkCard: false` in `src/config.ts` to disable server-side features

### Draft Posts

Posts with filenames starting with `_` (e.g., `_draft-example.md`) are drafts. Create them with `bun new _title`.

### Custom Scripts

- `scripts/new-post.ts` - Creates new post with proper frontmatter and filename sanitization
- `scripts/update-theme.ts` - Syncs with upstream Chiri theme repository (adds/updates upstream remote)
- `scripts/toggle-proxy.ts` - Conditionally enables/disables server-side features based on config

### Package Manager

This project uses **Bun**, not pnpm or npm. All package manager commands should use `bun`.

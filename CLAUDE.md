# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

### Development
- `npm install` - Install dependencies
- `npm run dev` or `npm start` - Start development server at http://localhost:4321
- `npm run build` - Run type checking with `astro check` then build for production
- `npm run preview` - Preview production build locally
- `npm run astro` - Run Astro CLI commands

### Deployment
The site automatically deploys to GitHub Pages when pushing to the main branch via GitHub Actions workflow (`.github/workflows/deploy.yml`).

## Architecture

This is an Astro static site with the following structure:

### Content Collections
- Blog posts live in `src/content/blog/` as Markdown files
- Content schema is defined in `src/content/config.ts` with title, date, and optional categories

### Layouts
- `BaseLayout.astro` - Main layout with Google Analytics, random header color, and responsive design
- `BlogPost.astro` - Wraps BaseLayout for blog post pages with metadata display

### Routing
- Static pages in `src/pages/` (index, about, 404)
- Dynamic blog routes via `src/pages/blog/[...slug].astro`
- Blog listing at `src/pages/blog/index.astro`

### Styling
- Bootstrap CSS and custom styles in `public/assets/css/`
- Header color randomization with contrast-aware text color

### Configuration
- `astro.config.mjs` requires updating the `site` field with actual GitHub username before deployment
- Base path is set to `/khunjon` for GitHub Pages deployment

### Key Implementation Details
- All asset URLs use `import.meta.env.BASE_URL` for proper GitHub Pages routing
- TypeScript is configured with relaxed settings
- Scripts marked with `is:inline` to prevent Astro processing
- Blog posts sorted by date in descending order
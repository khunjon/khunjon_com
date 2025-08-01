# Khun Jon - Astro Site

This is the converted Astro version of the Jekyll site.

## Local Development

1. Install dependencies:
   ```bash
   npm install
   ```

2. Start the development server:
   ```bash
   npm run dev
   ```

3. Build for production:
   ```bash
   npm run build
   ```

## GitHub Pages Deployment

1. Update the `astro.config.mjs` file:
   - Replace `yourusername` with your GitHub username in the `site` field
   - If your repository name is different from `khunjon`, update the `base` field

2. Push to GitHub:
   ```bash
   git add .
   git commit -m "Initial Astro site"
   git push
   ```

3. Enable GitHub Pages:
   - Go to your repository settings
   - Navigate to Pages
   - Under "Build and deployment", select "GitHub Actions" as the source

The site will be automatically deployed when you push to the main branch.
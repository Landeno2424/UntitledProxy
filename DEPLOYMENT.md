# Deployment Guide for Untitled Proxy

This guide will help you deploy your proxy to a live web server (not local).

## Option 1: Vercel (Recommended - Easiest)

1. Create a Vercel account at https://vercel.com
2. Install Vercel CLI or use the web dashboard
3. **Using Vercel CLI:**
   ```bash
   npm i -g vercel
   vercel login
   vercel --prod
   ```
4. **Using Vercel Dashboard:**
   - Click "New Project"
   - Import your GitHub repository
   - Click "Deploy"
5. Your site will be live at `https://your-project.vercel.app`

## Option 2: Netlify

1. Create a Netlify account at https://netlify.com
2. **Using Netlify CLI:**
   ```bash
   npm install -g netlify-cli
   netlify login
   netlify deploy --prod
   ```
3. **Using Netlify Dashboard:**
   - Click "Add new site" → "Import an existing project"
   - Connect your GitHub repository
   - Deploy settings are already configured in `netlify.toml`
   - Click "Deploy site"
4. Your site will be live at `https://your-site.netlify.app`

## Option 3: GitHub Pages

1. Go to your repository on GitHub
2. Navigate to Settings → Pages
3. Under "Build and deployment":
   - Source: Select "GitHub Actions"
4. Push your code to the `main` branch
5. The workflow will automatically deploy your site
6. Your site will be live at `https://yourusername.github.io/UntitledProxy`

## Option 4: Cloudflare Pages

1. Create a Cloudflare account at https://pages.cloudflare.com
2. Click "Create a project"
3. Connect your GitHub repository
4. Build settings:
   - Build command: (leave empty)
   - Build output directory: `/`
5. Click "Save and Deploy"
6. Your site will be live at `https://your-project.pages.dev`

## Option 5: Render

1. Create a Render account at https://render.com
2. Click "New" → "Static Site"
3. Connect your GitHub repository
4. Build settings:
   - Build Command: (leave empty)
   - Publish Directory: `.`
5. Click "Create Static Site"
6. Your site will be live at `https://your-project.onrender.com`

## Quick Deploy Buttons

Click one of these buttons to deploy instantly:

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/MaxWeichers/UntitledProxy)

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/MaxWeichers/UntitledProxy)

## Custom Domain (Optional)

After deployment, you can add a custom domain:
- **Vercel:** Settings → Domains
- **Netlify:** Site settings → Domain management
- **GitHub Pages:** Settings → Pages → Custom domain
- **Cloudflare Pages:** Custom domains tab
- **Render:** Settings → Custom domain

## Notes

- All these platforms offer free tiers perfect for hosting this proxy
- The proxy uses a Cloudflare Workers backend (already configured)
- No build step is required - it's pure static HTML/JS/CSS
- Make sure to keep your repository public or upgrade to a paid plan for private repos

## Troubleshooting

If the proxy doesn't work after deployment:
1. Check browser console for errors
2. Verify the bare server backend is running: https://github.com/MaxWeichers/bare-server-workers
3. Ensure all files (especially `uv/` directory) were deployed correctly
4. Clear your browser cache and try again

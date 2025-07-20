# ChatAt Website - Quick Deployment Guide

## Prerequisites
- Hugo Extended v0.92.0 or higher
- Git
- GitHub account (for GitHub Pages) or Netlify account

## Quick Start

### 1. Test Locally
```bash
cd ChatAtWebsite
hugo server --disableKinds=RSS
```
Visit `http://localhost:1313` to preview your site.

### 2. Deploy to GitHub Pages

1. **Create GitHub Repository**
   - Create a new repository on GitHub
   - Name it `yourusername.github.io` or any project name

2. **Push Your Code**
   ```bash
   git init
   git add .
   git commit -m "Initial commit: ChatAt website"
   git remote add origin https://github.com/yourusername/your-repo.git
   git push -u origin main
   ```

3. **Set Up GitHub Actions**
   Create `.github/workflows/hugo.yml`:
   ```yaml
   name: Deploy Hugo site to Pages
   on:
     push:
       branches: ["main"]
   permissions:
     contents: read
     pages: write
     id-token: write
   jobs:
     build:
       runs-on: ubuntu-latest
       steps:
         - name: Checkout
           uses: actions/checkout@v4
         - name: Setup Hugo
           uses: peaceiris/actions-hugo@v2
           with:
             hugo-version: '0.92.2'
             extended: true
         - name: Build
           run: hugo --minify --disableKinds=RSS
         - name: Upload artifact
           uses: actions/upload-pages-artifact@v2
           with:
             path: ./public
     deploy:
       environment:
         name: github-pages
         url: ${{ steps.deployment.outputs.page_url }}
       runs-on: ubuntu-latest
       needs: build
       steps:
         - name: Deploy to GitHub Pages
           uses: actions/deploy-pages@v3
   ```

4. **Enable GitHub Pages**
   - Go to repository Settings → Pages
   - Select "GitHub Actions" as source

### 3. Deploy to Netlify

1. **Connect Repository**
   - Sign up at netlify.com
   - Click "New site from Git"
   - Connect your GitHub repository

2. **Configure Build Settings**
   ```
   Build command: hugo --minify --disableKinds=RSS
   Publish directory: public
   Environment variables:
     HUGO_VERSION: 0.92.2
   ```

3. **Enable Forms** (for contact form)
   - Go to Site settings → Forms
   - Enable form detection
   - Update contact form action to use Netlify

## Important Notes

- The site uses `--disableKinds=RSS` to avoid RSS template errors
- Custom CSS is in `assets/css/extended/custom.css`
- Multilingual content is in `content/english/` and `content/arabic/`
- Contact form requires Formspree setup or Netlify forms

## Customization

### Update Contact Form
1. Sign up at formspree.io
2. Create a new form
3. Replace `YOUR_FORM_ID` in `layouts/shortcodes/contact-form.html`

### Modify Colors
Edit CSS variables in `assets/css/extended/custom.css`:
```css
:root {
  --primary-color: #2563eb;  /* Change this */
  --accent-color: #f59e0b;   /* And this */
}
```

### Add Content
- English: Add files to `content/english/`
- Arabic: Add files to `content/arabic/`
- Update menus in `config.toml`

## Support
- Check README.md for detailed documentation
- Hugo documentation: https://gohugo.io/documentation/
- PaperMod theme: https://github.com/adityatelange/hugo-PaperMod


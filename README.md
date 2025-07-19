# ChatAt - Multilingual Hugo Website

A modern, lightweight, and accessible multilingual website built with Hugo and the PaperMod theme, supporting both English and Arabic (RTL) languages.

## Table of Contents

1. [Project Overview](#project-overview)
2. [Features](#features)
3. [Prerequisites](#prerequisites)
4. [Installation Guide](#installation-guide)
5. [Configuration](#configuration)
6. [Content Management](#content-management)
7. [Customization](#customization)
8. [Deployment](#deployment)
9. [Maintenance](#maintenance)
10. [Troubleshooting](#troubleshooting)
11. [Contributing](#contributing)
12. [License](#license)

## Project Overview

ChatAt is designed as a friendly, accessible platform for sharing written content across languages and cultures. The website features a clean, modern design with full support for Right-to-Left (RTL) languages like Arabic, making it truly inclusive for global audiences.

### Key Design Principles

- **Simplicity**: Clean, distraction-free interface that puts content first
- **Accessibility**: Full RTL support and responsive design for all devices
- **Performance**: Static site generation for fast loading times
- **Multilingual**: Seamless language switching between English and Arabic
- **Cost-effective**: Designed for free hosting on platforms like GitHub Pages or Netlify

## Features

### Core Features
- ✅ Multilingual support (English/Arabic)
- ✅ RTL (Right-to-Left) text rendering
- ✅ Responsive design for mobile and desktop
- ✅ Dark/Light theme toggle
- ✅ Fast static site generation
- ✅ SEO optimized
- ✅ Contact form integration
- ✅ Search functionality
- ✅ Modern CSS animations and transitions

### Content Sections
- **About**: Introduction to ChatAt and its mission
- **Books**: Showcase of publications and reading recommendations
- **Contact**: Multiple ways to get in touch with the community

### Technical Features
- Hugo static site generator
- PaperMod theme with custom enhancements
- Custom CSS with modern design patterns
- Formspree integration for contact forms
- Language switcher component
- Optimized for GitHub Pages/Netlify deployment



## Prerequisites

Before setting up the ChatAt website, ensure you have the following installed on your system:

### Required Software
- **Hugo Extended**: Version 0.92.0 or higher
- **Git**: For version control and theme management
- **Text Editor**: VS Code, Sublime Text, or any preferred editor
- **Web Browser**: For local testing and preview

### Optional Tools
- **Node.js**: For advanced customizations and build tools
- **GitHub Account**: For version control and GitHub Pages deployment
- **Netlify Account**: For alternative deployment option

### System Requirements
- **Operating System**: Windows, macOS, or Linux
- **RAM**: Minimum 2GB (4GB recommended)
- **Storage**: At least 500MB free space
- **Internet Connection**: Required for theme installation and deployment

## Installation Guide

Follow these step-by-step instructions to set up your ChatAt website locally.

### Step 1: Install Hugo

#### On Windows
1. Download Hugo Extended from the [official releases page](https://github.com/gohugoio/hugo/releases)
2. Extract the executable to a folder (e.g., `C:\Hugo\bin`)
3. Add the folder to your system PATH
4. Verify installation by running `hugo version` in Command Prompt

#### On macOS
```bash
# Using Homebrew (recommended)
brew install hugo

# Or using MacPorts
sudo port install hugo
```

#### On Linux (Ubuntu/Debian)
```bash
# Install from package manager
sudo apt-get update
sudo apt-get install hugo

# Or download the latest version manually
wget https://github.com/gohugoio/hugo/releases/download/v0.92.2/hugo_extended_0.92.2_Linux-64bit.deb
sudo dpkg -i hugo_extended_0.92.2_Linux-64bit.deb
```

### Step 2: Clone or Download the Project

#### Option A: Clone from Repository (if available)
```bash
git clone https://github.com/yourusername/chatat-website.git
cd chatat-website
```

#### Option B: Create from Scratch
```bash
# Create new Hugo site
hugo new site ChatAtWebsite
cd ChatAtWebsite

# Clone the PaperMod theme
git clone https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```

### Step 3: Set Up the Project Structure

If you're creating from scratch, you'll need to set up the following directory structure:

```
ChatAtWebsite/
├── assets/
│   └── css/
│       └── extended/
│           └── custom.css
├── content/
│   ├── english/
│   │   ├── about.md
│   │   ├── books.md
│   │   └── contact.md
│   └── arabic/
│       ├── about.md
│       ├── books.md
│       └── contact.md
├── layouts/
│   ├── partials/
│   │   ├── head.html
│   │   └── language-switcher.html
│   └── shortcodes/
│       ├── contact-form.html
│       └── search.html
├── static/
├── themes/
│   └── PaperMod/
├── config.toml
└── README.md
```

### Step 4: Configure the Website

Copy the provided `config.toml` file to your project root, or create it with the multilingual configuration as shown in the Configuration section below.

### Step 5: Add Content

Copy the provided content files to their respective directories:
- English content goes in `content/english/`
- Arabic content goes in `content/arabic/`

### Step 6: Test Locally

Run the Hugo development server to test your website:

```bash
hugo server -D
```

Open your browser and navigate to `http://localhost:1313` to see your website in action.


## Configuration

The `config.toml` file is the heart of your Hugo website configuration. Here's a detailed breakdown of the key settings:

### Basic Site Settings

```toml
baseURL = "https://yourdomain.com/"
languageCode = "en-us"
title = "ChatAt"
theme = "PaperMod"

enableRobotsTXT = true
buildDrafts = false
buildFuture = false
buildExpired = false
```

### Multilingual Configuration

The multilingual setup allows your website to serve content in both English and Arabic:

```toml
[languages]
  [languages.en]
    contentDir = "content/english"
    languageName = "English"
    languageCode = "en-us"
    weight = 1
    title = "ChatAt"
    
  [languages.ar]
    contentDir = "content/arabic"
    languageName = "العربية"
    languageCode = "ar-sa"
    weight = 2
    title = "شات آت"
    rtl = true
```

### Theme Parameters

Customize the PaperMod theme behavior:

```toml
[params]
  defaultTheme = "auto"
  disableThemeToggle = false
  ShowReadingTime = true
  ShowShareButtons = true
  ShowPostNavLinks = true
  ShowBreadCrumbs = true
  ShowCodeCopyButtons = true
  ShowWordCount = true
  ShowRss = true
  disableScrollToTop = false
  hideFooter = false
  ShowLastmod = true
  ShowToc = true
  TocOpen = true
```

### Menu Configuration

Set up navigation menus that work across languages:

```toml
[menu]
  [[menu.main]]
    identifier = "about"
    name = "About"
    url = "/about/"
    weight = 10

  [[menu.main]]
    identifier = "books"
    name = "Books"
    url = "/books/"
    weight = 20

  [[menu.main]]
    identifier = "contact"
    name = "Contact"
    url = "/contact/"
    weight = 30
```

### Important Configuration Notes

1. **Base URL**: Update the `baseURL` to match your actual domain
2. **Content Directories**: Each language has its own content directory
3. **RTL Support**: The `rtl = true` setting enables right-to-left text for Arabic
4. **Language Weights**: Lower weights appear first in language switchers

## Content Management

Managing content in a multilingual Hugo site requires understanding the content structure and translation workflow.

### Content Structure

Each language maintains its own content directory:

```
content/
├── english/
│   ├── _index.md          # Home page content
│   ├── about.md           # About page
│   ├── books.md           # Books page
│   ├── contact.md         # Contact page
│   └── posts/             # Blog posts (optional)
└── arabic/
    ├── _index.md          # Arabic home page
    ├── about.md           # Arabic about page
    ├── books.md           # Arabic books page
    ├── contact.md         # Arabic contact page
    └── posts/             # Arabic blog posts (optional)
```

### Front Matter

Each content file begins with front matter that defines metadata:

```yaml
---
title: "Page Title"
date: 2025-07-19T10:00:00+00:00
draft: false
description: "Page description for SEO"
tags: ["tag1", "tag2"]
categories: ["category1"]
---
```

### Creating New Content

#### Adding a New Page

1. **English Version**:
   ```bash
   hugo new content/english/new-page.md
   ```

2. **Arabic Version**:
   ```bash
   hugo new content/arabic/new-page.md
   ```

3. **Edit the content** in your preferred text editor

4. **Update navigation** in `config.toml` if needed

#### Adding Blog Posts

1. **Create post directories** if they don't exist:
   ```bash
   mkdir -p content/english/posts
   mkdir -p content/arabic/posts
   ```

2. **Create new posts**:
   ```bash
   hugo new content/english/posts/my-first-post.md
   hugo new content/arabic/posts/my-first-post.md
   ```

### Translation Workflow

1. **Write content in your primary language** (usually English)
2. **Translate to secondary language** (Arabic in this case)
3. **Ensure both versions have matching file names** for proper linking
4. **Test language switching** to verify proper connections
5. **Review RTL formatting** for Arabic content

### Content Guidelines

#### For English Content
- Use clear, concise language
- Follow standard web writing practices
- Include proper headings hierarchy (H1, H2, H3)
- Add alt text for images
- Use descriptive link text

#### For Arabic Content
- Ensure proper RTL text flow
- Use appropriate Arabic typography
- Consider cultural context in translations
- Test readability on different devices
- Verify proper date and number formatting

### SEO Optimization

1. **Title Tags**: Keep under 60 characters
2. **Meta Descriptions**: 150-160 characters optimal
3. **Headings**: Use proper hierarchy (H1 → H2 → H3)
4. **Internal Linking**: Link between related pages
5. **Image Optimization**: Use descriptive file names and alt text

### Content Maintenance

1. **Regular Updates**: Keep content fresh and relevant
2. **Link Checking**: Verify internal and external links work
3. **Translation Sync**: Ensure translations stay current
4. **Performance Monitoring**: Check page load times
5. **User Feedback**: Incorporate visitor suggestions


## Customization

The ChatAt website is designed to be easily customizable while maintaining its clean, professional appearance.

### Custom CSS

The main customization file is located at `assets/css/extended/custom.css`. This file includes:

#### Typography Customization
```css
/* Custom font imports */
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Amiri:wght@400;700&display=swap');

/* Font family assignments */
body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
}

/* Arabic-specific fonts */
[dir="rtl"] body {
  font-family: 'Amiri', 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
}
```

#### Color Scheme Customization
```css
:root {
  --primary-color: #2563eb;      /* Main brand color */
  --primary-hover: #1d4ed8;      /* Hover state */
  --accent-color: #f59e0b;       /* Accent highlights */
  --text-primary: #1f2937;       /* Main text color */
  --text-secondary: #6b7280;     /* Secondary text */
  --bg-primary: #ffffff;         /* Background color */
  --bg-secondary: #f9fafb;       /* Secondary background */
  --border-color: #e5e7eb;       /* Border color */
}
```

#### Animation and Transition Effects
```css
/* Smooth transitions */
:root {
  --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

/* Fade-in animation */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
```

### Layout Customizations

#### Header Modifications
To customize the header appearance, edit the CSS for `.header` class:

```css
.header {
  backdrop-filter: blur(10px);
  background-color: rgba(255, 255, 255, 0.9);
  border-bottom: 1px solid var(--border-color);
}
```

#### Navigation Menu Styling
Customize menu appearance and behavior:

```css
.menu a {
  position: relative;
  padding: 0.5rem 1rem;
  color: var(--text-secondary);
  transition: var(--transition);
}

.menu a:hover {
  color: var(--primary-color);
  transform: translateY(-1px);
}
```

### Adding New Shortcodes

Shortcodes are reusable content components. To create a new shortcode:

1. **Create the shortcode file** in `layouts/shortcodes/`:
   ```html
   <!-- layouts/shortcodes/custom-component.html -->
   <div class="custom-component">
     <h3>{{ .Get "title" }}</h3>
     <p>{{ .Inner }}</p>
   </div>
   ```

2. **Use in content files**:
   ```markdown
   {{< custom-component title="My Title" >}}
   This is the content inside the shortcode.
   {{< /custom-component >}}
   ```

### Language-Specific Customizations

#### RTL Layout Adjustments
For Arabic content, specific RTL styles are applied:

```css
[dir="rtl"] {
  text-align: right;
}

[dir="rtl"] .menu {
  flex-direction: row-reverse;
}

[dir="rtl"] .post-content,
[dir="rtl"] .page-content {
  text-align: right;
}
```

#### Font Loading for Arabic
Ensure proper Arabic font loading:

```css
/* Preload Arabic fonts */
@font-face {
  font-family: 'Amiri';
  font-display: swap;
  src: url('path-to-arabic-font.woff2') format('woff2');
}
```

### Theme Customization

#### Overriding Theme Templates
To customize PaperMod theme templates:

1. **Copy the template** from `themes/PaperMod/layouts/` to `layouts/`
2. **Modify the copied file** to suit your needs
3. **Hugo will use your custom version** instead of the theme default

#### Adding Custom Partials
Create custom partial templates in `layouts/partials/`:

```html
<!-- layouts/partials/custom-footer.html -->
<footer class="custom-footer">
  <p>&copy; {{ now.Year }} ChatAt. All rights reserved.</p>
</footer>
```

### Performance Optimizations

#### Image Optimization
```css
/* Responsive images */
img {
  max-width: 100%;
  height: auto;
  loading: lazy;
}
```

#### CSS Minification
Hugo automatically minifies CSS when building for production:

```toml
[minify]
  [minify.css]
    precision = 2
```

## Deployment

The ChatAt website can be deployed to various hosting platforms. Here are the most popular options:

### GitHub Pages Deployment

GitHub Pages offers free hosting for static websites directly from your GitHub repository.

#### Prerequisites
- GitHub account
- Git installed locally
- Repository with your Hugo site

#### Step-by-Step Deployment

1. **Create a GitHub Repository**:
   - Go to GitHub and create a new repository
   - Name it `yourusername.github.io` for a user site, or any name for a project site
   - Initialize with a README if starting fresh

2. **Prepare Your Local Repository**:
   ```bash
   # Initialize git in your Hugo site directory
   cd ChatAtWebsite
   git init
   
   # Add GitHub repository as remote
   git remote add origin https://github.com/yourusername/your-repo-name.git
   
   # Create .gitignore file
   echo "public/" >> .gitignore
   echo ".hugo_build.lock" >> .gitignore
   ```

3. **Set Up GitHub Actions**:
   Create `.github/workflows/hugo.yml`:
   ```yaml
   name: Deploy Hugo site to Pages

   on:
     push:
       branches: ["main"]
     workflow_dispatch:

   permissions:
     contents: read
     pages: write
     id-token: write

   concurrency:
     group: "pages"
     cancel-in-progress: false

   defaults:
     run:
       shell: bash

   jobs:
     build:
       runs-on: ubuntu-latest
       env:
         HUGO_VERSION: 0.92.2
       steps:
         - name: Install Hugo CLI
           run: |
             wget -O ${{ runner.temp }}/hugo.deb https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb \
             && sudo dpkg -i ${{ runner.temp }}/hugo.deb
         - name: Checkout
           uses: actions/checkout@v4
           with:
             submodules: recursive
         - name: Setup Pages
           id: pages
           uses: actions/configure-pages@v4
         - name: Build with Hugo
           env:
             HUGO_ENVIRONMENT: production
             HUGO_ENV: production
           run: |
             hugo \
               --minify \
               --baseURL "${{ steps.pages.outputs.base_url }}/"
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
           id: deployment
           uses: actions/deploy-pages@v3
   ```

4. **Configure GitHub Pages**:
   - Go to your repository settings
   - Navigate to "Pages" section
   - Select "GitHub Actions" as the source
   - Save the configuration

5. **Deploy Your Site**:
   ```bash
   # Add all files to git
   git add .
   
   # Commit changes
   git commit -m "Initial commit: ChatAt website"
   
   # Push to GitHub
   git push -u origin main
   ```

6. **Access Your Site**:
   Your site will be available at `https://yourusername.github.io/your-repo-name/`

### Netlify Deployment

Netlify provides excellent hosting for static sites with additional features like form handling and continuous deployment.

#### Quick Deployment Steps

1. **Sign Up for Netlify**:
   - Go to [netlify.com](https://netlify.com)
   - Sign up using GitHub, GitLab, or email

2. **Connect Your Repository**:
   - Click "New site from Git"
   - Choose your Git provider (GitHub recommended)
   - Select your ChatAt repository

3. **Configure Build Settings**:
   ```
   Build command: hugo --minify
   Publish directory: public
   Environment variables:
     HUGO_VERSION: 0.92.2
   ```

4. **Deploy**:
   - Click "Deploy site"
   - Netlify will build and deploy your site automatically
   - You'll get a random subdomain (e.g., `amazing-site-123.netlify.app`)

5. **Custom Domain** (Optional):
   - Go to Site settings → Domain management
   - Add your custom domain
   - Configure DNS settings as instructed

#### Netlify Forms Setup

To enable the contact form functionality:

1. **Update Form Action**:
   In your contact form shortcode, replace `YOUR_FORM_ID` with `netlify`:
   ```html
   <form action="/contact/" method="POST" data-netlify="true">
   ```

2. **Add Hidden Field**:
   ```html
   <input type="hidden" name="form-name" value="contact" />
   ```

3. **Enable Form Detection**:
   - Go to Site settings → Forms
   - Enable form detection
   - Your forms will appear after the next deployment

### Alternative Deployment Options

#### Vercel
1. Install Vercel CLI: `npm i -g vercel`
2. Run `vercel` in your project directory
3. Follow the prompts to deploy

#### Firebase Hosting
1. Install Firebase CLI: `npm install -g firebase-tools`
2. Initialize Firebase: `firebase init hosting`
3. Build your site: `hugo --minify`
4. Deploy: `firebase deploy`

#### Custom Server
For deployment on your own server:

1. **Build the site**:
   ```bash
   hugo --minify
   ```

2. **Upload the `public/` directory** to your web server

3. **Configure web server** (Apache/Nginx) to serve static files

### Deployment Best Practices

1. **Environment Variables**: Use different configurations for development and production
2. **Build Optimization**: Always use `--minify` flag for production builds
3. **Cache Headers**: Configure proper cache headers for static assets
4. **SSL Certificate**: Ensure HTTPS is enabled (most platforms provide this automatically)
5. **Monitoring**: Set up uptime monitoring for your deployed site
6. **Backup**: Regularly backup your content and configuration files


## Maintenance

Regular maintenance ensures your ChatAt website remains secure, fast, and up-to-date.

### Regular Maintenance Tasks

#### Weekly Tasks
1. **Content Review**: Check for outdated information and update as needed
2. **Link Verification**: Test internal and external links for broken connections
3. **Performance Check**: Monitor site loading speed using tools like Google PageSpeed Insights
4. **Security Scan**: Review for any security vulnerabilities or suspicious activity

#### Monthly Tasks
1. **Hugo Updates**: Check for new Hugo releases and update if necessary
2. **Theme Updates**: Update the PaperMod theme to the latest version
3. **Content Backup**: Create backups of all content and configuration files
4. **Analytics Review**: Analyze visitor statistics and user behavior
5. **SEO Audit**: Review search engine optimization and rankings

#### Quarterly Tasks
1. **Comprehensive Content Audit**: Review all pages for accuracy and relevance
2. **Design Review**: Assess user interface and user experience
3. **Performance Optimization**: Optimize images, CSS, and JavaScript
4. **Accessibility Testing**: Ensure compliance with web accessibility standards
5. **Mobile Responsiveness**: Test on various devices and screen sizes

### Updating Hugo and Theme

#### Updating Hugo
1. **Check current version**:
   ```bash
   hugo version
   ```

2. **Download latest version** from [Hugo releases](https://github.com/gohugoio/hugo/releases)

3. **Test with new version**:
   ```bash
   hugo server -D
   ```

4. **Update deployment configuration** if necessary

#### Updating PaperMod Theme
1. **Navigate to theme directory**:
   ```bash
   cd themes/PaperMod
   ```

2. **Pull latest changes**:
   ```bash
   git pull origin master
   ```

3. **Test for compatibility**:
   ```bash
   hugo server -D
   ```

4. **Review changelog** for breaking changes

### Content Management Workflow

#### Adding New Content
1. **Create content files** in appropriate language directories
2. **Write and review content** for accuracy and style
3. **Translate content** to other languages
4. **Test locally** before publishing
5. **Deploy to production** and verify

#### Updating Existing Content
1. **Identify content** that needs updating
2. **Make changes** in source files
3. **Update translations** accordingly
4. **Test changes** locally
5. **Deploy updates** and monitor for issues

### Backup Strategy

#### What to Backup
- All content files (`content/` directory)
- Configuration files (`config.toml`)
- Custom layouts and partials (`layouts/` directory)
- Custom CSS and assets (`assets/` directory)
- Static files (`static/` directory)

#### Backup Methods
1. **Git Repository**: Use version control for automatic backups
2. **Cloud Storage**: Regular uploads to Google Drive, Dropbox, etc.
3. **Local Backups**: Periodic copies to external drives
4. **Automated Scripts**: Set up scripts for regular backup creation

### Performance Monitoring

#### Key Metrics to Track
- Page load speed
- Time to first byte (TTFB)
- Largest contentful paint (LCP)
- First input delay (FID)
- Cumulative layout shift (CLS)

#### Monitoring Tools
- Google PageSpeed Insights
- GTmetrix
- WebPageTest
- Google Analytics
- Search Console

### Security Considerations

#### Best Practices
1. **Keep software updated**: Hugo, themes, and dependencies
2. **Secure hosting**: Use reputable hosting providers
3. **HTTPS enforcement**: Ensure all traffic uses SSL/TLS
4. **Access control**: Limit who can modify the website
5. **Regular monitoring**: Watch for unusual activity or changes

## Troubleshooting

Common issues and their solutions when working with the ChatAt website.

### Build Errors

#### Hugo Version Compatibility
**Problem**: Site fails to build with newer Hugo versions
**Solution**:
1. Check Hugo version requirements in theme documentation
2. Update theme to latest version
3. Use Hugo Extended version if required
4. Pin specific Hugo version in deployment configuration

#### Theme Not Found
**Problem**: `Error: module "PaperMod" not found`
**Solution**:
1. Verify theme is properly installed in `themes/PaperMod/`
2. Check theme name in `config.toml` matches directory name
3. Ensure theme files are not corrupted
4. Re-clone theme if necessary

#### Content Rendering Issues
**Problem**: Content not displaying correctly
**Solution**:
1. Check front matter syntax for errors
2. Verify file encoding (should be UTF-8)
3. Ensure proper markdown syntax
4. Check for special characters causing issues

### Multilingual Issues

#### Language Switching Not Working
**Problem**: Language switcher doesn't appear or work
**Solution**:
1. Verify content exists in both language directories
2. Check language configuration in `config.toml`
3. Ensure proper file naming conventions
4. Test language switcher partial template

#### RTL Layout Problems
**Problem**: Arabic text not displaying right-to-left
**Solution**:
1. Verify `rtl = true` in Arabic language configuration
2. Check custom CSS for RTL-specific styles
3. Test with different browsers
4. Ensure proper HTML `dir` attribute

#### Translation Linking Issues
**Problem**: Translated pages not properly linked
**Solution**:
1. Ensure matching file names across languages
2. Check content directory structure
3. Verify language codes in configuration
4. Test with `hugo server -D` locally

### Deployment Issues

#### GitHub Pages Build Failures
**Problem**: GitHub Actions workflow fails
**Solution**:
1. Check Hugo version in workflow file
2. Verify repository permissions
3. Review build logs for specific errors
4. Ensure all required files are committed

#### Netlify Form Not Working
**Problem**: Contact form submissions not received
**Solution**:
1. Verify `data-netlify="true"` attribute
2. Check form name attribute
3. Enable form detection in Netlify settings
4. Test form after deployment (not locally)

#### Custom Domain Issues
**Problem**: Custom domain not working properly
**Solution**:
1. Verify DNS configuration
2. Check domain propagation status
3. Ensure SSL certificate is active
4. Update `baseURL` in configuration

### Performance Issues

#### Slow Loading Times
**Problem**: Website loads slowly
**Solution**:
1. Optimize images (compress and resize)
2. Minify CSS and JavaScript
3. Enable caching headers
4. Use CDN for static assets
5. Review and optimize custom CSS

#### Large Bundle Sizes
**Problem**: Generated site is too large
**Solution**:
1. Remove unused theme files
2. Optimize images and media files
3. Clean up unnecessary CSS
4. Use Hugo's built-in minification

### Browser Compatibility

#### CSS Not Working in Older Browsers
**Problem**: Styling appears broken in some browsers
**Solution**:
1. Add vendor prefixes for CSS properties
2. Use fallbacks for modern CSS features
3. Test with browser compatibility tools
4. Consider progressive enhancement approach

#### Font Loading Issues
**Problem**: Custom fonts not loading properly
**Solution**:
1. Check font file paths and formats
2. Add font-display: swap for better performance
3. Provide fallback fonts
4. Test font loading across different connections

### Content Issues

#### Special Characters Not Displaying
**Problem**: Arabic or special characters appear as boxes
**Solution**:
1. Ensure UTF-8 encoding for all files
2. Check font support for character sets
3. Verify proper HTML meta charset declaration
4. Test with different fonts

#### Search Not Working
**Problem**: Site search returns no results
**Solution**:
1. Verify search index generation
2. Check JavaScript console for errors
3. Ensure search data is properly formatted
4. Test search functionality locally

## Contributing

We welcome contributions to improve the ChatAt website project. Here's how you can help:

### Ways to Contribute

1. **Bug Reports**: Report issues you encounter
2. **Feature Requests**: Suggest new functionality
3. **Documentation**: Improve or expand documentation
4. **Code Contributions**: Submit bug fixes or enhancements
5. **Translations**: Help with additional language support
6. **Design Improvements**: Suggest UI/UX enhancements

### Contribution Guidelines

#### Before Contributing
1. Check existing issues and pull requests
2. Discuss major changes in an issue first
3. Follow the project's coding standards
4. Test your changes thoroughly

#### Submitting Changes
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request with clear description

#### Code Standards
- Use consistent indentation (2 spaces)
- Follow semantic HTML practices
- Write clear, commented CSS
- Test across multiple browsers
- Ensure accessibility compliance

### Development Setup

1. **Fork and clone** the repository
2. **Install dependencies** (Hugo, Git)
3. **Create feature branch** for your changes
4. **Test locally** with `hugo server -D`
5. **Submit pull request** when ready

### Community Guidelines

- Be respectful and inclusive
- Provide constructive feedback
- Help others learn and grow
- Follow the code of conduct
- Maintain professional communication

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

### MIT License Summary

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software.

### Third-Party Licenses

- **Hugo**: Apache License 2.0
- **PaperMod Theme**: MIT License
- **Google Fonts**: SIL Open Font License
- **Font Awesome** (if used): Font Awesome Free License

---

## Support

If you need help with the ChatAt website:

1. **Check this documentation** first
2. **Search existing issues** on GitHub
3. **Create a new issue** with detailed information
4. **Join community discussions** for general questions
5. **Contact maintainers** for urgent issues

### Getting Help

- **Documentation**: This README file
- **Issues**: GitHub Issues page
- **Discussions**: GitHub Discussions
- **Email**: Contact form on the website

Thank you for using ChatAt! We hope this documentation helps you create a beautiful, multilingual website that serves your community well.

---

*Last updated: July 19, 2025*
*Version: 1.0.0*


# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

### Local Development
```bash
# Install Ruby dependencies
bundle install

# Run local development server (auto-reloads on changes)
bundle exec jekyll serve

# Build site for production
bundle exec jekyll build

# Clean build artifacts
bundle exec jekyll clean
```

### Content Management
```bash
# Create new blog post (manual process)
# File format: _posts/YYYY-MM-DD-title.md
# Images go in: assets/img/YYYY-MM-DD-title/

# Test site locally before committing
bundle exec jekyll serve --livereload
```

## Architecture Overview

This is a **Jekyll-based personal blog** using the **Beautiful Jekyll theme** (v6.0.1) with GitHub Pages hosting. The architecture follows Jekyll's convention-over-configuration approach with minimal custom code.

### Core Structure
- **Theme-based**: Inherits most functionality from Beautiful Jekyll gem
- **Content-driven**: Focus on Markdown posts with YAML front matter
- **Bootstrap 4**: Responsive CSS framework via CDN
- **GitHub Pages**: Automated build and deployment pipeline

### Key File Relationships

**Layout Hierarchy:**
```
_layouts/base.html (root template with Bootstrap, common assets)
├── home.html (paginated blog listing)
├── post.html (individual blog posts with navigation)
├── page.html (static pages like About Me)
└── minimal.html (clean layout without header/footer)
```

**Content Flow:**
- `_posts/*.md` → processed by Jekyll → uses `post.html` layout → inherits from `base.html`
- `index.html` uses `home.html` layout to display paginated post list
- `_includes/` contains reusable components (nav, footer, analytics, etc.)

### Asset Organization
- **CSS**: Theme CSS + Bootstrap via CDN with performance optimizations
- **JavaScript**: Minimal JS (jQuery, Bootstrap) with `defer` attributes
- **Images**: Organized by post date in `/assets/img/YYYY-MM-DD-post-title/`
- **Performance**: DNS prefetch, async font loading, resource hints implemented

## Configuration Patterns

### Theme Customization (_config.yml)
- **Navigation**: Custom navbar links defined in `navbar-links`
- **Colors**: Full color scheme customization (page-col, text-col, etc.)
- **Social**: Social network links for footer (currently email + GitHub + RSS)
- **Features**: Post search, tag support, RSS feed, edit buttons enabled

### Post Front Matter Structure
```yaml
---
layout: post
title: "Required Title"
subtitle: "Optional subtitle"
tags: [tag1, tag2]  # Used for tag index page
cover-img: "/assets/img/path/to/image.jpg"  # Optional
comments: true  # Enables comment system (if configured)
---
```

### Content Patterns
- **Weekly posts**: "Weekly What's Up" series with reading/watching/playing sections
- **Trip reports**: Outdoor activity posts with photo galleries
- **Technical posts**: Home automation, game reviews, development topics
- **Image naming**: Match post date format for organization

## Deployment Architecture

### GitHub Actions Workflow
- **Trigger**: Push to master branch
- **Build**: Ruby 3.3, Jekyll in production mode
- **Deploy**: Automatic GitHub Pages deployment
- **Domain**: Custom domain `jlbrooks.tech` via CNAME

### Performance Optimizations
- **External resources**: Bootstrap, Font Awesome, Google Fonts via CDN
- **Async loading**: Fonts and icons load asynchronously to prevent render blocking
- **Resource hints**: DNS prefetch and preconnect for external CDNs
- **Deferred JS**: All JavaScript loads with defer attribute

## Theme Integration Points

### Beautiful Jekyll Theme Features
- **Responsive design**: Mobile-first Bootstrap layout
- **Blog functionality**: Post listing, pagination, tags, search
- **Social integration**: Configurable social media links
- **SEO optimized**: Meta tags, RSS feed, sitemap
- **Comment systems**: Support for multiple providers (currently disabled)

### Customization Areas
- **`_config.yml`**: Primary configuration file for theme settings
- **`assets/css/`**: Additional CSS files for custom styling
- **`_includes/`**: Override theme includes for custom functionality
- **Performance**: Recent optimizations for render-blocking resources

## Content Management

### Blog Post Workflow
1. Create `_posts/YYYY-MM-DD-title.md` with proper front matter
   - **IMPORTANT**: Date format must use zero-padded months and days (e.g., `2026-01-02`, NOT `2026-1-2`)
2. Add images to `assets/img/YYYY-MM-DD-title/` directory
3. Test locally with `bundle exec jekyll serve`
4. Commit and push to trigger automatic deployment

### Linking
- **Internal links** (posts, pages): use the `relative_url` filter: `[link text]({{ '/2026-02-21-idaho-ski-trip/' | relative_url }})`
- **Images**: use `{{site.url}}` prefix: `<img src="{{site.url}}/assets/img/YYYY-MM-DD-title/image.jpg" />`
- Do NOT use bare paths or `{{site.url}}` for post/page links

### Static Pages
- Created as `.md` files in repository root
- Use `page` layout by default
- Configured in `navbar-links` for navigation inclusion

## Development Notes

### Local Testing
- Use `--livereload` flag for automatic browser refresh during development
- Check mobile responsiveness as site uses Bootstrap responsive design
- Test external resource loading after making performance changes

### Theme Dependencies
- Ruby gems managed via `Gemfile` and `beautiful-jekyll-theme.gemspec`
- External CDN resources defined in `_layouts/base.html`
- Theme updates require updating gem version and testing locally

### GitHub Integration
- **Edit buttons**: Link directly to GitHub file editor for post editing
- **Issue integration**: Claude AI responder configured for `@claude` mentions
- **Automation**: Fully automated deployment pipeline via GitHub Actions
# Hugo Mana Theme

A custom Hugo theme inspired by PaperModX and Blowfish, featuring a dark theme by default, clean aesthetics, and modern functionality.

## Features

### Theme & Design
- **Dark theme by default** with light theme toggle
- **System preference detection** with manual override
- **Theme persistence** via localStorage
- **Glassy design** effects throughout
- **Clean, minimal aesthetic** with modern UI patterns
- **Fully responsive** layout (mobile-first approach)
- **Smooth animations** and transitions
- **Custom Google Fonts** integration (Space Grotesk, Inter, Outfit, JetBrains Mono)

### Navigation & Layout
- **Sticky header** navigation that stays visible while scrolling
- **Mobile hamburger menu** (glass dock navigation)
- **Smooth scroll** to anchor links
- **Scroll-to-top button** with visibility detection

### Content Features
- **Table of Contents** (TOC) with auto-expand on desktop, collapsible on mobile
- **Active TOC highlighting** that tracks scroll position
- **Post filtering system** by year/month and tags
- **Tag search** with autocomplete and keyboard navigation
- **Tag cloud** visualization
- **Archive pages** with chronological organization
- **Post navigation** (previous/next post links)
- **Post metadata** display (date, tags, reading time)
- **Post images/thumbnails** support

### Code Features
- **Syntax highlighting** with Chroma (Catppuccin themes by default)
- **Theme-aware syntax highlighting** (automatically switches with theme toggle)
- **Code block copy button** with visual feedback (checkmark icon)
- **Collapsible code blocks** with expand/collapse functionality
- **Responsive code blocks** (copy button adapts to screen size)

### Search & Discovery
- **Full-text search modal** with JSON index
- **Search result highlighting** of matching terms
- **Keyboard shortcuts** (Escape to close, Enter to search)
- **Clickaway to close** search modal

### Performance & Optimization
- **Content hashing** (fingerprinting) for cache busting
- **Asset minification** and bundling
- **Optimized resource loading** with defer attributes
- **RSS feed** support

### Integration & Widgets
- **Buy Me a Coffee** floating widget (configurable)
- **Social links** integration (GitHub, LinkedIn, Email)
- **Avatar support** for home and about pages
- **SEO meta tags** (description, keywords, author, canonical)
- **Favicon support** with multiple sizes and formats

## Installation

This theme is installed as a Git submodule. To add it to your Hugo site:

```bash
git submodule add https://github.com/Livour/hugo-mana-theme.git themes/mana
```

Then set `theme = "mana"` in your `hugo.toml` configuration file.

## Requirements

- Hugo Extended version 0.100.0 or higher (required for PostCSS support)

## Configuration

Add the following configuration to your `hugo.toml` file:

### Basic Configuration

```toml
[params]
  description = "Your site description"
  favicon = "/favicon/favicon.ico"
  footerText = "Built with Hugo and Mana theme"  # Optional
  
  # Hero section title (optional - defaults to site.Title)
  heroTitleLine1 = "Your Site Name"  # First line of hero title
  heroTitleLine2 = "Your Tagline"    # Second line of hero title (optional)
```

### Avatar

Configure your avatar image (displayed on home page and about page):

```toml
[params.avatar]
  url = "https://example.com/avatar.jpg"
```

### Social Links

Add your social media links:

```toml
[params.social]
  github = "https://github.com/yourusername"
  linkedin = "https://www.linkedin.com/in/yourprofile"
  email = "your.email@example.com"
```

### Buy Me a Coffee Widget

Enable the Buy Me a Coffee floating widget:

```toml
[params.buyMeACoffee]
  enabled = true
  id = "yourwidgetid"
  description = "Support me on Buy me a coffee!"
  message = ""  # Optional message
  color = "#BD5FFF"  # Widget color
  position = "Right"  # "Left" or "Right"
  x_margin = "18"  # Horizontal margin in pixels
  y_margin = "18"  # Vertical margin in pixels
```

### Menu Configuration

Configure your site navigation menu:

```toml
[[menus.main]]
  name = 'Home'
  pageRef = '/'
  weight = 10

[[menus.main]]
  name = 'Posts'
  pageRef = '/posts'
  weight = 20

[[menus.main]]
  name = 'Tags'
  pageRef = '/tags'
  weight = 30

[[menus.main]]
  name = 'About'
  url = '/about/'
  weight = 40
```

### Table of Contents

Enable table of contents for posts:

```toml
[markup]
  [markup.tableOfContents]
    startLevel = 1
    endLevel = 6
    ordered = false
```

### Code Syntax Highlighting

The theme supports theme-aware syntax highlighting using Chroma. By default, it uses Catppuccin themes:
- **Dark mode**: `catppuccin-macchiato`
- **Light mode**: `catppuccin-frappe`

Configure the themes in your `hugo.toml`:

```toml
[markup]
  [markup.highlight]
    codeFences = true
    guessSyntax = true
    noClasses = false
    style = "catppuccin-macchiato"  # Default style

[params]
  [params.codeHighlight]
    darkTheme = "catppuccin-macchiato"   # Theme for dark mode
    lightTheme = "catppuccin-frappe"     # Theme for light mode
```

#### Generating Syntax Highlighting CSS

To generate the CSS files for syntax highlighting, run these commands in your project root:

```bash
# Generate dark theme CSS
hugo gen chromastyles --style=catppuccin-macchiato > themes/mana/assets/css/syntax-dark.css

# Generate light theme CSS
hugo gen chromastyles --style=catppuccin-frappe > themes/mana/assets/css/syntax-light.css
```

**Note**: These CSS files are already included in the theme. You only need to regenerate them if you want to use different Chroma styles. You can use any valid Chroma style name (e.g., `github`, `monokai`, `dracula`, etc.).

### Search Index

Enable JSON output for search functionality:

```toml
[outputs]
  home = ["HTML", "JSON"]
```

## Post Frontmatter

The theme supports standard Hugo frontmatter. For post images, add an `image` parameter:

```markdown
---
title: "Your Post Title"
date: 2024-01-01
tags: ["tag1", "tag2"]
image: "/images/your-image.png"
---
```

## Pages

The theme includes layouts for:
- **Home page** - Displays mini about section and recent posts
- **Posts listing** - Shows all posts with filtering
- **Single post** - Individual post view with metadata and table of contents
- **Tags page** - Tag cloud view
- **Individual tag page** - Posts grouped by year for each tag
- **About page** - About page with avatar and social links

## License

MIT


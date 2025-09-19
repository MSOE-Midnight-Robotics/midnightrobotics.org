# Midnight Robotics Official Website

This is the official website for MSOE Midnight Robotics, a student-led combat robotics team at the Milwaukee School of Engineering (MSOE). The site is built with Hugo and uses the Blowfish theme.

## About Midnight Robotics

Founded in 2021, Midnight Robotics is a combat robotics collegiate organization that provides students with hands-on experience in engineering, teamwork, and problem-solving. The team designs, builds, and competes with high-performance battlebots in national competitions.

## Project Overview

This website is built using:

- **Hugo** - Static site generator
- **Blowfish Theme** - A modern, responsive Hugo theme
- **GitHub Pages** - Hosting platform

## Dependencies

### Required Software

- [Hugo Extended](https://gohugo.io/installation/) (v0.112.0 or later)
- [Git](https://git-scm.com/)
- [Node.js](https://nodejs.org/) (optional, for advanced asset processing)

### Theme

- [Blowfish Theme](https://blowfish.page/) - Included as a Git submodule

## File Structure

```
midnightrobotics.org/
├── archetypes/          # Content templates
├── assets/              # Source files for processing
│   └── images/          # Image assets
│       ├── leadership/  # Leadership team photos
│       └── sponsors/    # Sponsor logos
├── config/              # Hugo configuration
│   └── _default/        # Default configuration files
│       ├── hugo.toml    # Main site configuration
│       ├── languages.en.toml  # Language settings
│       ├── markup.toml  # Markdown settings
│       ├── menus.en.toml # Navigation menus
│       └── params.toml  # Theme parameters
├── content/             # Site content
│   ├── _index.md        # Homepage content
│   ├── about.md         # About page
│   └── learn/           # Learning resources section
│       ├── _index.md    # Section index
│       └── combat-robotics.md
├── data/                # Data files
├── layouts/             # Custom layout templates
├── static/              # Static assets (served directly)
│   └── images/          # Static images
├── themes/              # Hugo themes
│   └── blowfish/        # Blowfish theme (submodule)
└── public/              # Generated site (git ignored)
```

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/MSOE-Midnight-Robotics/midnightrobotics.org.git
cd midnightrobotics.org
```

### 2. Initialize Submodules

```bash
git submodule update --init --recursive
```

### 3. Install Hugo

Follow the [Hugo installation guide](https://gohugo.io/installation/) for your operating system.

### 4. Run Development Server

```bash
hugo server -D
```

## Development

### Adding Content

#### Creating a New Page

```bash
hugo new content/page-name.md
```

#### Creating a New Section

```bash
hugo new content/section-name/_index.md
hugo new content/section-name/article-name.md
```

### Configuration

#### Site Settings

- Main configuration: `config/_default/hugo.toml`
- Language settings: `config/_default/languages.en.toml`
- Theme parameters: `config/_default/params.toml`

#### Navigation Menu

Edit `config/_default/menus.en.toml` to add/remove menu items:

```toml
[[main]]
  name = "Page Name"
  pageRef = "page-name"
  weight = 10
```

#### Theme Customization

- Colors and appearance: `config/_default/params.toml`
- Custom CSS: Add to individual page front matter or create custom layouts
- Layout overrides: Add to `layouts/` directory

### Front Matter

All content pages use YAML front matter:

```yaml
+++
date = '2025-09-14T10:00:00-05:00'
draft = false
title = 'Page Title'
type = 'page'           # Optional: page type
layout = 'simple'       # Optional: layout override
+++
```

### Publishing Changes

1. Set `draft = false` in front matter
2. Commit and push changes
3. GitHub Actions will automatically build and deploy

## Building for Production

### Local Build

```bash
hugo --minify
```

### Build with Drafts

```bash
hugo --buildDrafts --minify
```

The generated site will be in the `public/` directory.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

# My Quarto Blog

A personal blog built with [Quarto](https://quarto.org/) and designed to be deployed on GitHub Pages.

## Prerequisites

- [Quarto](https://quarto.org/docs/get-started/) installed on your system
- [Git](https://git-scm.com/) for version control
- A [GitHub](https://github.com) account for hosting

## Local Development

### 1. Install Quarto

Download and install Quarto from [https://quarto.org/docs/get-started/](https://quarto.org/docs/get-started/)

### 2. Clone and Setup

```bash
git clone https://github.com/yourusername/jb_blog_quarto.git
cd jb_blog_quarto
```

### 3. Preview Locally

To preview your blog locally:

```bash
quarto preview
```

This will start a local server and open your blog in a web browser. The preview will automatically reload when you make changes.

### 4. Render the Site

To build the site for production:

```bash
quarto render
```

The rendered site will be in the `_site/` directory.

## Project Structure

```
.
├── _quarto.yml          # Quarto project configuration
├── index.qmd           # Homepage
├── about.qmd           # About page
├── posts/              # Blog posts directory
│   ├── _metadata.yml   # Default settings for all posts
│   └── welcome/        # Example post
│       └── index.qmd
├── styles.css          # Custom CSS (optional)
├── .gitignore         # Git ignore file
└── README.md          # This file
```

## Writing Posts

1. Create a new directory in `posts/` for your post
2. Add an `index.qmd` file with your content
3. Include frontmatter with title, author, date, and other metadata

Example post structure:

```yaml
---
title: "Your Post Title"
author: "Your Name"
date: "2024-01-15"
categories: [category1, category2]
description: "Brief description of your post"
---

Your post content goes here...
```

## Customization

- Edit `_quarto.yml` to change site settings, theme, and navigation
- Modify `index.qmd` to customize the homepage
- Update `about.qmd` with your information
- Add custom CSS in `styles.css` for additional styling

## GitHub Pages Deployment

Coming next! We'll set up automatic deployment to GitHub Pages.

## License

This project is open source and available under the [MIT License](LICENSE).
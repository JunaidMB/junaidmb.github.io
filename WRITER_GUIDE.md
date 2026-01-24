# Writer's Guide to Updating the Quarto Blog

This guide will help you make updates to the blog, even if you're new to Quarto and GitHub Pages. Follow these step-by-step instructions to add content and customize your blog.

## Table of Contents

1. [Getting Started](#getting-started)
2. [Understanding the Blog Structure](#understanding-the-blog-structure)
3. [Adding New Blog Posts](#adding-new-blog-posts)
4. [Adding New Study Notes](#adding-new-study-notes)
5. [Adding New Cheatsheets](#adding-new-cheatsheets)
6. [Adding Images](#adding-images)
7. [Customizing Themes and Styling](#customizing-themes-and-styling)
8. [Publishing Your Changes](#publishing-your-changes)
9. [Troubleshooting](#troubleshooting)

---

## Getting Started

### Prerequisites

Before you begin, make sure you have:

1. **Git** installed on your computer
2. **Quarto** installed ([Download here](https://quarto.org/docs/get-started/))
3. A **text editor** (VS Code, Sublime Text, or any editor you prefer)
4. **Access to the GitHub repository** for this blog

### Cloning the Repository

If you don't have the blog repository on your local machine:

```bash
# Clone the repository
git clone https://github.com/JunaidMB/junaidmb.github.io.git

# Navigate to the project directory
cd junaidmb.github.io
```

---

## Understanding the Blog Structure

Here's how the blog is organized:

```
junaidmb.github.io/
├── index.qmd                 # Homepage (About Me page)
├── blog.qmd                  # Blog listing page
├── study-notes.qmd           # Study Notes listing page
├── cheatsheets.qmd           # Cheatsheets listing page
├── _quarto.yml              # Site configuration
├── styles.css               # Custom styling
├── posts/                   # Blog posts folder
│   ├── _metadata.yml        # Post settings
│   └── welcome/             # Example post folder
│       └── index.qmd        # Post content
├── study-notes/             # Study notes folder
│   ├── _metadata.yml        # Study notes settings
│   ├── machine-learning-basics.qmd
│   └── python-data-structures.qmd
├── cheatsheets/             # Cheatsheets folder
│   ├── _metadata.yml        # Cheatsheet settings
│   ├── git-commands.qmd
│   └── pandas-essentials.qmd
└── .github/workflows/       # Automatic deployment setup
    └── publish.yml
```

### Key Files Explained

- **`.qmd` files**: These are Quarto Markdown files that contain your content
- **`_quarto.yml`**: Controls site-wide settings like navigation, theme, and layout
- **`_metadata.yml`**: Sets default options for content in each folder
- **`styles.css`**: Contains custom CSS for visual styling

---

## Adding New Blog Posts

Blog posts go in the `posts/` directory. Each post should be in its own folder.

### Step 1: Create a New Post Folder

```bash
# Create a new folder for your post (use lowercase with hyphens)
mkdir posts/my-new-post-title
```

### Step 2: Create the Post File

Create an `index.qmd` file in your new folder:

```bash
# Create the post file
touch posts/my-new-post-title/index.qmd
```

### Step 3: Add Post Content

Open `posts/my-new-post-title/index.qmd` and add this template:

```yaml
---
title: "Your Post Title Here"
author: "Junaid Butt"
date: "2024-01-25"
categories: [technology, tutorial, python]  # Add relevant categories
image: "thumbnail.jpg"  # Optional: add if you have a featured image
description: "A brief description of your post for SEO and previews."
---

# Your Post Title

Your introduction paragraph goes here.

## Section 1

Your content goes here. You can use:

- **Bold text**
- *Italic text*
- [Links](https://example.com)
- Code snippets

### Code Examples

```python
# Python code example
def hello_world():
    print("Hello, World!")

hello_world()
```

### Lists and Tables

You can create lists:

1. First item
2. Second item
3. Third item

And tables:

| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Value 1  | Value 2  | Value 3  |
| Value 4  | Value 5  | Value 6  |

## Conclusion

Wrap up your post here.
```

### Step 4: Preview Your Post

Before publishing, preview your post locally:

```bash
# From the root directory, start the preview server
quarto preview

# Or render the specific post
quarto render posts/my-new-post-title/index.qmd
```

---

## Adding New Study Notes

Study notes work similarly to blog posts but go in the `study-notes/` directory.

### Step 1: Create the Study Note File

```bash
# Create a new study note file
touch study-notes/new-topic-name.qmd
```

### Step 2: Add Study Note Content

Use this template for study notes:

```yaml
---
title: "Topic Name - Study Notes"
author: "Junaid Butt"
date: "2024-01-25"
categories: [study-notes, topic-category]
description: "Comprehensive notes on [topic name]."
---

# Topic Name - Study Notes

## Overview

Brief overview of the topic.

## Key Concepts

### Concept 1
Explanation and examples.

### Concept 2
More detailed information.

## Practical Examples

```language
// Code examples relevant to the topic
function example() {
    return "This is an example";
}
```

## Important Notes

- Key point 1
- Key point 2
- Key point 3

## References

- [Link to resource 1](https://example.com)
- [Link to resource 2](https://example.com)

---

*Last updated: [Date]*
```

---

## Adding New Cheatsheets

Cheatsheets are quick reference guides that go in the `cheatsheets/` directory.

### Step 1: Create the Cheatsheet File

```bash
# Create a new cheatsheet file
touch cheatsheets/tool-or-language-name.qmd
```

### Step 2: Add Cheatsheet Content

Use this template for cheatsheets:

```yaml
---
title: "Tool/Language Cheatsheet"
author: "Junaid Butt"
date: "2024-01-25"
categories: [cheatsheet, tool-name]
description: "Quick reference guide for [tool/language name]."
---

# Tool/Language Cheatsheet

## Basic Commands

```bash
# Command 1: Description
command --option

# Command 2: Description
another-command -flag value
```

## Advanced Usage

```language
// More complex examples
function advancedExample() {
    // Code here
}
```

## Common Patterns

| Task | Command/Code | Notes |
|------|--------------|-------|
| Task 1 | `command1` | When to use |
| Task 2 | `command2` | When to use |

## Tips and Tricks

- **Tip 1**: Explanation
- **Tip 2**: Explanation
- **Tip 3**: Explanation

---

*Last updated: [Date]*
```

---

## Adding Images

### Step 1: Create an Images Folder

For better organization, create an `images/` folder in your post directory:

```bash
# For blog posts
mkdir posts/my-post/images

# For study notes (create a general images folder)
mkdir images
```

### Step 2: Add Your Images

Copy your image files (PNG, JPG, GIF) to the appropriate folder:

```bash
# Copy image to post folder
cp /path/to/your/image.png posts/my-post/images/

# For study notes or cheatsheets
cp /path/to/your/image.png images/
```

### Step 3: Reference Images in Your Content

Use these formats to include images:

```markdown
# Basic image
![Alt text description](images/your-image.png)

# Image with caption
![Alt text description](images/your-image.png)
*Figure 1: Your image caption here*

# Image with custom size
![Alt text description](images/your-image.png){width=50%}

# Centered image
::: {.text-center}
![Alt text description](images/your-image.png)
:::
```

### Step 4: Featured Images

For blog posts, you can set a featured image in the frontmatter:

```yaml
---
title: "Your Post Title"
image: "images/featured-image.jpg"
# ... other frontmatter
---
```

### Image Best Practices

1. **Use descriptive filenames**: `machine-learning-workflow.png` instead of `img1.png`
2. **Optimize image sizes**: Keep images under 1MB when possible
3. **Use appropriate formats**:
   - PNG for screenshots and diagrams
   - JPG for photos
   - GIF for animations
4. **Add alt text**: Always describe what's in the image for accessibility

---

## Customizing Themes and Styling

### Basic Theme Changes

The main configuration is in `_quarto.yml`:

```yaml
format:
  html:
    theme: cosmo  # Try: flatly, minty, pulse, sandstone, spacelab, united
    css: styles.css
    toc: true
    code-copy: true
    code-overflow: wrap
```

### Available Built-in Themes

Popular Quarto themes you can try:
- `cosmo` (current)
- `flatly`
- `minty`
- `pulse`
- `sandstone`
- `spacelab`
- `united`
- `yeti`

To change the theme, edit `_quarto.yml` and replace `theme: cosmo` with your preferred theme.

### Custom CSS Modifications

Edit `styles.css` to customize colors, fonts, and layout:

#### Changing Colors

```css
:root {
  --purple-primary: #5A4A62;    /* Main purple color */
  --purple-light: #6B5B73;      /* Lighter shade */
  --purple-dark: #443540;       /* Darker shade */
}

/* To change to a different color scheme, update these variables */
:root {
  --primary-color: #your-color;
  --light-color: #your-light-color;
  --dark-color: #your-dark-color;
}

/* Then update the navbar */
.navbar {
  background: linear-gradient(135deg, var(--primary-color) 0%, var(--light-color) 100%);
}
```

#### Changing Fonts

```css
/* Add to styles.css */
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap');

body {
  font-family: 'Inter', sans-serif;
}

h1, h2, h3, h4, h5, h6 {
  font-family: 'Inter', sans-serif;
  font-weight: 600;
}
```

#### Customizing the Navigation

Edit `_quarto.yml` to modify navigation:

```yaml
website:
  navbar:
    left:
      - href: index.qmd
        text: About Me
      - href: blog.qmd
        text: Blog
      - href: study-notes.qmd
        text: Study Notes
      - href: cheatsheets.qmd
        text: Cheatsheets
      - href: new-page.qmd        # Add new pages here
        text: New Page
    right:
      - icon: github
        href: https://github.com/JunaidMB
      - icon: linkedin
        href: https://linkedin.com/in/your-profile
      - icon: twitter             # Add new social links
        href: https://twitter.com/your-handle
```

---

## Publishing Your Changes

### Step 1: Preview Locally

Always preview your changes before publishing:

```bash
# Start the preview server
quarto preview

# This will open http://localhost:4444 in your browser
```

### Step 2: Commit Your Changes

```bash
# Add all changes
git add .

# Commit with a descriptive message
git commit -m "Add new blog post about machine learning"

# Or for multiple changes
git commit -m "
- Add new study notes on Python decorators
- Update cheatsheet for Docker commands
- Fix typo in about page
"
```

### Step 3: Push to GitHub

```bash
# Push to the main branch
git push origin main
```

### Step 4: Automatic Deployment

The blog will automatically update within 2-3 minutes thanks to GitHub Actions. You can monitor the deployment at:
`https://github.com/JunaidMB/junaidmb.github.io/actions`

---

## Troubleshooting

### Common Issues and Solutions

#### 1. Preview Not Working

**Problem**: `quarto preview` shows errors
**Solution**:
- Check for syntax errors in your `.qmd` files
- Make sure all image paths are correct
- Verify your YAML frontmatter is properly formatted

#### 2. Images Not Displaying

**Problem**: Images don't show up on the website
**Solutions**:
- Check file paths are correct (case-sensitive!)
- Make sure images are in the right folder
- Verify image files are actually committed to git

#### 3. Site Not Updating After Push

**Problem**: Changes don't appear on the live site
**Solutions**:
- Check GitHub Actions status for build errors
- Wait 2-3 minutes for deployment
- Clear your browser cache (Ctrl+F5 or Cmd+Shift+R)

#### 4. Formatting Issues

**Problem**: Content doesn't look right
**Solutions**:
- Check YAML frontmatter syntax
- Verify Markdown formatting
- Test with `quarto render` locally

#### 5. Build Failures

**Problem**: GitHub Actions build fails
**Solutions**:
- Check the Actions tab on GitHub for error details
- Common issues:
  - Missing images referenced in posts
  - Invalid YAML frontmatter
  - Broken links

### Getting Help

If you run into issues:

1. **Check the error message** - it usually tells you what's wrong
2. **Search the [Quarto documentation](https://quarto.org/docs/)**
3. **Look at existing posts** for examples of working code
4. **Test locally first** with `quarto preview`

### Useful Commands Reference

```bash
# Preview the entire site
quarto preview

# Render the entire site
quarto render

# Render a specific file
quarto render posts/my-post/index.qmd

# Check Git status
git status

# See what changed
git diff

# View commit history
git log --oneline

# Undo uncommitted changes
git checkout -- filename.qmd
```

---

## Quick Start Checklist

For adding new content, use this checklist:

### New Blog Post
- [ ] Create folder in `posts/`
- [ ] Add `index.qmd` with proper frontmatter
- [ ] Write content using Markdown
- [ ] Add images to `images/` subfolder if needed
- [ ] Preview locally with `quarto preview`
- [ ] Commit and push changes

### New Study Note
- [ ] Create `.qmd` file in `study-notes/`
- [ ] Add frontmatter with categories
- [ ] Write comprehensive notes
- [ ] Preview locally
- [ ] Commit and push

### New Cheatsheet
- [ ] Create `.qmd` file in `cheatsheets/`
- [ ] Use cheatsheet template
- [ ] Include code examples and tables
- [ ] Preview locally
- [ ] Commit and push

---

## Final Tips

1. **Start Simple**: Begin with basic posts and gradually add more complex features
2. **Preview Everything**: Always use `quarto preview` before publishing
3. **Be Consistent**: Use the same format and style across all your content
4. **Organize Well**: Use clear folder names and file structures
5. **Version Control**: Commit often with descriptive messages
6. **Backup Important Work**: Keep local copies of important content

Happy blogging! 🎉
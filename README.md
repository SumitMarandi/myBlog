# myBlog

A modern, responsive Jekyll blog designed for GitHub Pages with highly customizable CSS styling. Built with dark theme aesthetics and developer-friendly features.

## 📁 Project Structure

```
myBlog/
├── _config.yml                           # Jekyll configuration
├── _layouts/                              # Template layouts
│   ├── default.html                       # Base HTML template
│   └── post.html                          # Blog post template
├── _posts/                                # Blog posts directory
│   └── 2025-10-02-welcome-to-myblog.md   # Sample blog post
├── assets/                                # Static assets
│   └── css/
│       └── style.css                      # Main stylesheet with CSS variables
├── index.md                               # Homepage (lists all posts)
├── about.md                               # About page
├── Gemfile                                # Ruby gem dependencies
├── README.md                              # This documentation
└── .gitignore                             # Git ignore rules
```

## ✨ Features

- **GitHub Pages Ready**: Zero-config deployment to GitHub Pages
- **SEO Optimized**: Built-in SEO tags and meta information
- **Responsive Design**: Mobile-first responsive layout
- **Dark Theme**: Modern dark theme with customizable CSS variables
- **RSS Feed**: Automatic RSS/Atom feed generation
- **Fast Loading**: Optimized CSS and minimal JavaScript
- **Markdown Support**: Full Markdown support with syntax highlighting
- **Sticky Navigation**: Smooth sticky header with backdrop blur

## 🚀 Quick Start

### Prerequisites

- **Ruby** (2.7 or higher)
- **Bundler** gem
- **Git** (for deployment)

### Local Development

1. **Install dependencies:**
   ```bash
   bundle install
   ```

2. **Start the development server:**
   ```bash
   bundle exec jekyll serve --livereload
   ```

3. **View your site:**
   - Open http://127.0.0.1:4000/myBlog/ in your browser
   - The site will automatically reload when you make changes

### Alternative Development Commands

```bash
# Serve without livereload
bundle exec jekyll serve

# Build the site (generates _site/ folder)
bundle exec jekyll build

# Clean build artifacts
bundle exec jekyll clean

# Serve with drafts included
bundle exec jekyll serve --drafts
```

## 🌐 Deploying to GitHub Pages

### Option 1: Project Site (Recommended)

1. **Create a GitHub repository** named `myBlog`
2. **Update configuration** in `_config.yml`:
   ```yaml
   url: "https://sumitmarandi.github.io"
   baseurl: "/myBlog"
   ```
3. **Push your code:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/sumitmarandi/myBlog.git
   git push -u origin main
   ```
4. **Enable GitHub Pages:**
   - Go to repository Settings → Pages
   - Select "Deploy from a branch"
   - Choose "main" branch
   - Your site will be available at `https://sumitmarandi.github.io/myBlog/`

### Option 2: User/Organization Site

1. **Create a repository** named `sumitmarandi.github.io`
2. **Update configuration** in `_config.yml`:
   ```yaml
   url: "https://sumitmarandi.github.io"
   baseurl: ""
   ```
3. **Deploy** following the same git commands above
4. **Your site** will be available at `https://sumitmarandi.github.io/`

## ✍️ Writing Posts

### Creating a New Post

1. **Create a new file** in `_posts/` directory
2. **Use the naming convention:** `YYYY-MM-DD-title.md`
3. **Add front matter:**
   ```markdown
   ---
   layout: post
   title: "Your Post Title"
   author: "Your Name"  # Optional
   ---
   
   Your post content here...
   ```

### Example Post Structure

```markdown
---
layout: post
title: "Getting Started with Jekyll"
author: "John Doe"
date: 2025-10-02 14:30:00 +0000
---

# Introduction

This is my first Jekyll post!

## Code Example

```python
print("Hello, Jekyll!")
```

## 🎨 Customizing Styles
```

### CSS Variables Approach

The theme uses CSS custom properties (variables) for easy customization. Edit `assets/css/style.css`:

```css
:root {
  /* Color scheme */
  --bg: #0b0f19;          /* Background color */
  --text: #e6e6e6;        /* Primary text color */
  --muted: #a1a1aa;       /* Muted text color */
  --primary: #7c3aed;     /* Primary accent color */
  --link: #60a5fa;        /* Link color */
  --card-bg: #111827;     /* Card background */
  --border: #1f2937;      /* Border color */
  
  /* Layout */
  --radius: 12px;         /* Border radius */
  --max-w: 820px;         /* Max content width */
}
```

### Popular Theme Variations

**Light Theme:**
```css
:root {
  --bg: #ffffff;
  --text: #1f2937;
  --muted: #6b7280;
  --card-bg: #f9fafb;
  --border: #e5e7eb;
}
```

**Green Accent:**
```css
:root {
  --primary: #10b981;
  --link: #34d399;
}
```

**Purple Accent:**
```css
:root {
  --primary: #8b5cf6;
  --link: #a78bfa;
}
```

## ⚙️ Configuration

### Site Configuration (`_config.yml`)

```yaml
# Site settings
title: myBlog
email: your-email@example.com
description: A simple Jekyll blog powered by GitHub Pages
url: "https://sumitmarandi.github.io"
baseurl: "/myBlog"

# Author information
author:
  name: Your Name
  url: https://sumitmarandi.github.io
  email: your-email@example.com

# Build settings
markdown: kramdown
permalink: /:categories/:year/:month/:day/:title/
plugins:
  - jekyll-feed
  - jekyll-seo-tag
```

### Important Configuration Notes

- **baseurl**: Use `/myBlog` for project sites, empty `""` for user sites
- **url**: Your GitHub Pages domain
- **permalink**: Controls URL structure for posts
- **plugins**: Only GitHub Pages-compatible plugins included

## 🔧 Troubleshooting

### Common Issues

**Bundle install fails:**
```bash
# Update RubyGems
gem update --system

# Install bundler
gem install bundler
```

**Jekyll serve fails:**
```bash
# Clean and reinstall
bundle exec jekyll clean
bundle install
bundle exec jekyll serve
```

**GitHub Pages build fails:**
- Check that all plugins are GitHub Pages compatible
- Ensure `_config.yml` syntax is valid
- Check repository Settings → Pages for error details

**Styles not loading:**
- Verify `baseurl` setting matches your site structure
- Check browser developer tools for 404 errors
- Ensure `assets/css/style.css` exists

## 📝 Adding Pages

Create new pages by adding Markdown files to the root directory:

```markdown
---
layout: default
title: Contact
permalink: /contact/
---

# Contact Me

Your contact information here...
```

Then add navigation links in `_layouts/default.html`:

```html
<nav class="site-nav">
  <a href="{{ "/" | relative_url }}">Home</a>
  <a href="{{ "/about/" | relative_url }}">About</a>
  <a href="{{ "/contact/" | relative_url }}">Contact</a>
</nav>
```

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🆘 Support

For questions and support:
- Check the [Jekyll documentation](https://jekyllrb.com/docs/)
- Review [GitHub Pages documentation](https://docs.github.com/en/pages)
- Open an issue in this repository

---

**Happy blogging! 🎉**

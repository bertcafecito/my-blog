# My Blog

A personal blog built with [Hugo](https://gohugo.io/) and the [Terminal theme](https://github.com/panr/hugo-theme-terminal).

## 🚀 Quick Start

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) (v0.152.2 or later)
- [Git](https://git-scm.com/)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/bertcafecito/my-blog.git
cd my-blog
```

2. Initialize and update the theme submodule:
```bash
git submodule update --init --recursive
```

3. Start the development server:
```bash
hugo server --buildDrafts
```

4. Open your browser and visit `http://localhost:1313`

## 📝 Creating New Posts

Create a new post using the Hugo CLI:

```bash
hugo new content posts/my-post-title.md
```

This will create a new post in `content/posts/` with the default front matter. Edit the file and set `draft: false` when ready to publish.

### Scheduling Posts

To schedule a post for future publication, add a `publishDate` field in the post's front matter:

```yaml
---
title: "My Scheduled Post"
date: 2025-12-18T10:00:00-05:00
draft: false
publishDate: 2025-12-25T09:00:00-05:00  # Post will publish on this date
---
```

The post will automatically be published when the daily GitHub Actions workflow runs (at 2 AM EST). You can also manually trigger the workflow from the Actions tab to publish immediately.

**Note:** Set `draft: false` and add a future `publishDate`. The site is configured with `buildFuture = false` to prevent future-dated posts from appearing until their scheduled time.

## 🎨 Theme Configuration

This blog uses the Terminal theme with the following configuration (in `hugo.toml`):

- **Theme Color**: Orange
- **Content Type**: Posts
- **Menu Items**: 2 visible items

To customize the theme, edit the `[params]` section in `hugo.toml`.

## 🏗️ Building for Production

Build the static site:

```bash
hugo --minify
```

The generated files will be in the `public/` directory.

## 🚢 Deployment

This blog is configured for automatic deployment to GitHub Pages using GitHub Actions. The workflow:

- Triggers on push to the `main` branch
- Runs daily at 2 AM EST to publish scheduled posts
- Can be triggered manually via workflow dispatch

The workflow configuration is in `.github/workflows/hugo.yaml`.

## 📁 Project Structure

```
.
├── archetypes/       # Content templates
├── content/          # Blog posts and pages
│   └── posts/        # Blog posts
├── layouts/          # Custom layouts
├── static/           # Static files (images, etc.)
├── themes/           # Hugo themes
│   └── terminal/     # Terminal theme (submodule)
├── hugo.toml         # Hugo configuration
└── public/           # Generated site (gitignored)
```

## ⚙️ Configuration

Key settings in `hugo.toml`:

- `baseURL`: Your site's URL
- `title`: Site title
- `theme`: Active theme (terminal)
- `buildFuture`: Set to `false` to prevent building future-dated posts

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

Feel free to submit issues and pull requests!

## 📚 Resources

- [Hugo Documentation](https://gohugo.io/documentation/)
- [Terminal Theme Documentation](https://github.com/panr/hugo-theme-terminal)
- [Hugo Themes Gallery](https://themes.gohugo.io/)

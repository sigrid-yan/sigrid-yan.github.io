# sigrid-yan.github.io

## 消炎的blog

记录学习C++的日常

---

A personal blog powered by [Hexo](https://hexo.io/) and hosted on GitHub Pages.

## Setup Complete ✅

This blog has been configured with:

- **Hexo** static site generator
- **GitHub Actions** for automatic deployment
- **GitHub Pages** hosting at https://sigrid-yan.github.io

## Local Development

### Install Dependencies

```bash
npm install
```

### Create New Post

```bash
npx hexo new "Post Title"
```

### Generate Static Files

```bash
npx hexo generate
# or
npx hexo g
```

### Run Local Server

```bash
npx hexo server
# or
npx hexo s
```

Visit http://localhost:4000 to preview your blog.

### Clean Generated Files

```bash
npx hexo clean
```

## Deployment

### Automatic Deployment

This blog is configured with GitHub Actions for automatic deployment. Every time you push to the `main` branch:

1. GitHub Actions will automatically run
2. The blog will be built
3. Generated files will be deployed to GitHub Pages

### Manual Push

```bash
git add .
git commit -m "Your commit message"
git push origin main
```

## Configuration

The main configuration file is `_config.yml`. Key settings:

- **Site Info**: Title, subtitle, description, author
- **URL**: https://sigrid-yan.github.io
- **Theme**: landscape (default)
- **Deployment**: Configured for GitHub Pages

## GitHub Pages Settings

After pushing to GitHub, you need to:

1. Go to your repository settings: https://github.com/sigrid-yan/sigrid-yan.github.io/settings/pages
2. Under "Build and deployment":
   - Source: GitHub Actions
3. Your site will be published at: https://sigrid-yan.github.io

## Troubleshooting

### If deployment fails:

1. Check GitHub Actions tab in your repository
2. Verify GitHub Pages is enabled in repository settings
3. Ensure the workflow file is present: `.github/workflows/pages.yml`

### If you can't push to GitHub:

Check your network connection or try using a VPN/proxy. You may need to configure git proxy:

```bash
git config --global http.proxy socks5h://127.0.0.1:7890
git config --global https.proxy socks5h://127.0.0.1:7890
```

## Directory Structure

```
.
├── .github/
│   └── workflows/
│       └── pages.yml          # GitHub Actions workflow
├── scaffolds/                 # Post templates
├── source/
│   └── _posts/               # Your blog posts
├── themes/                    # Hexo themes
├── _config.yml               # Main configuration
├── package.json              # Node.js dependencies
└── README.md                 # This file
```

## Writing Posts

Posts are located in `source/_posts/`. Each post is a Markdown file with front matter:

```markdown
---
title: Post Title
date: 2025-10-09 22:40:00
tags: [tag1, tag2]
categories: Category Name
---

Your content here...
```

## Resources

- [Hexo Documentation](https://hexo.io/docs/)
- [Hexo Themes](https://hexo.io/themes/)
- [Hexo Plugins](https://hexo.io/plugins/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)

---

Built with ❤️ using Hexo and GitHub Pages

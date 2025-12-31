# Personal Blog & Portfolio

Welcome to my personal blog and portfolio site! This is where I share my thoughts, experiences, and projects related to DevOps, software engineering, and technology.

🌐 **Live Site**: [gsantovena.github.io](https://gsantovena.github.io)

## About Me

I'm Gerardo Santoveña, a DevOps Engineer from Guatemala passionate about automation, infrastructure, and building reliable systems. This blog serves as a platform to document my learning journey and share knowledge with the community.

## Technology Stack

This site is built with:

- **Jekyll** - Static site generator
- **Minimal Mistakes** - Beautiful, responsive theme
- **GitHub Pages** - Free hosting and deployment
- **Ruby 3.1** - Programming language
- **GitHub Actions** - Automated CI/CD pipeline

## Local Development

Want to run this site locally or contribute? Here's how:

### Prerequisites

- Ruby 3.1 or higher
- Bundler 2.5+
- Git

### Setup

```bash
# Clone the repository
git clone https://github.com/gsantovena/gsantovena.github.io.git
cd gsantovena.github.io

# Install dependencies
bundle install

# Run the site locally
bundle exec jekyll serve
```

The site will be available at `http://localhost:4000`

### Creating Content

**New Blog Post:**
1. Create a file in `_posts/` with format: `YYYY-MM-DD-title.md`
2. Add front matter (layout, title, tags, excerpt)
3. Write your content in Markdown
4. Preview locally with `bundle exec jekyll serve`
5. Commit and push to deploy automatically

**Example Post:**
```markdown
---
layout: single
title: "My New Post"
tags: [devops, automation]
excerpt: "A brief description of this post"
---

Your content here...
```

## Project Structure

```
├── _posts/          # Blog posts
├── _pages/          # Static pages (About, Resume, etc.)
├── _data/           # Site data (navigation, etc.)
├── _includes/       # Reusable components
├── _config.yml      # Site configuration
├── assets/          # Images, CSS, JS
└── tags/            # Tag archive page
```

## Deployment

The site automatically deploys to GitHub Pages when changes are pushed to the `main` branch. GitHub Actions handles the build and deployment process.

## Features

- 📱 Responsive design
- 🏷️ Tag-based categorization
- 📖 Reading time estimates
- 🔗 Social sharing buttons
- 📧 RSS/Atom feed
- 🎨 Customizable theme (currently using "mint" skin)

## Contributing

While this is a personal blog, I welcome:

- **Bug reports** - Found an issue? Open a GitHub issue
- **Suggestions** - Have ideas for improvement? Let me know!
- **Typo fixes** - Feel free to submit a PR for corrections

## Connect With Me

- 🐦 [Twitter](https://twitter.com/gsantovena)
- 💼 [GitHub](https://github.com/gsantovena)
- 📷 [Instagram](https://instagram.com/gerardosantovena)
- 📘 [Facebook](https://facebook.com/gsantovena)

## License

The content of this project is licensed under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/), and the underlying source code is licensed under the [MIT License](LICENSE).

## Acknowledgments

- Theme by [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/)
- Hosted on [GitHub Pages](https://pages.github.com/)
- Built with [Jekyll](https://jekyllrb.com/)

---

Made with ❤️ in Guatemala

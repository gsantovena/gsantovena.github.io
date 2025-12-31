# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Technology Stack

This is a Jekyll-based static site using the Minimal Mistakes theme, deployed to GitHub Pages. The site serves as a personal blog and portfolio for Gerardo Santoveña.

- **Static Site Generator**: Jekyll 4.3.3
- **Theme**: minimal-mistakes-jekyll
- **Ruby Version**: 3.1 (as specified in GitHub Actions)
- **Bundler Version**: 2.5.23 (compatible with Ruby 3.1)
- **Deployment**: GitHub Pages via GitHub Actions

## Development Commands

### Local Development
```bash
# Install dependencies
bundle install

# Serve the site locally (with auto-reload)
bundle exec jekyll serve

# Build the site for production
bundle exec jekyll build --baseurl ""
```

### Dependency Management
```bash
# Update a specific gem (security patches)
bundle update <gem-name>

# Update all gems (use with caution)
bundle update

# Check for outdated gems
bundle outdated

# Verify bundle integrity
bundle check
```

### Content Management
- Posts are located in `_posts/` directory with YYYY-MM-DD-title.md naming convention
- Pages are in `_pages/` directory
- Navigation is configured in `_data/navigation.yml`
- Site configuration is in `_config.yml`

## Site Architecture

### Key Directories
- `_posts/`: Blog posts with front matter (layout, title, tags, excerpt)
- `_pages/`: Static pages (about.md, resume.md, posts.md, index.md, 404.html)
- `_data/`: Site data files (navigation.yml for menu structure)
- `_includes/`: Reusable template components (_toc.html for table of contents)
- `tags/`: Tag archive page
- `.github/workflows/`: CI/CD configuration for automated deployment

### Content Structure
- Posts use `single` layout with author profile, read time, sharing, and related posts enabled
- Tags are used for categorization and are displayed in the tags archive
- Site uses the "mint" skin variant of Minimal Mistakes theme
- Pagination is set to 5 posts per page

### Deployment
- Automatic deployment to GitHub Pages via `.github/workflows/jekyll.yml`
- Triggers on pushes to `main` branch
- Uses Ruby 3.1 with bundler cache for faster builds
- Builds with `JEKYLL_ENV: production` environment
- Deployment artifacts available at `https://gsantovena.github.io`

### Theme Configuration
- Uses Minimal Mistakes remote theme with extensive customization in `_config.yml`
- Site owner: Gerardo Santoveña (DevOps Engineer from Guatemala)
- Social links configured for Twitter, Facebook, GitHub, Instagram
- Gravatar integration for author profile
- No comments system currently enabled

## Security & Dependencies

### Security-Critical Gems
The following gems have minimum version constraints due to security vulnerabilities:

- **rexml** `>= 3.3.9`: Addresses XML parsing security issues
- **uri** `>= 0.13.3`: Fixes URI parsing vulnerabilities (currently at 1.1.1)

### Core Dependencies
- **jekyll** `~> 4.3.3`: Static site generator
- **minimal-mistakes-jekyll**: Theme framework
- **jekyll-feed** `~> 0.12`: RSS/Atom feed generation

### Platform-Specific Dependencies
- **tzinfo**: Timezone data (Windows/JRuby)
- **wdm**: Directory watching performance booster (Windows)
- **http_parser.rb** `~> 0.6.0`: HTTP parsing (JRuby)

### Utility Gems
- **csv**: CSV parsing support
- **base64**: Base64 encoding/decoding
- **bigdecimal**: Arbitrary-precision decimal arithmetic

## Maintenance & Updates

### Security Updates
When Dependabot alerts are received:
1. Create a feature branch: `git checkout -b fix/<gem>-security-vulnerability`
2. Add/update gem constraint in `Gemfile`
3. Run `bundle update <gem-name>`
4. Verify build: `bundle install`
5. Commit changes with descriptive message
6. Create PR for review
7. Merge after CI/CD validation

### Version Compatibility
- Ruby 3.1 is the target version for GitHub Actions
- Bundler 2.5.23 is locked for Ruby 3.1 compatibility
- All gems should be compatible with Ruby 3.1+

### Testing Before Deployment
```bash
# Local build test
bundle exec jekyll build --baseurl ""

# Local server test
bundle exec jekyll serve

# Check for broken links (if link checker installed)
bundle exec jekyll build && bundle exec htmlproofer ./_site
```

## Git Workflow

### Branch Strategy
- `main`: Production branch, auto-deploys to GitHub Pages
- Feature branches: Use descriptive names like `fix/issue-description` or `feature/feature-name`
- Always create PRs for changes, never commit directly to `main`

### Commit Message Format
Follow the established pattern:
```
<Type>: <Short description>

<Detailed explanation if needed>

🤖 Generated with [Claude Code](https://claude.com/claude-code)

Co-Authored-By: Claude Sonnet 4.5 <noreply@anthropic.com>
```

### Recent Security Fixes
- **2024-12**: Fixed uri gem vulnerability (0.13.2 → 1.1.1)
- **2024-12**: Fixed rexml security vulnerability (→ 3.4.4)
- **2024-12**: Downgraded Bundler to 2.5.23 for Ruby 3.1 compatibility

## Troubleshooting

### Common Issues

**Bundle Install Fails**
- Verify Ruby version: `ruby -v` (should be 3.1+)
- Clear bundle cache: `bundle clean --force`
- Reinstall: `rm -rf vendor/bundle && bundle install`

**Jekyll Serve Errors**
- Check all gems are installed: `bundle check`
- Verify Jekyll version: `bundle exec jekyll -v`
- Clear Jekyll cache: `bundle exec jekyll clean`

**Deployment Failures**
- Check GitHub Actions logs in repository
- Verify `_config.yml` syntax is valid
- Ensure all required gems are in `Gemfile.lock`

**Dependency Conflicts**
- Review `Gemfile.lock` for version mismatches
- Try: `bundle update --conservative <gem-name>`
- Last resort: `rm Gemfile.lock && bundle install`

## Additional Resources

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [Minimal Mistakes Theme Docs](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Bundler Documentation](https://bundler.io/docs.html)

# ZenBlog - Jekyll Site for GitHub Pages

A modern, responsive blog template built with Bootstrap and powered by Jekyll for GitHub Pages.

## Features

- Built with Bootstrap 5
- Responsive design
- Multiple page layouts (Home, About, Contact, Category, Single Post)
- **Dynamic blog posts** - Write posts in Markdown
- **Featured posts slider** - Control which posts appear on homepage
- Easy to customize with Jekyll
- Ready for GitHub Pages deployment

## Local Development

### Option 1: Using Docker (Recommended)

The easiest way to test the site locally without installing Ruby.

**Prerequisites:**
- Docker
- Docker Compose (usually included with Docker Desktop)

**Steps:**

1. Start the Jekyll server:
```bash
docker-compose up
```

2. Open your browser and visit: `http://localhost:4000`

3. The site will automatically reload when you make changes (live reload on port 35729)

4. To stop the server, press `Ctrl+C` or run:
```bash
docker-compose down
```

### Option 2: Using Ruby Directly

**Prerequisites:**
- Ruby 2.7 or higher
- Bundler

**Setup:**

1. Install dependencies:
```bash
bundle install
```

2. Run the Jekyll server:
```bash
bundle exec jekyll serve
```

3. Open your browser and visit: `http://localhost:4000`

## Deployment to GitHub Pages

1. Push your code to a GitHub repository named `username.github.io` (where `username` is your GitHub username)

2. Go to your repository Settings > Pages

3. Under "Source", select the branch you want to deploy (usually `main` or `master`)

4. Click "Save"

5. Your site will be live at `https://username.github.io` within a few minutes

## Configuration

Edit the `_config.yml` file to customize:

- Site title and description
- Social media links
- Contact information
- Navigation menu

## Project Structure

```
.
├── _config.yml          # Jekyll configuration
├── _includes/           # Reusable components (header, footer, post cards)
├── _layouts/            # Page layouts
├── _posts/              # Blog posts (Markdown files)
├── assets/              # CSS, JavaScript, images
├── index.html           # Home page
├── about.html           # About page
├── contact.html         # Contact page
├── category.html        # Category page
├── single-post.html     # Single post page
└── starter-page.html    # Starter page template
```

## Customization

### Adding Blog Posts

**📝 See [HOW-TO-ADD-POSTS.md](HOW-TO-ADD-POSTS.md) for a complete guide on creating blog posts.**

Quick start:
1. Create a file in `_posts/` folder: `YYYY-MM-DD-title.md`
2. Add front matter with title, date, category, etc.
3. Set `featured: true` to show post in homepage slider (max 4 posts)
4. Write content in Markdown

The homepage automatically displays:
- Featured posts in the top slider
- Recent posts in all sections
- Trending posts list

### Changing Colors and Styles

Edit the CSS files in [assets/css/](assets/css/) to customize the appearance.

### Adding New Pages

Create a new HTML file with front matter:

```html
---
layout: default
title: My New Page
body_class: my-page-class
---

<section>
  <!-- Your content here -->
</section>
```

### Modifying Header and Footer

Edit the files in the `_includes` folder:
- [_includes/header.html](_includes/header.html) - Site header and navigation
- [_includes/footer.html](_includes/footer.html) - Site footer

## Credits

- Template: [ZenBlog by BootstrapMade](https://bootstrapmade.com/zenblog-bootstrap-blog-template/)
- Distributed by: [ThemeWagon](https://themewagon.com)
- Converted to Jekyll for GitHub Pages

## License

This template is licensed under BootstrapMade. Please review their [license](https://bootstrapmade.com/license/) for usage terms.

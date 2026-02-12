# How to Add Blog Posts

This guide explains how to add new blog posts to your Jekyll site and control which posts appear in the slider.

## Creating a New Post

### 1. File Naming Convention

Posts must be placed in the `_posts` folder with this naming format:

```
YEAR-MONTH-DAY-title.md
```

**Examples:**
- `2024-01-15-my-first-post.md`
- `2024-02-20-getting-started-with-jekyll.md`

### 2. Post Front Matter

Every post must start with YAML front matter (the content between `---` lines):

```yaml
---
layout: post
title: "Your Post Title Here"
date: 2024-01-15
author: "Your Name"
author_image: "assets/img/person-1.jpg"
category: "Category Name"
featured: true
featured_image: "assets/img/post-slide-1.jpg"
thumbnail: "assets/img/post-landscape-1.jpg"
excerpt: "A brief description of your post that appears in previews."
---
```

### 3. Front Matter Fields Explained

| Field | Required | Description |
|-------|----------|-------------|
| `layout` | Yes | Should always be `post` |
| `title` | Yes | The title of your post |
| `date` | Yes | Publication date (YYYY-MM-DD) |
| `author` | Optional | Author's name |
| `author_image` | Optional | Path to author's profile image |
| `category` | Optional | Post category (e.g., "Culture", "Business", "Lifestyle", "Tech") |
| `featured` | Optional | Set to `true` to show in homepage slider (default: `false`) |
| `featured_image` | Required if featured | Large image for slider background |
| `thumbnail` | Yes | Image shown in post listings |
| `excerpt` | Optional | Brief description (if not provided, Jekyll auto-generates one) |

## Controlling the Homepage Slider

The homepage slider displays **up to 4 featured posts**. To add a post to the slider:

1. Set `featured: true` in the post's front matter
2. Provide a `featured_image` (recommended size: 1920x1080px)

**Example:**

```yaml
---
layout: post
title: "Amazing Post That Should Be Featured"
date: 2024-02-12
category: "Lifestyle"
featured: true
featured_image: "assets/img/my-featured-image.jpg"
thumbnail: "assets/img/my-thumbnail.jpg"
excerpt: "This will appear in the slider!"
---
```

### Slider Rules

- Only posts with `featured: true` appear in the slider
- Maximum of 4 posts are shown (most recent first)
- If you have more than 4 featured posts, only the 4 most recent will display
- The slider automatically updates when you add/remove featured posts

## Writing Post Content

After the front matter, write your content in Markdown:

```markdown
---
layout: post
title: "My Great Post"
date: 2024-02-12
featured: false
thumbnail: "assets/img/my-post.jpg"
---

This is the introduction to my post.

## First Section

Here's some content with **bold text** and *italic text*.

## Second Section

You can add:
- Bullet lists
- Links: [Link text](https://example.com)
- Images: ![Alt text]({{ site.baseurl }}/assets/img/image.jpg)

### Subsection

More content here...
```

## Categories

Available categories (customize as needed):
- Culture
- Business
- Lifestyle
- Tech
- Design
- Travel
- Food
- Sport

## Post Examples

### Regular Post (not featured)

```markdown
---
layout: post
title: "10 Tips for Remote Work"
date: 2024-02-12
author: "Jane Doe"
author_image: "assets/img/person-1.jpg"
category: "Business"
featured: false
thumbnail: "assets/img/remote-work.jpg"
excerpt: "Learn how to be productive while working from home."
---

Your content here...
```

### Featured Post (appears in slider)

```markdown
---
layout: post
title: "The Future of Web Design"
date: 2024-02-12
author: "John Smith"
author_image: "assets/img/person-2.jpg"
category: "Design"
featured: true
featured_image: "assets/img/web-design-hero.jpg"
thumbnail: "assets/img/web-design-thumb.jpg"
excerpt: "Exploring the latest trends in modern web design."
---

Your content here...
```

## Image Guidelines

### Featured Images (for slider)
- **Size:** 1920x1080px or similar 16:9 ratio
- **Format:** JPG or PNG
- **Location:** `assets/img/`
- **Usage:** Background image in homepage slider

### Thumbnails
- **Size:** 800x600px or similar 4:3 ratio
- **Format:** JPG or PNG
- **Location:** `assets/img/`
- **Usage:** Post listings, cards, and previews

### Content Images
- Place in `assets/img/` folder
- Reference with: `![Alt text]({{ site.baseurl }}/assets/img/your-image.jpg)`

## Testing Your Posts

1. **Locally with Docker:**
   ```bash
   docker-compose up
   ```
   Visit `http://localhost:4000`

2. **Locally with Ruby:**
   ```bash
   bundle exec jekyll serve
   ```
   Visit `http://localhost:4000`

3. **On GitHub Pages:**
   Just commit and push your changes. GitHub will automatically build and deploy.

## Tips

- **Post Dates:** Posts with future dates won't be published until that date
- **Drafts:** Create a `_drafts` folder for unpublished posts (no date needed in filename)
- **Permalinks:** Posts are accessible at `/YYYY/MM/DD/title/` by default
- **Updates:** To update a post, just edit the markdown file and save
- **SEO:** Use descriptive titles and excerpts for better search engine visibility

## Dynamic Post Features

The homepage automatically displays:
- ✅ Featured posts in the top slider (up to 4)
- ✅ Most recent posts in the "Trending" section (5 posts)
- ✅ Recent posts in the main content area
- ✅ Posts are sorted by date (newest first)

You don't need to manually update the homepage - it's all automatic!

# SEO Optimization Guide for Agora

This guide explains all the SEO features built into your Jekyll blog to help your articles get discovered by Google News and search engines.

## Overview

Your blog now includes comprehensive SEO optimization with:
- ✅ Open Graph meta tags for social media sharing
- ✅ Twitter Card integration
- ✅ JSON-LD structured data for Google News
- ✅ XML sitemap for search engine crawling
- ✅ RSS/Atom feed for news aggregators
- ✅ Robots.txt for search engine directives
- ✅ Canonical URLs to prevent duplicate content
- ✅ Tag and keyword support

## Post Front Matter Fields

When creating or editing posts in `_posts/`, you can use these SEO-optimized front matter fields:

### Required Fields
```yaml
layout: post
title: "Your Article Title"
date: 2022-03-15
```

### SEO-Specific Fields

#### `description` (Highly Recommended)
Custom meta description for search results (150-160 characters recommended):
```yaml
description: "A compelling summary of your article that will appear in Google search results"
```
If omitted, uses `excerpt` or site description.

#### `tags` (Recommended for Google News)
Array of relevant tags/keywords:
```yaml
tags:
  - Politics
  - Trump
  - Europe
  - International Relations
  - Political Satire
```
These appear in:
- Meta keywords
- Open Graph article tags
- JSON-LD structured data
- RSS feed categories

#### `keywords` (Alternative to tags)
Comma-separated or array format:
```yaml
keywords:
  - Trump Europe relations
  - European diplomacy
  - transatlantic politics
```

#### `image` (Recommended)
Primary image for social media sharing and search results:
```yaml
image: "assets/img/post-landscape-7.jpg"
```
Falls back to `thumbnail` or `featured_image` if not specified.

#### `modified_date` (Optional)
Update date for revised articles:
```yaml
modified_date: 2022-03-16
```
Helps Google understand content freshness.

#### `author` and `author_twitter` (Recommended)
```yaml
author: "Jenny Wilson"
author_twitter: "jennywilson"
```
Included in JSON-LD structured data and Twitter Cards.

#### `category` (Recommended)
Main article category:
```yaml
category: "Politics"
```
Appears in Open Graph and JSON-LD as article section.

### Complete Example

```yaml
---
layout: post
title: "Breaking: Europe Politely Asks Trump to Stay in America"
date: 2022-03-15
modified_date: 2022-03-16
author: "Jenny Wilson"
author_image: "assets/img/person-5.jpg"
author_twitter: "jennywilson"
category: "Politics"
tags:
  - Trump
  - Europe
  - International Relations
  - Political Satire
  - Diplomacy
featured: false
thumbnail: "assets/img/post-landscape-7.jpg"
image: "assets/img/post-landscape-7.jpg"
description: "European leaders unite in unprecedented diplomatic request for Trump to conduct transatlantic relations remotely."
keywords:
  - Trump Europe relations
  - European diplomacy
  - transatlantic politics
excerpt: "In a rare show of unity, all European nations agree on one thing"
---
```

## What Gets Generated

### 1. Open Graph Tags
For Facebook, LinkedIn, and social media sharing:
- `og:type` - "article" for posts
- `og:title` - Article title
- `og:description` - Article description
- `og:image` - Featured image
- `og:url` - Canonical URL
- `article:published_time` - Publication date
- `article:modified_time` - Last update
- `article:author` - Author name
- `article:section` - Category
- `article:tag` - All tags

### 2. Twitter Cards
Optimized previews when shared on Twitter:
- `twitter:card` - "summary_large_image"
- `twitter:title` - Article title
- `twitter:description` - Description
- `twitter:image` - Featured image
- `twitter:creator` - Author Twitter handle

### 3. JSON-LD Structured Data
Google News/Search optimization:
```json
{
  "@context": "https://schema.org",
  "@type": "NewsArticle",
  "headline": "Article title",
  "image": ["featured-image.jpg"],
  "datePublished": "2022-03-15",
  "dateModified": "2022-03-16",
  "author": {...},
  "publisher": {...},
  "description": "Article summary",
  "keywords": "tag1, tag2, tag3"
}
```

### 4. Meta Tags
- Canonical URL (prevents duplicate content)
- Description (for search results)
- Keywords/news_keywords
- Robots directives

## Files Created

### `/sitemap.xml`
XML sitemap listing all pages and posts with:
- URL location
- Last modification date
- Change frequency
- Priority

Automatically submitted via `robots.txt`.

### `/robots.txt`
Instructs search engines:
```
User-agent: *
Allow: /

Sitemap: https://agora-demo.github.io/sitemap.xml
```

### `/feed.xml`
RSS/Atom feed for:
- Google News
- Feed readers (Feedly, etc.)
- News aggregators

Latest 20 articles with full metadata.

## Configuration

In `_config.yml`, you can customize:

```yaml
title: Agora
description: "Your site description for meta tags"
url: "https://agora-demo.github.io"
twitter_username: "agora"
locale: "en_US"
timezone: "America/New_York"
```

## Best Practices for Google News Discovery

1. **Use Descriptive Titles** (50-60 characters)
   - Include primary keywords
   - Make it compelling for clicks

2. **Write Meta Descriptions** (150-160 characters)
   - Summarize the article
   - Include target keywords naturally

3. **Add Relevant Tags** (5-8 tags recommended)
   - Use specific, relevant tags
   - Mix broad and specific terms
   - Include trending topics when relevant

4. **Update Dates**
   - Use `modified_date` when updating articles
   - Google favors fresh content

5. **Choose Good Images**
   - High quality (at least 1200x630px for OG images)
   - Relevant to content
   - Include in `image` field

6. **Write Quality Content**
   - Minimum 300 words for news articles
   - Clear headlines and subheadings
   - Proper formatting with H2/H3 tags

7. **Regular Publishing**
   - Consistent posting schedule
   - Google News prefers active sites

## Verification Tools

After deployment, verify your SEO setup:

1. **Google Search Console**
   - Submit your sitemap
   - Monitor indexing status
   - Check for errors

2. **Facebook Sharing Debugger**
   - Test: https://developers.facebook.com/tools/debug/
   - Verify Open Graph tags

3. **Twitter Card Validator**
   - Test: https://cards-dev.twitter.com/validator
   - Verify Twitter Cards

4. **Rich Results Test**
   - Test: https://search.google.com/test/rich-results
   - Verify structured data

5. **PageSpeed Insights**
   - Test: https://pagespeed.web.dev/
   - Speed affects SEO ranking

## Monitoring Results

Track your SEO performance:
- Google Search Console: impressions, clicks, position
- Google Analytics: organic traffic, bounce rate
- Social media: shares, engagement
- RSS subscriber count

## Troubleshooting

**Images not showing in social shares?**
- Verify `image` path is correct
- Use full URL in structured data (automatically handled)
- Check image size (min 1200x630px recommended)

**Not appearing in Google News?**
- Apply for Google News Publisher Center
- Maintain regular publishing schedule
- Ensure content meets news quality guidelines

**Sitemap errors?**
- Verify `url` in `_config.yml` is correct
- Submit sitemap in Google Search Console
- Check for 404 errors

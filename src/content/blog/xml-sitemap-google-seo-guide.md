---
title: "How to Create and Submit an XML Sitemap for Google SEO (2026 Guide)"
description: "Learn how to create an XML sitemap, submit it to Google Search Console, and improve website crawling and indexing with technical SEO best practices."
author: "cat_squirrel"
date: "2026-07-23"
tags:
  - SEO
  - Technical SEO
  - XML Sitemap
  - Google Search Console

faq:
  - question: "What is an XML sitemap?"
    answer: "An XML sitemap is a file that helps search engines discover important pages on a website and understand its structure."

  - question: "Does submitting a sitemap guarantee Google indexing?"
    answer: "No. A sitemap helps Google discover URLs, but Google decides whether pages should be indexed based on content quality, relevance, and other ranking signals."

  - question: "How do I submit an XML sitemap to Google?"
    answer: "You can submit an XML sitemap through Google Search Console by opening the Sitemaps report and entering your sitemap URL."

  - question: "Do small websites need an XML sitemap?"
    answer: "Yes. XML sitemaps can help search engines discover important pages, especially for new websites."
---

# How to Create and Submit an XML Sitemap for Google SEO (2026 Guide)

The `<loc>` element represents the URL location of a page.

Google uses sitemaps as a discovery signal to better understand website structure.

Official documentation:

https://developers.google.com/search/docs/crawling-indexing/sitemaps/overview


# Why Is an XML Sitemap Important for SEO?

An XML sitemap does not directly improve your Google ranking.

However, it helps search engines discover and crawl your important pages more efficiently.

For new websites, this is especially useful because search engines may not immediately discover every page.


## 1. Help Google Discover New Pages

When you publish a new article, Google needs to discover the URL before indexing it.

A sitemap provides Google with a structured list of important URLs.

Example:
```text
New Article Published
        ↓
Sitemap Updated
        ↓
Google Crawls URL
        ↓
Page May Be Indexed
```
## 2. Improve Website Crawling

Search engines have limited crawling resources.

A sitemap helps Google understand:

- Which pages exist
- Which pages are important
- Which URLs should be crawled

This is especially useful for:

- Large websites
- New websites
- Websites with many pages

## 3. Monitor Indexing Performance

After submitting your sitemap to Google Search Console, you can monitor:

- Submitted URLs
- Indexed pages
- Sitemap errors
- Last crawl time

This helps SEO professionals identify indexing problems.

# XML Sitemap vs robots.txt

Many beginners confuse XML sitemap with robots.txt.

They have different purposes.


| File | Purpose |
| --- | --- |
| XML Sitemap | Helps search engines discover URLs |
| robots.txt | Controls crawler access |

Simply:

Sitemap:
```sitemap
Here are my important pages.

robots.txt:
Here are the pages crawlers can or cannot access.
```
Both are important parts of technical SEO.

# How to Create an XML Sitemap

There are several ways to create a sitemap depending on your website technology.


## Method 1: Generate Sitemap with Astro

Since this blog is built with Astro, I use the official Astro sitemap integration.

Install the sitemap package:

```bash
npm install @astrojs/sitemap

Configure:
```
astro.config.ts
```
```TypeScript
import { defineConfig } from "astro/config";
import sitemap from "@astrojs/sitemap";

export default defineConfig({
  site: "https://zxxhbiii.github.io",

  integrations: [
    sitemap()
  ],
});
```

Then build your website:
```bash
npm run build
```
Astro automatically generates:
```text
sitemap-index.xml
```
My sitemap:
https://zxxhbiii.github.io/sitemap-index.xml

Whenever I publish new content, Astro updates the sitemap automatically.

## Method 2: Use CMS Plugins

For WordPress websites, SEO plugins can automatically generate XML sitemaps.

Popular plugins include:

- Yoast SEO
- Rank Math
- All in One SEO

These tools update sitemaps automatically when new content is published.


## Method 3: Create a Sitemap Manually

For small websites, you can manually create an XML sitemap.

Example:

```xml
<url>
  <loc>
    https://yourwebsite.com/blog/article/
  </loc>
</url>
```

# How to Submit an XML Sitemap to Google Search Console

After creating your sitemap, submit it to Google Search Console.
```text
The process:

Google Search Console

        ↓
Sitemaps
        ↓
Enter sitemap URL
        ↓
Submit
```

For my website:
https://zxxhbiii.github.io/sitemap-index.xml

After submission, Google will show:

- Sitemap status
- Number of discovered URLs
- Last crawl date

# Does Submitting a Sitemap Guarantee Indexing?

No.

A sitemap only helps Google discover your URLs.

It does not guarantee that every page will appear in search results.

Google evaluates factors including:

- Content quality
- Website authority
- Internal linking
- Technical accessibility

A page may still appear as:

```
Crawled - Currently Not Indexed
```

in Google Search Console.

# Common XML Sitemap Problems
## Sitemap Submitted but Pages Are Not Indexed

This is common for new websites.

Possible reasons:

- New domain
- Low website authority
- Thin content
- Weak internal links

Solutions:

- Publish more valuable content
- Improve internal linking
- Optimize search intent
- Build website authority

## Sitemap Contains Invalid URLs

Avoid including:

- 404 pages
- Redirect URLs
- Duplicate pages
- Noindex pages

A clean sitemap helps Google crawl efficiently.

## Sitemap Blocked by robots.txt

Make sure your sitemap is accessible.

Example:
https://yourwebsite.com/robots.txt

Recommended configuration:
```
User-agent: *

Allow: /

Sitemap: https://yourwebsite.com/sitemap-index.xml
```

# XML Sitemap Best Practices
## Only Include Important Pages

A sitemap should contain valuable URLs.

Avoid:

- Login pages
- Duplicate pages
- Temporary pages

## Keep Your Sitemap Updated

Automatic sitemap generation is recommended for modern websites.

Examples:

- Astro
- WordPress
- Next.js

## Use Canonical URLs

Only include the preferred version of a page.

Good:
https://example.com/blog/article/

Avoid:
https://example.com/blog/article/?ref=123

<div class="faq">

## Frequently Asked Questions

### What is an XML sitemap?

An XML sitemap is a file that helps search engines discover important pages on a website.

### Does submitting a sitemap guarantee Google indexing?

No.
A sitemap helps Google discover URLs, but indexing depends on content quality and relevance.

### How do I submit an XML sitemap to Google?

You can submit your sitemap through:
Google Search Console → Sitemaps → Enter sitemap URL → Submit

### Do small websites need an XML sitemap?

Yes.
Even small websites can benefit from helping search engines discover important content.

</div>

# Conclusion

An XML sitemap is a fundamental part of technical SEO.

Although it does not directly improve rankings, it helps search engines discover, crawl, and understand your website structure.

For new websites, setting up:

- XML sitemap
- Google Search Console
- robots.txt
- Internal linking

creates a strong SEO foundation.

By combining technical optimization with high-quality content, websites can gradually improve their visibility in Google Search.
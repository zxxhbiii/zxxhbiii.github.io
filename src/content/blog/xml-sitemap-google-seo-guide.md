---
title: "How to Create and Submit an XML Sitemap for Google SEO (2026 Guide)"
description: "Learn how to create an XML sitemap, submit it to Google Search Console, and improve website crawling and indexing for better SEO performance."
author: "cat_squirrel"
date: "2026-07-23"
tags:
  - SEO
  - Technical SEO
  - XML Sitemap
  - Google Search

faq:
  - question: "What is an XML sitemap?"
    answer: "An XML sitemap is a file that helps search engines discover important pages on a website and understand its structure."

  - question: "Does submitting a sitemap guarantee Google indexing?"
    answer: "No. A sitemap helps Google discover URLs, but Google decides whether pages should be indexed based on content quality, relevance, and other ranking signals."

  - question: "Where should I submit my sitemap?"
    answer: "You can submit your sitemap through Google Search Console under the Sitemaps section."

  - question: "Do small websites need an XML sitemap?"
    answer: "Yes. Although small websites may be easier for Google to crawl, a sitemap can still help search engines discover important pages efficiently."
---

# How to Create and Submit an XML Sitemap for Google SEO (2026 Guide)

Creating a website is only the first step of SEO.

After publishing content, search engines need to discover, crawl, and understand your website structure before your pages can appear in search results.

An XML sitemap is one of the fundamental technical SEO elements that helps search engines discover important URLs on your website.

When I built my SEO blog with Astro and deployed it on GitHub Pages, generating and submitting a sitemap was one of the first technical SEO tasks I completed.

In this guide, I will explain what an XML sitemap is, how to create one, how to submit it to Google Search Console, and common sitemap issues.

---

# What Is an XML Sitemap?

An XML sitemap is a file that lists important URLs on your website.

It provides search engines with information about your website structure and helps crawlers discover pages more efficiently.

A sitemap usually contains:

- Website URLs
- Last modification dates
- Page update frequency
- Page priority information

Example:

```xml
<?xml version="1.0" encoding="UTF-8"?>

<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">

<url>
<loc>https://example.com/page/</loc>
</url>

</urlset>

According to Google, a sitemap can help search engines discover pages, especially for large websites or websites with new content.

Learn more:Google Sitemap Documentation
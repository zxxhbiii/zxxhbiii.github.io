---
title: "How I Built an SEO-Friendly Astro Blog with Astro and GitHub Pages (2026 Guide)"
description: "A practical guide on building an SEO-friendly Astro blog with GitHub Pages, including Google Search Console, GA4 tracking, sitemap, robots.txt, canonical URLs, structured data, and technical SEO optimization."
author: " Cat Squirrel"
date: "2026-07-19"
tags:
  - SEO
  - Astro
  - GitHub Pages
  - Technical SEO
  - Google Search Console
  - Google Analytics
faq:
  - question: "Why did you choose Astro for an SEO blog?"
    answer: "Astro provides excellent performance with static site generation, clean HTML output, and strong SEO capabilities."

  - question: "Can GitHub Pages host an Astro website?"
    answer: "Yes. Astro can generate static files that can be deployed to GitHub Pages using GitHub Actions."

  - question: "Does Astro support SEO optimization?"
    answer: "Yes. Astro supports metadata management, sitemap generation, structured data, and fast-loading pages."
---

Building a personal technical blog has always been one of my goals as I continue learning about web development and SEO. However, creating a blog is not only about publishing articles. A successful website also needs a solid technical foundation to help search engines understand, crawl, and index its content.

In this project, I built an SEO-friendly blog using Astro and deployed it on GitHub Pages. I chose Astro because of its excellent performance, static site generation capabilities, and developer-friendly architecture.

During the development process, I implemented essential technical SEO features, including Google Search Console verification, Google Analytics 4 tracking, sitemap generation, robots.txt configuration, canonical URLs, structured data, and RSS feeds.

In this article, I will share how I built this blog from scratch, the SEO improvements I added, and the challenges I encountered during deployment.

## Why I Chose Astro for My SEO Blog

When I decided to build my own technical blog, choosing the right framework was one of the first decisions I needed to make. Since my goal was not only to publish content but also to build an SEO-friendly website, website performance and search engine accessibility were important factors.

I chose Astro because it is designed for content-focused websites and provides excellent performance through static site generation. Unlike traditional websites that rely heavily on client-side JavaScript, Astro ships minimal JavaScript by default and generates fast-loading static pages.

For an SEO blog, page speed and accessibility are important ranking factors. A faster website provides a better user experience and helps search engines crawl content more efficiently.

Another reason I selected Astro is its flexibility for technical SEO implementation. Astro makes it easy to customize important SEO elements, including metadata, canonical URLs, structured data, sitemap generation, and RSS feeds.

By combining Astro with GitHub Pages, I was able to create a lightweight, fast, and low-cost technical blog while maintaining full control over SEO optimization.

## Setting Up the Astro Blog Project

After choosing Astro as the framework, I started building the blog from scratch. The first step was setting up the development environment and creating a clean project structure that could support long-term content publishing.

I used Node.js and npm to initialize the Astro project:

```bash
npm create astro@latest
```

During the setup process, I selected a basic Astro template and configured the project based on my needs. Since this website is designed as a technical SEO blog, I focused on keeping the structure simple, maintainable, and optimized for content management.

The main technologies used in this project include:

Astro for static site generation
Tailwind CSS for styling
Astro Content Collections for managing blog posts
Markdown for writing articles

---

```md
The final project structure was organized as follows:

src/
├── components/
│   └── SEO.astro
│
├── content/
│   └── blog/
│       └── first-seo-post.md
│
├── layouts/
│   └── Layout.astro
│
├── pages/
│   ├── index.astro
│   └── blog/
│       ├── index.astro
│       └── [slug].astro
│
└── styles/
    └── global.css
```

This structure separates content, layouts, components, and pages, making the website easier to maintain as more articles are published.

For the blog system, I used Astro Content Collections to manage articles. Each post is written in Markdown with structured frontmatter, including the title, description, date, and tags.

This approach allows me to focus on creating SEO-friendly content while keeping the technical architecture lightweight and scalable.

## Deploying Astro to GitHub Pages with GitHub Actions

After building the Astro project locally, the next step was deploying the website to the internet. I chose GitHub Pages because it provides free static website hosting and works well with Astro's static output.

However, instead of manually uploading files after every update, I configured GitHub Actions to automatically build and deploy the website whenever new changes are pushed to the main branch.

The deployment workflow follows this process:

```text
Code Push
    ↓
GitHub Actions Trigger
    ↓
Install Dependencies
    ↓
Run Astro Build
    ↓
Generate Static Files
    ↓
Deploy to GitHub Pages
```

The GitHub Actions workflow was configured using the official GitHub Pages deployment process:

```yaml
name: Deploy Astro to GitHub Pages

on:
  push:
    branches:
      - main

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - uses: actions/setup-node@v4
        with:
          node-version: 22

      - run: npm ci

      - run: npm run build
```

After the build process completed successfully, GitHub Actions generated the static files from the Astro project and deployed them to GitHub Pages automatically.

This automated workflow provides several benefits:

- Faster publishing process when new articles are added
- Reduced manual deployment errors
- Consistent production builds
- Better workflow for maintaining a long-term content website

For an SEO blog, a reliable deployment process is important because technical issues can affect website availability, crawling, and indexing.

## Connecting Google Search Console and Google Analytics 4

After deploying the website, the next step was making sure search engines could discover and understand my content. A website without proper tracking and indexing configuration makes it difficult to measure SEO performance.

Therefore, I connected my Astro blog with Google Search Console and Google Analytics 4.

### Setting Up Google Search Console

Google Search Console (GSC) is an essential tool for monitoring how a website performs in Google Search. It provides information about search impressions, clicks, indexing status, and potential technical issues.

To verify my website ownership, I added the Google Search Console verification file to the public directory of my Astro project.

After successful verification, I submitted the generated sitemap:
https://zxxhbiii.github.io/sitemap-index.xml

The sitemap helps Google discover important pages on my website, including blog posts and category pages. It also provides search engines with a clearer understanding of the website structure.

### Adding Google Analytics 4

Besides search performance, I also wanted to understand user behavior after visitors arrived at the website. Therefore, I integrated Google Analytics 4 (GA4).

I added the GA4 tracking code to the global layout component so that every page could be tracked automatically.

During the setup process, I encountered an issue where GA4 worked correctly in the local development environment but failed after deployment.

The problem was caused by environment variables not being passed correctly during the GitHub Actions build process.

After adding the required environment variable in GitHub Actions, GA4 tracking started working correctly on the production website.

This experience showed me that SEO is not only about publishing content. Technical implementation, tracking, and data analysis are also important parts of building a successful website.

## Implementing Technical SEO for Astro

After connecting Google Search Console and Google Analytics, I continued improving the technical SEO foundation of the website.

### Canonical URLs

Canonical URLs help search engines understand the preferred version of a webpage and prevent duplicate content issues.

I added canonical tags to important pages, especially blog articles, to ensure each page has a clear primary URL.

### Open Graph and Twitter Cards

To improve social sharing appearance, I added Open Graph and Twitter Card metadata.

These tags allow platforms such as LinkedIn, X, and other social networks to display proper titles, descriptions, and preview images when a page is shared.

### Structured Data with JSON-LD

I implemented JSON-LD structured data using Schema.org vocabulary.

For the website homepage, I added WebSite structured data. For individual blog posts, I added BlogPosting structured data, including:

- Article title
- Description
- Publication date
- Author information

Structured data helps search engines better understand the content and improves eligibility for rich search results.

### robots.txt and Sitemap

I created a robots.txt file to provide crawling instructions for search engines and included the sitemap location.

Example:

User-agent: *
Allow: /

Sitemap: https://zxxhbiii.github.io/sitemap-index.xml

### RSS Feed

Since this is a content-focused website, I also added an RSS feed to make it easier for users and feed readers to follow new articles.

These technical SEO improvements created a stronger foundation for future content growth and search visibility.

## SEO Problems I Encountered and How I Fixed Them

Building an SEO-friendly website was not always straightforward. During the development and deployment process, I encountered several technical issues related to tracking, indexing, and deployment.

These problems helped me better understand that SEO is not only about adding keywords or publishing content. Technical implementation plays an important role in search engine visibility.

### 1. Google Analytics 4 Worked Locally but Not After Deployment

One of the first problems I encountered was that Google Analytics 4 worked correctly in the local development environment, but no real-time users appeared after deploying the website.

After debugging the issue, I found that the GA4 tracking ID was stored in an environment variable, but the variable was not passed correctly during the GitHub Actions build process.

The solution was adding the required environment variable to GitHub Actions so that Astro could access it during production builds.

After updating the deployment workflow, GA4 tracking started working correctly on the live website.

---

### 2. Google Search Console Could Not Fetch the Sitemap

After verifying website ownership in Google Search Console, I submitted the sitemap file.

However, Search Console initially showed that the sitemap could not be fetched.

I checked several possible causes:

- Whether the sitemap URL was accessible
- Whether robots.txt contained the correct sitemap path
- Whether the sitemap format was valid
- Whether the website deployment was completed successfully

After confirming that the sitemap-index.xml file was generated correctly and publicly accessible, Google Search Console was able to process the sitemap successfully.

---

### 3. Deployment and Environment Configuration Issues

During development, I also encountered deployment-related issues, including GitHub connection failures and Node.js version compatibility problems.

For example, the Astro project required a newer Node.js version during setup, so I upgraded the development environment to ensure compatibility.

These experiences reminded me that maintaining an SEO website requires continuous monitoring of both technical infrastructure and search engine performance.

---

Through solving these problems, I gained practical experience in technical SEO, website deployment, and SEO troubleshooting. These lessons will also help me optimize future websites more efficiently.

## Conclusion

Building my first SEO-friendly blog with Astro and GitHub Pages has been a valuable learning experience.

Through this project, I learned that creating a successful website requires more than just writing content. A strong SEO foundation includes technical optimization, search engine tracking, website performance, and continuous improvement.

By implementing Google Search Console, Google Analytics 4, sitemap generation, robots.txt, canonical URLs, structured data, and RSS feeds, I created a solid foundation for future content growth.

However, SEO is an ongoing process. In the future, I will continue publishing technical articles, analyzing search performance through Google Search Console, and improving the website based on real user data.

This blog will continue to serve as a place where I document my journey in SEO, artificial intelligence, and web development.

## Frequently Asked Questions

<div class="faq">

### Is Astro good for SEO?

Yes. Astro is suitable for SEO-focused websites because it generates fast static pages and provides flexible control over metadata and structured data.


### Can I deploy Astro websites for free?

Yes. Astro static websites can be deployed using platforms such as GitHub Pages, Netlify, or Vercel.


### Does Astro automatically handle SEO?

No. Astro provides a strong technical foundation, but developers still need to configure metadata, sitemap, canonical URLs, and structured data.

</div>
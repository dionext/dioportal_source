---
title: "SEO"
description: ""
keywords: ""
lang: "en"
permalink: "web-seo"
aliases:
  - "web-seo"
---

# SEO

## Overview

Search engine optimization (SEO) is the process of improving the quality and quantity of website traffic to a website or a web page from search engines. SEO targets unpaid traffic (known as "natural" or "organic" results) rather than direct traffic or paid traffic. Unpaid traffic may originate from different kinds of searches, including image search, video search, academic search, news search, and industry-specific vertical search engines. As an Internet marketing strategy, SEO considers how search engines work, the computer-programmed algorithms that dictate search engine behavior, what people search for, the actual search terms or keywords typed into search engines, and which search engines are preferred by their targeted audience. SEO is performed because a website will receive more visitors from a search engine when websites rank higher on the search engine results page (SERP). These visitors can then potentially be converted into customers. [https://en.wikipedia.org/wiki/Search\_engine\_optimization](https://en.wikipedia.org/wiki/Search_engine_optimization)

## File robots.txt

robots.txt is the filename used for implementing the Robots Exclusion Protocol, a standard used by websites to indicate to visiting web crawlers and other web robots which portions of the website they are allowed to visit.  
When a site owner wishes to give instructions to web robots they place a text file called robots.txt in the root of the web site hierarchy (e.g. https://www.example.com/robots.txt). This text file contains the instructions in a specific format (see examples below). Robots that choose to follow the instructions try to fetch this file and read the instructions before fetching any other file from the website. If this file does not exist, web robots assume that the website owner does not wish to place any limitations on crawling the entire site.  
A robots.txt file contains instructions for bots indicating which web pages they can and cannot access. Robots.txt files are particularly important for web crawlers from search engines such as Google. [https://en.wikipedia.org/wiki/Robots.txt](https://en.wikipedia.org/wiki/Robots.txt)

Example:This example tells all robots not to enter three directories:

    User-agent: *
    Disallow: /cgi-bin/
    Disallow: /tmp/
    Disallow: /junk/

## File Sitemap

A sitemap is a file where you provide information about the pages, videos, and other files on your site, and the relationships between them. Search engines like Google read this file to crawl your site more efficiently. A sitemap tells search engines which pages and files you think are important in your site, and also provides valuable information about these files. For example, when the page was last updated and any alternate language versions of the page. [https://developers.google.com/search/docs/crawling-indexing/sitemaps/overview?hl=en](https://developers.google.com/search/docs/crawling-indexing/sitemaps/overview?hl=en)

[https://www.sitemaps.org/protocol.html](https://www.sitemaps.org/protocol.html)

Example:

```html
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9" >
 <url>
  <loc>http://www.example.com/index.html</loc>
  <lastmod>2024-04-15</lastmod>
  <priority>1.0</priority>
 </url>
 <url>
  <loc>http://www.example.com/somepage.html</loc>
  <lastmod>2024-04-15</lastmod>
  <priority>1.0</priority>
 </url>
</urlset>
	
```

Sitemap with localized versions of pages [https://developers.google.com/search/docs/specialty/international/localized-versions?hl=en](https://developers.google.com/search/docs/specialty/international/localized-versions?hl=en)

Example:

```
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9"
  xmlns:xhtml="http://www.w3.org/1999/xhtml">
  <url>
    <loc>https://www.example.com/english/page.html</loc>
    <xhtml:link
               rel="alternate"
               hreflang="de"
               href="https://www.example.de/deutsch/page.html"/>
    <xhtml:link
               rel="alternate"
               hreflang="de-ch"
               href="https://www.example.de/schweiz-deutsch/page.html"/>
    <xhtml:link
               rel="alternate"
               hreflang="en"
               href="https://www.example.com/english/page.html"/>
  </url>
  <url>
    <loc>https://www.example.de/deutsch/page.html</loc>
    <xhtml:link
               rel="alternate"
               hreflang="de"
               href="https://www.example.de/deutsch/page.html"/>
    <xhtml:link
               rel="alternate"
               hreflang="de-ch"
               href="https://www.example.de/schweiz-deutsch/page.html"/>
    <xhtml:link
               rel="alternate"
               hreflang="en"
               href="https://www.example.com/english/page.html"/>
  </url>
  <url>
    <loc>https://www.example.de/schweiz-deutsch/page.html</loc>
    <xhtml:link
               rel="alternate"
               hreflang="de"
               href="https://www.example.de/deutsch/page.html"/>
    <xhtml:link
               rel="alternate"
               hreflang="de-ch"
               href="https://www.example.de/schweiz-deutsch/page.html"/>
    <xhtml:link
               rel="alternate"
               hreflang="en"
               href="https://www.example.com/english/page.html"/>
  </url>
</urlset>
```

```html

        
```

References:

[https://github.com/dfabulich/sitemapgen4j](https://github.com/dfabulich/sitemapgen4j) SitemapGen4j is a library to generate XML sitemaps in Java

[https://stackoverflow.com/questions/31714663/build-sitemap-xml-by-java-spring](https://stackoverflow.com/questions/31714663/build-sitemap-xml-by-java-spring)

[https://stackoverflow.com/questions/12289232/serving-sitemap-xml-and-robots-txt-with-spring-mvc](https://stackoverflow.com/questions/12289232/serving-sitemap-xml-and-robots-txt-with-spring-mvc)

## Google Analytics

[https://analytics.google.com/analytics/web/provision/#/provision](https://analytics.google.com/analytics/web/provision/#/provision)

Google Analytics is a web analytics service offered by Google that tracks and reports website traffic and also the mobile app traffic \& events, currently as a platform inside the Google Marketing Platform brand. Google launched the service in November 2005 after acquiring Urchin [https://en.wikipedia.org/wiki/Google\_Analytics](https://en.wikipedia.org/wiki/Google_Analytics)

## Website Speed Test

[https://pagespeed.web.dev/](https://pagespeed.web.dev/) PageSpeed Insights

## Offline site generators

Java: [https://jbake.org/](https://jbake.org/)

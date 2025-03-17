---
title: "Dionext software development notes"
description: ""
keywords: ""
lang: "en"
permalink: "web-html"
aliases:
  - "web-html"
---

## HTML

## HTML Editors

### WYSIWYG

WYSIWYG - an acronym for What You See Is What You Get, refers to software which allows content to be edited in a form that resembles its appearance when printed or displayed as a finished product, such as a printed document, web page, or slide presentation. WYSIWYG implies a user interface that allows the user to view something very similar to the result while the document is being created. In general, WYSIWYG implies the ability to directly manipulate the layout of a document without having to type or remember names of layout commands. [https://en.wikipedia.org/wiki/WYSIWYG](https://en.wikipedia.org/wiki/WYSIWYG)

**TinyMCE.** This is a very popular web-based HTML WYSIWYG editor used by popular content management systems like WordPress. You can easily add images, links, lists and quotes to your webpage very easily without needing to know any HTML code whatsoever. *(Free Plan allows 1,000 editor loads per month [https://www.tiny.cloud/pricing/](https://www.tiny.cloud/pricing/) )*

**Microsoft Expression Web** is a discontinued HTML editor and general web design software product by Microsoft. It was discontinued on December 20, 2012, and subsequently made available free of charge from Microsoft. It was a component of the also discontinued Expression Studio. Expression Web can design and develop web pages using HTML5, CSS 3, ASP.NET, PHP, JavaScript, XML+XSLT and XHTML. Expression Web 4 requires .NET Framework 4.0 and Silverlight 4.0 to install and run. Expression Web uses its own standards-based rendering engine which is different from Internet Explorer's Trident engine. [https://en.wikipedia.org/wiki/Microsoft\_Expression\_Web](https://en.wikipedia.org/wiki/Microsoft_Expression_Web)

## Adaptive web design

Adaptive web design (AWD) promotes the creation of multiple versions of a web page to better fit the user's device, as opposed to a single static page which loads (and looks) the same on all devices or a single page which reorders and resizes content responsively based on the device/screen size/browser of the user.

[https://en.wikipedia.org/wiki/Adaptive\_web\_design](https://en.wikipedia.org/wiki/Adaptive_web_design)

The future of responsive design [https://developer.ibm.com/articles/responsive-design-future/](https://developer.ibm.com/articles/responsive-design-future/)

## Html structure

Order of elements [https://stackoverflow.com/questions/1987065/what-are-best-practices-to-order-elements-in-head](https://stackoverflow.com/questions/1987065/what-are-best-practices-to-order-elements-in-head)

## Responsive images

### picture

    <picture> 
    <source media="(min-width: 1024px)" srcset="opera-fullshot.webp" type="image/webp"> 
    <source media="(min-width: 1024px)" srcset="opera-fullshot.jpg"> 
    <source srcset="opera-closeup.webp" type="image/webp"> 
    <img src="opera-closeup.jpg" alt="The Oslo Opera House"> 
    </picture> 

### srcset

    <img src="small.jpg" srcset="medium.jpg 1000w, large.jpg 2000w"alt="yah"> 
    <img src="opera-1x.jpg" alt="The Oslo Opera House" srcset="opera-2x.jpg 2x, opera-3x.jpg 3x"> 
    <img src="opera-fallback.jpg" alt="The Oslo Opera House" sizes="(min-width: 640px) 60vw, 100vw" srcset="opera-200.jpg 200w, opera-400.jpg 400w, opera-800.jpg 800w, opera-1200.jpg 1200w">

## Cites

* \<blockquote\>
* \<q\>
* \<cite\>

[https://www.bdblogov.ru/2014/07/beautiful-styles-design-quotes-in-blog-Blogspot.html](https://www.bdblogov.ru/2014/07/beautiful-styles-design-quotes-in-blog-Blogspot.html)

[https://www.ipetrenko.com/2015/11/5-amazing-style-for-blockquote.html](https://www.ipetrenko.com/2015/11/5-amazing-style-for-blockquote.html)

[https://html5book.ru/krasivoe-oformlenie-citat-na-sayte/](https://html5book.ru/krasivoe-oformlenie-citat-na-sayte/)

## Code highlighting

### highlightjs

[https://highlightjs.org/](https://highlightjs.org/) javascript

    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/styles/default.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/highlight.min.js"></script>
    
    <!-- and it's easy to individually load additional languages -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/languages/go.min.js"></script>
    
    <script>`hljs.highlightAll();</script>`

This will find and highlight code inside \<pre\>\<code\> tags; it tries to detect the language automatically. If automatic detection does not work for you, you can specify the language in the class attribute:

```
`<`pre><code class="language-html">`...</code></pre>`
```

List of languages [https://highlightjs.readthedocs.io/en/latest/supported-languages.html](https://highlightjs.readthedocs.io/en/latest/supported-languages.html)

Add "Copy" button [https://github.com/arronhunt/highlightjs-copy](https://github.com/arronhunt/highlightjs-copy)

Alternate [https://www.eddymens.com/blog/adding-a-copy-button-to-highlightjs-code-snippets](https://www.eddymens.com/blog/adding-a-copy-button-to-highlightjs-code-snippets)

You could just replace the default theme name inside \<Head\> with your desired theme

```
<link rel="stylesheet" href="//cdn.jsdelivr.net/gh/highlightjs/cdn-release@10.3.2/build/styles/{ THEME_NAME }.min.css"></lin
```

### Prism

Prism is a lightweight, extensible syntax highlighter, built with modern web standards in mind. It's used in millions of websites, including some of those you visit daily. [https://prismjs.com/](https://prismjs.com/) [https://www.garb.ru/blog/prism.html](https://www.garb.ru/blog/prism.html)

### SyntaxHighlight

For mediawiki [https://www.mediawiki.org/wiki/Extension:SyntaxHighlight/ru](https://www.mediawiki.org/wiki/Extension:SyntaxHighlight/ru)

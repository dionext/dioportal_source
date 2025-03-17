---
title: "Spring starter (library) for creating simple websites"
description: ""
keywords: ""
lang: "en"
permalink: "lib-site-spring-starter"
aliases:
  - "lib-site-spring-starter"
---


# Spring starter (library) for creating simple websites

Source: [https://github.com/dionext/lib-site-spring-starter](https://github.com/dionext/lib-site-spring-starter)

The goal of the project is to make it easier to generate simple websites. The main content of such sites consists of static materials: articles, blogs, etc. The easiest way to post them on the Internet is to post them as static pages and then process them with a simple web server (for example, nginx). Such a site is usually called a static site. And many sites on the Internet were originally made in exactly this way. However, quite a long time ago there was a tendency towards an increase in the percentage of dynamic sites. Even for simple projects. Why is this happening? The point is that even the simplest website usually needs some dynamic content. For example, a site has a menu that is repeated on every page. When you add a new item to a menu, you have to edit all the pages on which it is used. The question arises: is it possible to place the site menu in a separate file, which will then be dynamically included in all pages? This problem can be solved in various ways. One of the solutions is provided by various offline editors and generators (outdated Ms Frontpage, not outdated Adobe Dreamweaver, etc.). There are also many other alternative ways to solve the problem: frames, javascript, cloud site builders, installing a web content management system (WordPress, etc.). However, developers who have a good command of software technologies in the Java language often come to the conclusion that it is more profitable not to diversify their attention to studying third-party technologies, but to solve this rather simple task, remaining within the framework of the technology that they are fluent in. For example, using Java and Spring Boot. But if they choose this path, then before they can get the maximum benefit from using their experience and knowledge, they will have to solve a number of routine problems. The described library is intended to help with this.

PageCreatorService

* createHtmlAll
  * createHtmlBeginTag
  * createHeadContentType
  * createHeadTitle
  * createHeadLocaleLinks
  * createHeadMetaDescription
  * createHeadMetaForIcons
  * createHeadMetaForSocialMedia
  * createHeadBootstrap
  * createHeadBottom
  * createBodyTop
    * createBodyTopBanner
    * createBodyTopMenu
      * createBodyTopMenuStyle
      * createBodyTopMenuHierLevel
      * createBodyTopMenuLangSelector
  * createBodyMainSection
  * createBodyBottom
    HtmlBlock
    * createBodyBottomInformation
    * createBodyBottomMenu
  * createBodyBootstrap
  * createBodyScripts
  * createBodySearchEngineScripts

PageParserService

processPage

* getTitleFromPage
* getMetaDescriptionFromPage
* getMetaKeywordsFromPage
* getBodyFromPage
* adjustBody
  * adjustHrefs
    * adjustHref
  * adjustBlockquotes
    * adjustBlockquote
  * adjustIframes
    * adjustIframe
  * adjustImages
    * adjustImage
    * adjustImageByFigure

---
title: "Integration with internet services"
description: ""
keywords: ""
lang: "en"
permalink: "integration-with-internet-services"
aliases:
  - "integration-with-internet-services"
---

# Integration with internet services

## Open Graph protocol

Open Graph protocol logo The Open Graph protocol enables developers to integrate their pages into Facebook's global mapping/tracking tool Social Graph. These pages gain the functionality of other graph objects including profile links and stream updates for connected users. [https://en.wikipedia.org/wiki/Facebook\_Platform#Open\_Graph\_protocol](https://en.wikipedia.org/wiki/Facebook_Platform#Open_Graph_protocol)

[http://ogp.me](http://ogp.me)

Introduction The Open Graph protocol enables any web page to become a rich object in a social graph. For instance, this is used on Facebook to allow any web page to have the same functionality as any other object on Facebook. While many different technologies and schemas exist and could be combined together, there isn't a single technology which provides enough information to richly represent any web page within the social graph. The Open Graph protocol builds on these existing technologies and gives developers one thing to implement. Developer simplicity is a key goal of the Open Graph protocol which has informed many of the technical design decisions.

```html

<meta property="og:title" content="Example title of article">
<meta property="og:site_name" content="example.com website">
<meta property="og:type" content="article">
<meta property="og:url" content="http://example.com/example-title-of-article">
<meta property="og:image" content="http://example.com/article_thumbnail.jpg">
<meta property="og:image" content="http://example.com/website_logo.png">
<meta property="og:description" content="This example article is an example of OpenGraph protocol.">
```

## RDFa

RDFa or Resource Description Framework in Attributes\[1\] is a W3C Recommendation that adds a set of attribute-level extensions to HTML, XHTML and various XML-based document types for embedding rich metadata within Web documents. The Resource Description Framework (RDF) data-model mapping enables its use for embedding RDF subject-predicate-object expressions within XHTML documents. It also enables the extraction of RDF model triples by compliant user agents. [https://en.wikipedia.org/wiki/RDFa](https://en.wikipedia.org/wiki/RDFa)

```html

<div xmlns:dc="http://purl.org/dc/elements/1.1/"
  about="http://www.example.com/books/wikinomics">
  <span property="dc:title">Wikinomics</span>
  <span property="dc:creator">Don Tapscott</span>
  <span property="dc:date">2006-10-01</span>
</div>
```

## OpenID

OpenID is an open standard and decentralized authentication protocol promoted by the non-profit OpenID Foundation. It allows users to be authenticated by co-operating sites (known as relying parties, or RP) using a third-party identity provider (IDP) service, eliminating the need for webmasters to provide their own ad hoc login systems, and allowing users to log in to multiple unrelated websites without having to have a separate identity and password for each.\[1\] Users create accounts by selecting an OpenID identity provider, and then use those accounts to sign on to any website that accepts OpenID authentication. Several large organizations either issue or accept OpenIDs on their websites [https://en.wikipedia.org/wiki/OpenID](https://en.wikipedia.org/wiki/OpenID)

## OAuth

OAuth (short for "Open Authorization") is an open standard for access delegation, commonly used as a way for internet users to grant websites or applications access to their information on other websites but without giving them the passwords. This mechanism is used by companies such as Amazon, Google, Meta Platforms, Microsoft, and Twitter to permit users to share information about their accounts with third-party applications or websites.

## References

[https://docs.oneall.com/api/](https://docs.oneall.com/api/)
Opt for a cloud-based social network integration to reduce in-house development time and eliminate maintenance costs. We constantly monitor the APIs and technologies of the different social networks and update our services as soon as changes arise. By using OneAll you can integrate 35+ social networks in one go.

[https://www.slideshare.net/Open-IT/social-network-api](https://www.slideshare.net/Open-IT/social-network-api) (lang:rus)

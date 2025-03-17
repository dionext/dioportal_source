---
title: "Working with text"
description: ""
keywords: ""
lang: "en"
permalink: "working-with-text"
aliases:
  - "working-with-text"
---

# Working with text

## HTML

See [HTML](web-html)

## Markdown

See also: [Documentation. Notes](documentation)

Markdown is a lightweight markup language for creating formatted text using a plain-text editor. John Gruber and Aaron Swartz created Markdown in 2004 as a markup language that is intended to be easy to read in its source code form. Markdown is widely used for blogging and instant messaging, and also used elsewhere in online forums, collaborative software, documentation pages, and readme files

GitHub had been using its own variant of Markdown since as early as 2009, which added support for additional formatting such as tables and nesting block content inside list elements, as well as GitHub-specific features such as auto-linking references to commits, issues, usernames, etc. In 2017, GitHub released a formal specification of its GitHub Flavored Markdown (GFM) that is based on CommonMark. It is a strict superset of CommonMark, following its specification exactly except for tables, strikethrough, autolinks and task lists, which GFM adds as extensions. Accordingly, GitHub also changed the parser used on their sites, which required that some documents be changed. For instance, GFM now requires that the hash symbol that creates a heading be separated from the heading text by a space character.

Some apps, services and editors support Markdown as an editing format. ChatGPT: Output from the AI model formatted in Markdown will be rendered in LaTeX and HTML by the ChatGPT client, and the model is encouraged to use Markdown to format its output. Markdown provided by the user will not be formatted by the client, but will still be passed to the AI model unaltered. [https://en.wikipedia.org/wiki/Markdown](https://en.wikipedia.org/wiki/Markdown)

[https://www.markdownguide.org/](https://www.markdownguide.org/)

[https://www.youtube.com/watch?v=d8fXEhWy\_rY](https://www.youtube.com/watch?v=d8fXEhWy_rY) Every USEFUL Markdown Syntax That I Use in Obsidian

Example

    Heading
    =======
    
    Sub-heading
    -----------
    
    # Alternative heading
    
    ## Alternative sub-heading
    
    Paragraphs are separated 
    by a blank line.
    
    Two spaces at the end of a line  
    produce a line break.

```
 
```

`Links `

[https://help.obsidian.md/links](https://help.obsidian.md/links)` `

\[link\](http://example.com)

You can link to headings with custom IDs in the file by creating a standard link with a number sign (#) followed by the custom heading ID. These are commonly referred to as anchor links.

You can optionally add a title for a link. This will appear as a tooltip when the user hovers over the link. To add a title, enclose it in quotation marks after the URL.

My favorite search engine is \[Duck Duck Go\](https://duckduckgo.com "The best search engine for privacy").

Many Markdown processors support custom IDs for headings - some Markdown processors automatically add them. Adding custom IDs allows you to link directly to headings and modify them with CSS. To add a custom heading ID, enclose the custom ID in curly braces on the same line as the heading.

### My Great Heading {\#custom-id}

\[Heading IDs\](#heading-ids)

Some Markdown applications like Markdeep can automatically generate a table of contents (also referred to as a toc) from your headings, but this isn't a feature provided by all Markdown applications. However, if your Markdown application supports heading IDs, you can create a table of contents for your Markdown file using a list and some links. ####

Table of Contents

- \[Underline\](#underline)

- \[Indent\](#indent)

- \[Center\](#center)

- \[Color\](#color)

Indent (Tab)

\&nbsp;\&nbsp;\&nbsp;\&nbsp;This is the first sentence of my indented paragraph.

Some people like creating links that open in new tabs or windows. The Markdown syntax for links doesn't allow you to specify the target attribute, but if your Markdown processor supports HTML, you can use HTML to create these links.

\<a href="https://www.markdownguide.org" target="\_blank"\>Learn Markdown!\</a\>

To quickly turn a URL or email address into a link, enclose it in angle brackets.

\<https://www.markdownguide.org\>

\<fake@example.com\>

Images

!\[Tux, the Linux mascot\](/assets/images/tux.png)

To add a link to an image, enclose the Markdown for the image in brackets, and then add the link in parentheses.

\[!\[An old rock in the desert\](/assets/images/shiprock.jpg "Shiprock, New Mexico by Beau Rogers")\](https://www.flickr.com/photos/beaurogers/31833779864)

[http://www.chriskrycho.com/2015/academic-markdown-and-citations.html](http://www.chriskrycho.com/2015/academic-markdown-and-citations.html) Academic Markdown and Citations  
Footnotes in Markdown look like this:

```markdown hljs
Here is some text.[^fn]

[^fn]: And the footnote!
```

GitHub Flavored Markdown doesn't support footnotes, but you can manually fake it¹ with Unicode characters or superscript tags, e.g. ^1^.

|-------------------------------------------------------------------------------------------------------------------------------|
| 1{#myfootnote1}: Footnote content goes here Then reference it at some other place in the document like this [1](#myfootnote1) |

### HTML to/from Markdown converters

[https://pandoc.org/](https://pandoc.org/) If you need to convert files from one markup format into another, pandoc is your swiss-army knife. Pandoc can convert between the following formats: (← = conversion from; → = conversion to; ↔︎ = conversion from and to)

[https://www.cssportal.com/markdown-to-html/](https://www.cssportal.com/markdown-to-html/)

[https://www.cssportal.com/html-to-markdown/](https://www.cssportal.com/html-to-markdown/)

### Java libraries for working with markdown

[https://github.com/vsch/flexmark-java/wiki/Usage](https://github.com/vsch/flexmark-java/wiki/Usage)

### Markdown Viewers and Editors

Visual Studio Code plugins

* Markdown All in One
* others

Notepad++ plugins

* Markdown Panel (C#, IE)
* MarkdownViewer++ (C#, HTML-Renderer)

Obsidian has desktop version [https://obsidian.md/download](https://obsidian.md/download)

iA Writer [https://ia.net/writer](https://ia.net/writer) 5$/Month

[https://ghostwriter.kde.org/](https://ghostwriter.kde.org/)

[https://www.zettlr.com/](https://www.zettlr.com/)

[https://github.com/atom/atom](https://github.com/atom/atom)

## Mediawiki format

[https://www.mediawiki.org/wiki/Help:Formatting](https://www.mediawiki.org/wiki/Help:Formatting/ru)

## LaTeX

LaTeX is a software system for typesetting documents. LaTeX markup describes the content and layout of the document, as opposed to the formatted text found in WYSIWYG word processors like Microsoft Word, LibreOffice Writer and Apple Pages. The writer uses markup tagging conventions to define the general structure of a document, to stylise text throughout a document (such as bold and italics), and to add citations and cross-references. A TeX distribution such as TeX Live or MiKTeX is used to produce an output file (such as PDF or DVI) suitable for printing or digital distribution. [https://en.wikipedia.org/wiki/LaTeX](https://en.wikipedia.org/wiki/LaTeX)

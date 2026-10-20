---
title: "Documentation. Notes"
description: ""
keywords: ""
lang: "en"
permalink: "documentation"
aliases:
  - "documentation"
---


# Documentation. Notes

## Different formats 

doc

rtf 

html 

fb2 

FB2 refers to the FictionBook e-book file format, an open, XML-based format primarily used for fiction but suitable for any eBook content, that was developed in Russia. It uses a single XML file to describe the book's structure and metadata and supports features like images, footnotes, and text formatting. FB2 files are DRM-free and can be opened with various e-reading applications and browsers, often through extensions, on multiple platforms

djvu 

DjVu is a computer file format designed primarily to store scanned documents, especially those containing a combination of text, line drawings, indexed color images, and photographs. It uses technologies such as image layer separation of text and background/images, progressive loading, arithmetic coding, and lossy compression for bitonal (monochrome) images. This allows high-quality, readable images to be stored in a minimum of space, so that they can be made available on the web. DjVu has been promoted as providing smaller files than PDF for most scanned documents. The DjVu developers report that color magazine pages compress to 40–70 kB, black-and-white technical papers compress to 15–40 kB, and ancient manuscripts compress to around 100 kB; a satisfactory JPEG image typically requires 500 kB. Like PDF, DjVu can contain an OCR text layer, making it easy to perform copy and paste and text search operations.


## Text convertors 
### Pandoc 
Pandoc  [https://pandoc.org/](https://pandoc.org/)  export to html, pdf 

Pandoc is a Haskell library for converting from one markup format to another, and a command-line tool that uses this library. Pandoc can convert between numerous markup and word processing formats, including, but not limited to, various flavors of Markdown, HTML, LaTeX and Word docx. For the full lists of input and output formats, see the --from and --to options below. Pandoc can also produce PDF output: see creating a PDF, below.
~~~shell
pandoc -t markdown "D:\file1.docx" -o "D:\file1_converted.md"
~~~

Pandoc primarily uses UTF-8 for both input and output character encoding. If you are working with files encoded in Windows-1251 (CP1251), which is common for Cyrillic languages in older systems, you will need to convert the encoding before or after processing with Pandoc. 

Here's how to handle Windows-1251 with Pandoc:

1. Converting Input Files to UTF-8:

The recommended approach is to convert your Windows-1251 input files to UTF-8 before feeding them to Pandoc. You can use a tool like `iconv` (available on most Unix-like systems and via various ports on Windows) for this purpose.

```shell
iconv -f WINDOWS-1251 -t UTF-8 input.txt > input_utf8.txt
pandoc input_utf8.txt -o output.html
```

2. 
 * **Open your file**: in Notepad++.
- Go to the Encoding menu.
- Select Convert to UTF-8 (or your desired encoding).
- **Save**: the file.

### Calibre

**calibre is a powerful and easy to use e-book manager**. Users say it’s _outstanding_ and a _must-have_. It’ll allow you to do nearly everything and it takes things a step beyond normal e-book software. It’s also **completely free** and _open source_ and great for both **casual users** and computer experts.

https://calibre-ebook.com/
## Obsidian


[https://obsidian.md/](https://obsidian.md/) Sharpen your thinking. Obsidian is the private and flexible writing app that adapts to the way you think. 

https://help.obsidian.md/file-formats  Accepted file formats

[https://help.obsidian.md/plugins/audio-recorder](https://help.obsidian.md/plugins/audio-recorder)

### Text formating 

~~~ markdown 
>[!question] 
> What? 
~~~

>[!question] 
> What? 

![[{1A8990BD-8689-455E-91E7-8D1A547E3F52}.png]]

* https://github.com/Reocin/obsidian-markdown-formatting-assistant-plugin This Plugin provides easy to use snippets for Markdown, HTML and Latex and a color picker which shows the history of last used colors. Furthermore, it is possible to save any color you want. Version 0.4.0 ( PLUGIN NOT MAINTAINED anymore)

Add Colour to Your Markdown Text [https://clemensjarnach.github.io/02-articles/2023-05-02-article.html](https://clemensjarnach.github.io/02-articles/2023-05-02-article.html)

### Links 
~~~

[[wiki link]]
[markdown link]()

[[documentation]]
[[documentation#Obsidian]]
[[documentation#^41765f]]

![[documentation]]
![[documentation#Obsidian]]
![[documentation#^41765f]]

[[documentation | Page about documentation ]]

//embeded Youtube 

![](https://www.youtube.com/watch?v=6R3RF2CoYv8)  

~~~


Useful plugins 
* https://github.com/zolrath/obsidian-auto-link-title  This plugin automatically fetches the webpage to extract link titles when they're pasted, creating a markdown link with the correct title set.  Overwrite Titles Of Existing Markdown Links.  Additionally, using `ctrl-shift-e` (Windows) or `cmd-shift-e` (OS X) you can overwrite an existing title of a markdown link with the fetched title from the url.   - *work bad on youtube* 
* https://github.com/Seraphli/obsidian-link-embed This plugin allows you to convert URLs in your notes into embedded previews. - *work bad on youtube* 
* Backlinks (Core, default on) Show links from other notes to the current one
* https://github.com/dartungar/obsidian-emotion-picker Obsidian Emotion Picker. Paste an emotion / feeling into note, using customizable list of emotions (or sensible default one).  Some specific Markdown environments or extensions support "emoji shortcodes," which are text-based representations like `:smile:` for 😄 or `:heart:` for ❤️. When rendered, these shortcodes are automatically converted into their corresponding emojis. This functionality is not part of standard Markdown but is common in platforms like GitHub, Slack, and various Markdown editors with emoji plugins (e.g., Markdown Emoji extension for VS Code). 
* *Alternative for insert emotion in markdown: - **Windows:** Press `Windows key + .` (period) to open the emoji keyboard.*
* https://github.com/oliveryh/obsidian-emoji-toolbar This plugin allows you to quickly search for and add emojis to your editor. After enabling the plugin, you'll find a new hot key setting called `Emoji Toolbar: Open emoji picker`. Set this to whatever you like. Once clicked it will allow you to search through a list of emojis.
### Images 

Useful plugins 
* Local Images Plus - https://github.com/Sergei-Korneev/obsidian-local-images-plus (not perfect)
* https://github.com/xryul/obsidian-image-converter 

### Files, Attachments 

### Search 

* https://github.com/scambier/obsidian-omnisearch Omnisearch is a search engine that "just works". It always instantly shows you the most relevant results, thanks to its smart weighting algorithm.
### Compose

https://github.com/kevboh/longform  Longform is a plugin for Obsidian that helps you write and edit novels, screenplays, and other long projects. It lets you organize a series of notes, or scenes, into an ordered manuscript. It also supports single-note projects for shorter works.

### Import from different sources 

- \[Подробная настройка и использование Telegram Sync\](https://www.youtube.com/watch?v=xV02gHXZULM\&t=555s)
- \[Obsidian Web Clipper\](https://obsidian.md/clipper) (from https://www.youtube.com/watch?v=_sigcgludUE  Obsidian Web Clipper Deep Dive: Free AI-Powered Web Capture That Beats Readwise) 
- Telegram Sync [https://obsidian.md/plugins?id=telegram-sync](https://obsidian.md/plugins?id=telegram-sync)
- https://github.com/OliverBalfour/obsidian-pandoc (old beta) It adds command palette options to export your notes to a variety of formats including Word Documents, PDFs, ePub books, HTML websites, PowerPoints and LaTeX among (many) others. This is all thanks to Pandoc. This lets you write presentations, draft books, make webpages, and write assignments all in Markdown, and export to whichever format you fancy, all without leaving Obsidian.

#### Zotero integration
https://github.com/mgmeyers/obsidian-zotero-integration Insert and import citations, bibliographies, notes, and PDF annotations from Zotero into Obsidian. Requires the Better BibTeX for Zotero plugin.

https://github.com/retorquere/zotero-file-hierarchy When installed in Zotero, this translator will allow exporting attachments of items in your Zotero Library or selected collection as files organized in folders. The exported attachments (files) will be organized in folders which reflect the hierarchical structure of your selected Zotero Library/Collections.

### Export (publish)

https://dg-docs.ole.dev/ Obsidian Digital Garden
The Obsidian Digital Garden Plugin is a free and open source publishing tool for Obsidian. Publish your notes directly from Obsidian to the internet. While feature packed, it is highly configurable and hackable. Enable and disable features on a per-note basis. Use it as a full fledged digital garden or as a simple note sharing solution.

### Audio
* Audio Recorder (Core Plugin) Audio recorder is a core plugin that lets you record and save audio in an Obsidian note. With the Audio recorder plugin, you can record details from a lecture, meeting, or other important situations where you can't type fast enough. https://help.obsidian.md/plugins/audio-recorder  Alternative(?): https://www.obsidianstats.com/plugins/super-duper-audio-recorder
* Whisper API [https://github.com/nikdanilov/whisper-obsidian-plugin](https://github.com/nikdanilov/whisper-obsidian-plugin) Obsidian Whisper is a plugin that effortlessly turns your speech into written notes. Just speak your mind, and let Whisper from OpenAI do the rest!  For this plugin to work, you will need to provide your OpenAI API key. (works only with OpenAI server ?)



Audio Notes plugin for Obsidian from the community plugin browser, then obtain a Deepgram AI API key and add it to the plugin's settings.   - not works with russian voice, but works on web 

https://github.com/djmango/obsidian-transcription not working 
### Tables 

### Dataview 
* https://github.com/blacksmithgu/obsidian-dataview Treat your Obsidian Vault as a database which you can query from. Provides a JavaScript API and pipeline-based query language for filtering, sorting, and extracting data from Markdown pages. See the Examples section below for some quick examples, or the full reference for all the details.



### AI 
list https://www.obsidianstats.com/tags/ai 

Interesting plugins 
* https://github.com/logancyang/obsidian-copilot
* Text Extractor
* Text Generator [https://docs.text-gen.com/](https://docs.text-gen.com/) [https://www.youtube.com/watch?v=D682V8SfYmI](https://www.youtube.com/watch?v=D682V8SfYmI)
* Smart Connections https://github.com/brianpetro/obsidian-smart-connections The Smart Connections plugin is designed to enhance your Obsidian experience by leveraging AI to find and connect relevant notes. By using AI embeddings, it provides real-time suggestions of related notes through the Smart View, making it easier to discover connections in your vault. The plugin also offers Smart Chat, which enables dynamic conversations with your notes, allowing for better information retrieval and exploration. It supports both local and cloud-based AI models, ensuring privacy and flexibility. Additionally, the plugin offers customizable settings, including note exclusions and integration with AI models like GPT-4, Gemini, and Claude. Overall, it streamlines the process of linking and managing notes, allowing for a more efficient and insightful note-taking experience.   Zero-setup: Local AI models for embeddings https://effortlessacademic.com/adding-ai-to-your-obsidian-notes-with-smartconnections-and-copilot/ 
* Obsidian AI Assistant [https://github.com/qgrail/obsidian-ai-assistant](https://github.com/qgrail/obsidian-ai-assistant) (Good Speech-To-Text)
* Whisper API [https://github.com/nikdanilov/whisper-obsidian-plugin](https://github.com/nikdanilov/whisper-obsidian-plugin)
* Mesh AI https://github.com/chasebank87/mesh-ai The Mesh AI plugin emulates the functionality provided by the [Fabric tool](https://github.com/danielmiessler/fabric) within your Obsidian vault. This plugin allows users to run and manage multiple text processing patterns on their notes, the clipboard, or Tavily search results. It integrates with various AI services and platforms to enhance your productivity within Obsidian.  https://www.youtube.com/watch?v=Q4GChPkIQg0
* I Tagger: Automatically tag your notes using AI
 * Link: [https://github.com/lucagrippa/obsidian-ai-tagger](https://github.com/lucagrippa/obsidian-ai-tagger?ref=dsebastien.net)
* AI Summary: Automatically summarize your notes
  * Link: [https://github.com/irbull/obsidian-ai-summary](https://github.com/irbull/obsidian-ai-summary?ref=dsebastien.net)
* Companion: Autocomplete using AI, including ChatGPT, and local model (e.g., via Ollama
  * Link: [https://github.com/rizerphe/obsidian-companion](https://github.com/rizerphe/obsidian-companion?ref=dsebastien.net)
* Copilot from logancyang (free) and Copilot Plus (license: $11.67 /mo [https://www.youtube.com/watch?v=tZ2jm\_UPc6c](https://www.youtube.com/watch?v=tZ2jm_UPc6c) )
* ChatGPT MD
* SystemSculpt AI  https://www.youtube.com/@SystemSculpt/playlists 

MCP Tools 
*  Local REST API for Obsidian https://github.com/coddingtonbear/obsidian-local-rest-api  (from https://www.youtube.com/watch?v=VeTnndXyJQI) 
* https://github.com/jacksteamdev/obsidian-mcp-tools  MCP Tools for Obsidian enables AI applications like Claude Desktop to securely access and work with your Obsidian vault through the Model Context Protocol (MCP). MCP is an open protocol that standardizes how AI applications can interact with external data sources and tools while maintaining security and user control.  (from https://www.youtube.com/watch?v=VeTnndXyJQI) 
* https://github.com/MarkusPfundstein/mcp-obsidian MCP server to interact with Obsidian via the Local REST API community plugin

Plugins for Visual Studio Code 
* Roo Code https://github.com/RooCodeInc/Roo-Code   **Roo Code** is an AI-powered **autonomous coding agent** that lives in your editor https://docs.roocode.com/   (from https://www.youtube.com/watch?v=qron8Myvc6w)
### Synch 

The Easiest Way to Connect Your Obsidian Vault with Github [https://linked-blog-starter.vercel.app/connect-obsidian-vault-with-github](https://linked-blog-starter.vercel.app/connect-obsidian-vault-with-github)

### References 
https://www.youtube.com/watch?v=6R3RF2CoYv8 # 33 приёма Obsidian, без которых я уже не могу работать

[https://www.dsebastien.net/2022-10-19-the-must-have-obsidian-plugins/](https://www.dsebastien.net/2022-10-19-the-must-have-obsidian-plugins/)

https://www.youtube.com/watch?v=h7P3CHuXpe4  Секрет идеальной Базы Знаний ИИ: Obsidian + Claude Code за 1 вечер

# Graph

## Draw.io

[Draw.io](http://draw.io/) или [Diagrams.net](http://diagrams.net/) — это бесплатный инструмент для создания диаграмм. С его помощью можно рисовать блок-схемы, ментальные карты, организационные структуры и многое другое. У сервиса простой интерфейс и большая библиотека шаблонов. Пользоваться им можно прямо в браузере или через приложение для Windows, macOS и Linux.

Диаграммы можно экспортировать в PNG, SVG, PDF и другие форматы. Также их можно сохранять в Google Drive, OneDrive, Dropbox, GitHub или локально на устройстве. При этом ваша работа не привязана к одному облаку, как в случае с Google Drawings, где всё хранится в Google Drive.

https://www.drawio.com/docs/security/diagrams-offline/  [draw.io Desktop](https://get.diagrams.net/) is a downloadable security-first diagramming application that runs fully offline on Windows, MacOS and Linux.
Creating diagrams in the desktop app doesn't need an internet connection. This is useful when you are disconnected or when you must create diagrams in a highly secure environment, where [data protection](https://www.drawio.com/docs/security/) is of the utmost importance.
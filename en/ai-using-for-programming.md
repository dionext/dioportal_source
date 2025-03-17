---
title: "AI. Using for programming"
description: ""
keywords: ""
lang: "en"
permalink: "ai-using-for-programming"
aliases:
  - "ai-using-for-programming"
---

# AI. Using for programming

[https://www.youtube.com/watch?v=zfOG7YCn0bE](https://www.youtube.com/watch?v=zfOG7YCn0bE) Обзор ИИ инструментов для работы и учебы [00:39](https://www.youtube.com/watch?v=zfOG7YCn0bE&t=39s) Perplexity [02:43](https://www.youtube.com/watch?v=zfOG7YCn0bE&t=163s) Gamma AI [03:32](https://www.youtube.com/watch?v=zfOG7YCn0bE&t=212s) Yippity [04:03](https://www.youtube.com/watch?v=zfOG7YCn0bE&t=243s) MathGPT [04:38](https://www.youtube.com/watch?v=zfOG7YCn0bE&t=278s) GitHub Copilot [05:51](https://www.youtube.com/watch?v=zfOG7YCn0bE&t=351s) Fig и Warp [06:58](https://www.youtube.com/watch?v=zfOG7YCn0bE&t=418s) Documatic

[https://www.youtube.com/watch?v=dn4O3nftwjA](https://www.youtube.com/watch?v=dn4O3nftwjA) Хорошо ли GPT умеет строить SQL запросы?

[https://www.youtube.com/watch?v=adJwFliSJjA](https://www.youtube.com/watch?v=adJwFliSJjA) Тест 6 ИИ программистов

[https://www.youtube.com/watch?v=x4Pe5LjUHKQ](https://www.youtube.com/watch?v=x4Pe5LjUHKQ) Is AI Coding ACTUALLY 10x Faster? \[REAL RESULTS\]

[00:11:57](https://www.youtube.com/watch?v=adJwFliSJjA&t=717s) Devika [00:13:20](https://www.youtube.com/watch?v=adJwFliSJjA&t=800s) All-hands (open hands) [00:14:19](https://www.youtube.com/watch?v=adJwFliSJjA&t=859s) Github Workspaces [00:16:30](https://www.youtube.com/watch?v=adJwFliSJjA&t=990s) Replit.com [00:18:52](https://www.youtube.com/watch?v=adJwFliSJjA&t=1132s) Cursor Composer (Cursor бесплатно по 2 недели на аккаунт) [00:20:38](https://www.youtube.com/watch?v=adJwFliSJjA&t=1238s) Aider

### Cursor Composer

#### Overview

The tool excels in Python, JavaScript, and TypeScript, but it can also be used with other popular programming languages. This versatility makes Cursor AI a valuable asset for developers who work on projects that require knowledge of multiple languages.

The free tier of Cursor is powered by GPT-3.5. Paying users can use either GPT-3.5 or GPT-4. The free plan allows you to use the AI up to 100 times a month. If you need to use more, you will have to buy a pro plan.

[https://docs.cursor.com/get-started/migrate-from-vscode](https://docs.cursor.com/get-started/migrate-from-vscode) documentation

[https://forum.cursor.com/](https://forum.cursor.com/) forum

#### Price and model

[https://docs.cursor.com/billing/billing-faq](https://docs.cursor.com/billing/billing-faq)

[https://www.cursor.com/pricing](https://www.cursor.com/pricing)

* Hobby Free Includes Pro two-week trial 2000 completions 50 slow premium requests
* Pro $20/month Everything in Hobby, plus Unlimited completions 500 fast premium requests per month ? Unlimited slow premium requests 10 o1-mini uses per day Get Started
* Business $40/user/month Everything in Pro, plus Enforce privacy mode org-wide Centralized team billing Admin dashboard with usage stats Get Started

What are the premium models? GPT-4, GPT-4o, and Claude 3.5 Sonnet are all considered premium models. You have 500 fast uses and unlimited slow uses each month for these models. Each request to Claude 3.5 Haiku counts as 1/3 of a premium request.

What are fast and slow uses? Fast uses of premium models are given first priority by our backend. On Pro, once you hit your fast usage limit, you can still use premium models, but your requests may be queued behind others at times of high load.

Usage-based Pricing

You may opt in to usage-based pricing for requests that go beyond what is included in your plan by visiting your [settings page](https://cursor.com/settings).

Usage-based pricing details:

* Usage-based pricing is per calendar month (not necessarily same as your billing cycle, will be billed roughly on the 2nd-3rd day of the month)
* If you immediately cancel a request or if it errors we do not count it
* You can configure a hard limit, and you will never ever have to pay more than the hard limit per month (for the usage-based pricing)
* Right now, usage-based pricing only applies to o1-preview, Claude 3 Opus and a few models in long context chat.

#### Settings

Cursor is compatible with VSCode extensions. All you need to do is import them automatically with Cursor. [https://medium.com/@techwriterjohn/cursor-a-i-powered-integrated-development-environment-40977ef2f011](https://medium.com/@techwriterjohn/cursor-a-i-powered-integrated-development-environment-40977ef2f011)

#### Useful commands

Ctrl- I - Open global composer

Ctrl -K - Open inline prompt in code editor

On the selection, go to the prompt and write Explain this code

You can accept a suggestion by pressing Tab, or reject it by pressing Esc. To partially accept a suggestion word-by-word, press Ctrl/⌘ →. To reject a suggestion, just keep typing, or use Escape to cancel/hide the suggestion. You can accept the next word of a suggestion by pressing Ctrl/⌘ and the right arrow (or by setting editor.action.inlineSuggest.acceptNextWord to your preferred keybinding). To enable partial accepts, navigate to Cursor Settings \> Features \> Cursor Tab.

Type @ to see context options based on your current work. Navigate with arrow keys, select with Enter, and filter by typing after @. Use Ctrl/⌘ M to switch file reading methods. @Recommended in Agent automatically pulls relevant context.

What's the difference between Chat and Composer? Cursor Chat helps you search and understand your code. Use it to explore your codebase, ask questions, and get explanations. You can search your code with ⌘⏎. Composer helps you write and edit code. It provides a workspace where you can generate new code and apply changes directly to your files.{#whats-the-difference-between-chat-and-composer}

By default, Cursor Chat includes the current file as context. You can submit a query without including any context by removing the current file pill from the message. As you type, you can see what will be included in context in the pills above the input box. ​ Adding Context By default, user messages will contain the text you type, along with the context you've referenced. You can add more custom context to each bubble with @ symbols, and by default, the current viewing file will be used as context as well in the user message.

AI Fix in Chat - A convenient feature to fix linter errors in your codebase is to use the AI fix in chat. To do this, hover over the error in the editor, and click the blue AI fix button that shows up.

In the built-in Cursor terminal, you can press Ctrl/⌘ K to open a prompt bar on the bottom of the terminal. This prompt bar allows you to describe your desired action in the terminal, and terminal Cmd K will generate a command. You can accept the command by hitting esc or run the command immediately with Ctrl/⌘ + Enter.

#### Codebase Indexing

[https://docs.cursor.com/context/codebase-indexing](https://docs.cursor.com/context/codebase-indexing)  
[​](https://docs.cursor.com/context/codebase-indexing#index-your-codebase)  
Index your Codebase

For better and more accurate codebase answers using @codebase or Ctrl/⌘ Enter, you can index your codebase. Behind the scenes, Cursor computes embeddings for each file in your codebase, and will use these to improve the accuracy of your codebase answers.

Your codebase index will automatically synchronize with your latest codebase changes.

The status of your codebase indexing is under Cursor Settings \> Features \> Codebase Indexing.

#### How does Cursor behave with large projects?

I'm using cursor on a 460k line .net application with two different .NET languages, xUnit, JSON, images etc. It's a monster. I was surprised but cursor can index the entire project and analyze it very accurately . I use the paid Anthropic Sonnent 3.5 API access when I need cursor to dive deep in the code and it works great. Cursor can handle huge projects, I was very surprised, it works better than I expected. It's a huge time saver and it tells me what parts of the application do when I've never even seen the code. I'm new to the codebase and cursor has been a massive help. I recommend it for large projects but I would use Anthropic OPUS or Sonnet or even the preview open AI o1 model when digging deep into large projects looking for specific logic. Generally the free models that come with a cursor subscription are enough but if you're a professional developer paying $2-$3 for fast access to the most accurate models is worth it. You can toggle the advanced paid models on and off as you work to save money. I'm just a customer but I highly recommend cursor even for huge codebase. It's well worth it.

#### References

[https://www.youtube.com/watch?v=ocMOZpuAMw4](https://www.youtube.com/watch?v=ocMOZpuAMw4&t=18s) Cursor Tutorial for Beginners (AI Code Editor) (Express.js)

[https://www.youtube.com/watch?v=gDzND0M6SGE](https://www.youtube.com/watch?v=gDzND0M6SGE) Cursor Tutorial for Beginners (AI Code Editor)

[https://www.youtube.com/watch?v=mxX1TYrhPFo](https://www.youtube.com/watch?v=mxX1TYrhPFo) How I built a REAL Full Stack App in 5hr using Cursor ([Volo](https://www.youtube.com/@VoloBuilds))

[https://www.youtube.com/watch?v=yk9lXobJ95E](https://www.youtube.com/watch?v=yk9lXobJ95E) Cursor AI Tutorial for Beginners (How I Code 159% Faster) ([Volo](https://www.youtube.com/@VoloBuilds))

[https://www.youtube.com/watch?v=ctn3mvDo22E](https://www.youtube.com/watch?v=ctn3mvDo22E) New Cursor Agents - game changer or flop? ([Volo](https://www.youtube.com/@VoloBuilds))

[https://www.youtube.com/watch?v=CqkZ-ybl3lg](https://www.youtube.com/watch?v=CqkZ-ybl3lg) Get Started with Cursor - The AI Code Editor

[https://www.youtube.com/watch?v=cs4kgngIn3w](https://www.youtube.com/watch?v=cs4kgngIn3w) Cursor для управления знаниями. AI Mindset \[podcast\] AI Mindset Podcast \[002\]: Cursor для управления знаниями -- Cursor - это мощный редактор кода с интегрированным ИИ, который упрощает разработку. Он легко интегрируется с такими инструментами, как Obsidian, поддерживает Markdown и может использоваться для эффективного управления знаниями. Cursor позволяет задавать запросы к заметкам, анализировать их, настраивать предпочтения для проектов и создавать связи между источниками данных. Благодаря своей гибкости и скорости работы, это универсальный инструмент как для программирования, так и для работы с контентом. (Obsidian is a personal knowledge base and note-taking software application that operates on Markdown files.\[3\]\[4\]\[5\] It allows users to make internal links for notes and then to visualize the connections as a graph.\[6\]\[7\] It is designed to help users organize and structure their thoughts and knowledge in a flexible, non-linear way.\[8\] The software is free for personal use, with paid commercial licenses available )

#### Alternative

[https://www.youtube.com/watch?v=ucalLC8k94w\&t=8s](https://www.youtube.com/watch?v=ucalLC8k94w&t=8s) VSCode + ClaudeDev + Continue : STOP PAYING for CURSOR with this OPENSOURCE \& LOCAL Alternative

### GitHub Copilot

(Not available in some geographic regions )

[https://github.com/copilot](https://github.com/copilot) Online

Plugins for VSC, Idea, etc.

In VSC you can use [https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-speech](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-speech) (In Cursor not works?)

GitHub Copilot is a [code completion](https://en.wikipedia.org/wiki/Code_completion "Code completion") and [automatic programming](https://en.wikipedia.org/wiki/Automatic_programming "Automatic programming") tool developed by [GitHub](https://en.wikipedia.org/wiki/GitHub "GitHub") and [OpenAI](https://en.wikipedia.org/wiki/OpenAI "OpenAI") that assists users of [Visual Studio Code](https://en.wikipedia.org/wiki/Visual_Studio_Code "Visual Studio Code"), [Visual Studio](https://en.wikipedia.org/wiki/Visual_Studio "Visual Studio"), [Neovim](https://en.wikipedia.org/wiki/Neovim "Neovim"), and [JetBrains](https://en.wikipedia.org/wiki/JetBrains "JetBrains") [integrated development environments](https://en.wikipedia.org/wiki/Integrated_development_environment "Integrated development environment") (IDEs) by [autocompleting](https://en.wikipedia.org/wiki/Autocomplete "Autocomplete") code.[\[1\]](https://en.wikipedia.org/wiki/GitHub_Copilot#cite_note-:0-1) Currently available by subscription to individual developers and to businesses, the [generative artificial intelligence](https://en.wikipedia.org/wiki/Generative_artificial_intelligence "Generative artificial intelligence") software was first announced by GitHub on 29 June 2021, and works best for users coding in [Python](<https://en.wikipedia.org/wiki/Python_(programming_language)> "Python (programming language)"), [JavaScript](https://en.wikipedia.org/wiki/JavaScript "JavaScript"), [TypeScript](https://en.wikipedia.org/wiki/TypeScript "TypeScript"), [Ruby](<https://en.wikipedia.org/wiki/Ruby_(programming_language)> "Ruby (programming language)"), and [Go](<https://en.wikipedia.org/wiki/Go_(programming_language)> "Go (programming language)").[\[2\]](https://en.wikipedia.org/wiki/GitHub_Copilot#cite_note-:2-2) In March 2023 GitHub announced plans for "Copilot X", which will incorporate a [chatbot](https://en.wikipedia.org/wiki/Chatbot "Chatbot") based on [GPT-4](https://en.wikipedia.org/wiki/GPT-4 "GPT-4"), as well as support for voice commands, into Copilot.[\[3\]](https://en.wikipedia.org/wiki/GitHub_Copilot#cite_note-3)

[https://github.com/features/copilot](https://github.com/features/copilot)

What's included (free):

* 2,000 intelligent code completions a month: Get context-aware code suggestions that draw context from your GitHub projects and VS Code workspace.
* 50 Copilot Chat messages a month: Ask Copilot for help understanding code, refactoring something, or debugging an issue.
* Choose your AI model: Pick between Claude 3.5 Sonnet or OpenAI GPT-4o.
* Make changes to multiple files with Copilot Edits: Tackle changes across multiple files with Copilot Edits.
* Support for the Copilot Extensions ecosystem: Access third-party agents designed for tasks such as querying Stack Overflow or searching the web with Perplexity.
* Choose where you build: Enjoy support in VS Code and across GitHub.

### IDE WindSurf

[https://www.youtube.com/watch?v=YcWve8i9lLI](https://www.youtube.com/watch?v=YcWve8i9lLI) IDE WindSurf: код от AI на реальном проекте! Подойдет новичку? Плюсы и минусы ИИ-редактора.

Пользовался последние две недели Windsurf - всё круто, примерно, как Cursor, но приятней дизайн (да и вообще его сделали в коллаборации создатели Codeium и Cursor), но именно сегодня Codeium, а соответственно и Windsurf, отказались работать в рф, так что пришлось вернуться на Curso

### v0.dev

[https://v0.dev/](https://v0.dev/) v0 begins with a chat-based interface, where users can input prompts and attach files. v0 can respond with text, code, or Blocks. [https://habr.com/ru/articles/875442/](https://habr.com/ru/articles/875442/) Comparing AI Prototyping Tools: v0, Bolt, and Lovable

### Aide.dev

[https://aide.dev/](https://aide.dev/)

[https://www.youtube.com/watch?v=Kevt1-EgpN4](https://www.youtube.com/watch?v=Kevt1-EgpN4) AIDE.dev: FREE AI Code Editor - Full Stack AI Code Editor On The web! Cursor AI Alternative

### Aider

[https://aider.chat/](https://aider.chat/) Aider is AI pair programming in your terminal Aider lets you pair program with LLMs, to edit code in your local git repository. Start a new project or work with an existing git repo. Aider works best with GPT-4o \& Claude 3.5 Sonnet and can connect to almost any LLM.

### Machinet

[https://plugin.machinet.net/?utm\_source=baeldung\&utm\_campaign=NPI\&utm\_content=npiea3#pricing](https://plugin.machinet.net/?utm_source=baeldung&utm_campaign=NPI&utm_content=npiea3#pricing)

AI assistant for developers Boost your productivity with Machinet. Experience the power of AI-assisted coding and automated unit test generation. Download the plugin for JetBrains now

### IBM watsonx Code Assistant

et started with the IBM watsonx Code Assistant: [https://obvs.ly/tech-with-tim](https://www.youtube.com/redirect?event=comments&redir_token=QUFFLUhqbkxYME85ZFExNW9vTk5qTGNWNWFvcmtLYkRLZ3xBQ3Jtc0tsTDBobGpTWWtGQWNaeGg0UmVCc2t5STRUSTE3dkVvdWVleDJQaWNVbnpvUnBrWl85Q2FWb2dza1NlZ2gwbS1NQkZPV3hMWk14eTZQdHBWYUFtZHVLdUM5MDlpQTRDSlVFbjRrSWdXTGszNmNuNEplQQ&q=https%3A%2F%2Fobvs.ly%2Ftech-with-tim)

[https://www.youtube.com/watch?v=becL7\_JrHSo](https://www.youtube.com/watch?v=becL7_JrHSo)

### Claude Code

[https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview)

### Cline

[https://cline.bot/](https://cline.bot/) Plugin for VSC [https://www.youtube.com/watch?v=nhK89Qc0\_UE](https://www.youtube.com/watch?v=nhK89Qc0_UE) (ru)

### Warp

[https://www.warp.dev/](https://www.warp.dev/) The intelligent terminal. Become a command line power user on day one. Warp combines AI and your dev team's knowledge in one fast, intuitive terminal.

### Gemini Code Assist (Google)

(Not available in some geographic regions )

[https://codeassist.google/](https://codeassist.google/) (For Visual Studio Code)

[https://www.youtube.com/watch?v=dGtMdl1fnz0](https://www.youtube.com/watch?v=dGtMdl1fnz0) (ru)

## References

[https://www.youtube.com/watch?v=XbSTRweCcg8](https://www.youtube.com/watch?v=XbSTRweCcg8) Build Home Assistant Automations in Seconds! with AI

[https://www.youtube.com/watch?v=J-vxmg\_kQVU](https://www.youtube.com/watch?v=J-vxmg_kQVU) (ru) Testing 13 BEST neural networks in a real developer task

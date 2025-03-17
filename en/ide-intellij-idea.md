---
title: "IntelliJ IDEA"
description: "Using IntelliJ IDEA"
keywords: "IntelliJ, IDEA, IDE"
lang: "en"
permalink: "ide-intellij-idea"
aliases:
  - "ide-intellij-idea"
---

# {\#id6}IntelliJ IDEA

## Overview

[https://www.jetbrains.com/idea/](https://www.jetbrains.com/idea/)

IntelliJ IDEA is an integrated development environment (IDE) written in Java for developing computer software written in Java, Kotlin, Groovy, and other JVM-based languages. It is developed by JetBrains (formerly known as IntelliJ) and is available as an Apache 2 Licensed community edition, and in a proprietary commercial edition. Both can be used for commercial development. [https://en.wikipedia.org/wiki/IntelliJ\_IDEA](https://en.wikipedia.org/wiki/IntelliJ_IDEA)

Comparison: IntelliJ IDEA Ultimate vs IntelliJ IDEA Community Edition

[https://www.jetbrains.com/products/compare/?product=idea\&product=idea-ce](https://www.jetbrains.com/products/compare/?product=idea&product=idea-ce)

[https://portapps.io/app/intellij-idea-community-portable/](https://portapps.io/app/intellij-idea-community-portable/) Portable IntelliJ IDEA Community Edition

## Useful settings

Set UTF-8 for Project and properties files

Enable toolbar for use "Back" button. In the main menu select View \> Appearance and enable Toolbar. It has the back/forward buttons. Right mouse click on Toolbar -\> Add To Main Toolbar

Set new JDK: File \> Project Structure (ctrl+alt+shift+s) - SDKs. - JDK.

## Useful plugins

The Docker plugin is available by default only in IntelliJ IDEA Ultimate. For IntelliJ IDEA Community Edition, you need to install the Docker plugin as described in [Install plugins](https://www.jetbrains.com/help/idea/2022.3/managing-plugins.html).

JPA Buddy - working with databases (proprietary)

Database Navigator - working with databases

EnvFile - is a plugin for JetBrains IDEs that allows you to set environment variables for your run configurations from one or multiple files. [https://plugins.jetbrains.com/plugin/7861-envfile](https://plugins.jetbrains.com/plugin/7861-envfile)

[https://plugins.jetbrains.com/plugin/17718-github-copilot](https://plugins.jetbrains.com/plugin/17718-github-copilot)

[https://plugins.jetbrains.com/plugin/22635-speech-to-text-aws-transcribe-/pricing](https://plugins.jetbrains.com/plugin/22635-speech-to-text-aws-transcribe-/pricing) first year US $ 10.00 per year

## Fonts

To configure the font used in the IntelliJ IDEA interface (tool windows, toolbars, menus, and so on), open the IDE settings Ctrl+Alt+S, and go to Appearance \& Behavior | Appearance. From the Use custom font list, select a font and specify the font size in the Size field.{#ca0e2433}

* The default font size is set on the Editor | Font page of the IDE settings Ctrl+Alt+S. It will be used in the editor by for all newly opened documents, unless overridden in the current [color scheme](https://www.jetbrains.com/help/rider/Configuring_Colors_and_Fonts.html){#50749ebc}.{#d7ba49}
  
  {#da6a018c}
  {#da6a018c}

{#283d9f98}

[Use Ctrl/Cmd+mouse wheel to change font size in the current document﻿](https://www.jetbrains.com/help/rider/Zooming_in_the_Editor.html#use-ctrl-cmd-mouse-wheel-to-change-font-size-in-the-current-document)

1. Press Ctrl+Alt+S to open the IDE settings and select Editor | General.{#b9c19088}

2. Select Change font size with Ctrl/Cmd+Mouse Wheel in:{#a56bf9b5}

3. Choose Active editor below that checkbox.{#edbcb969}

4. Now you can press Ctrl and while holding it, rotate the mouse wheel to increase or decrease the font size in the current document.

5. If you close and reopen the document, the font size will be reset to the default font or to the color scheme font according to your settings.

## Show non-printable characters

[https://intellij-support.jetbrains.com/hc/en-us/community/posts/207045165-Show-non-printable-characters-Tabs](https://intellij-support.jetbrains.com/hc/en-us/community/posts/207045165-Show-non-printable-characters-Tabs)

* View | Active Editor | Show Whitespaces -- affects current tab only
* Settings | Editor | General | Appearance --\> Show whitespaces -- affects all (newly opened) tabs

## Executing bash scripts

[https://www.jetbrains.com/help/idea/shell-scripts.html#shell-scripts-configurations](https://www.jetbrains.com/help/idea/shell-scripts.html#shell-scripts-configurations)

[https://www.cyberciti.biz/faq/linux-unix-osx-bsd-ssh-run-command-on-remote-machine-server/](https://www.cyberciti.biz/faq/linux-unix-osx-bsd-ssh-run-command-on-remote-machine-server/) How To Run Multiple SSH Command On Remote Machine And Exit Safely [https://stackoverflow.com/questions/4412238/what-is-the-cleanest-way-to-ssh-and-run-multiple-commands-in-bash](https://stackoverflow.com/questions/4412238/what-is-the-cleanest-way-to-ssh-and-run-multiple-commands-in-bash) What is the cleanest way to ssh and run multiple commands in Bash?

## Working with docker

[https://www.jetbrains.com/help/idea/docker.html#connect\_to\_docker](https://www.jetbrains.com/help/idea/docker.html#connect_to_docker)

## Using Lombok

[https://www.baeldung.com/lombok-ide#intellij-apt](https://www.baeldung.com/lombok-ide#intellij-apt) Setting up Lombok with Eclipse and Intellij

Our experience:

you may get problem with ...m2\\repository\\org\\projectlombok\\lombok\\unknown\\lombok-unknown.jar

To avoid that - use exact version of Lombok or do not use annotationProcessorPaths in maven-compiler-plugin

[https://youtrack.jetbrains.com/issue/IDEA-332869/Incompatible-Lombok-version-leads-to-error-NoSuchFieldError-com.sun.tools.javac.tree.JCTree-qualid-during-project-compilation](https://youtrack.jetbrains.com/issue/IDEA-332869/Incompatible-Lombok-version-leads-to-error-NoSuchFieldError-com.sun.tools.javac.tree.JCTree-qualid-during-project-compilation)

Upgrade Lombok to the compatible version. JDK21 - Lombok 1.18.30 JDK22 - Lombok 1.18.32

## AI Assistant

[https://www.jetbrains.com/ai/](https://www.jetbrains.com/ai/)

[https://www.youtube.com/watch?v=yAxLR1YPwyQ](https://www.youtube.com/watch?v=yAxLR1YPwyQ) Build a Spring Boot app with AI Assistant

## References

[https://www.youtube.com/watch?v=sSoS6edODWM](https://www.youtube.com/watch?v=sSoS6edODWM) Artyom Zaitsev "Write code quickly and easily with Intellij IDEA" (lang: rus)

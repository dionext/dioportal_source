---
title: "Visual Studio Code"
description: "Using Visual Studio Code"
keywords: "Visual Studio Code"
lang: "en"
permalink: "ide-visual-studio-code"
aliases:
  - "ide-visual-studio-code"
---

# {\#id5}Visual Studio Code

## Overview

[https://code.visualstudio.com/](https://code.visualstudio.com/)

Visual Studio Code, also commonly referred to as VS Code,\[9\] is a source-code editor developed by Microsoft for Windows, Linux and macOS.\[10\] Features include support for debugging, syntax highlighting, intelligent code completion, snippets, code refactoring, and embedded Git. Users can change the theme, keyboard shortcuts, preferences, and install extensions that add functionality. [https://en.wikipedia.org/wiki/Visual\_Studio\_Code](https://en.wikipedia.org/wiki/Visual_Studio_Code)

Beginning as an experiment, the code editor has evolved over this time into a new cross-platform development tool that perfectly complements the entire history of the platform for creating software using Visual Studio. Visual Studio Code now provides advanced editing, navigation, debugging, and native Git support. You can download and install Visual Studio Code 1.0 for Windows, Linux and OS X operating systems.

## Useful settings

Selecting the Color Theme · In VS Code, open the Color Theme picker with File \> Preferences \> Theme \> Color Theme.

CMD for launching on weak computers: --disable-gpu

## Useful plugins

* VSCode Google Translate
* Project manager
* Setting sync - to store settings on Gitlab
* vscode-solution-explorer
* NuGet Package Manager
* Visual Studio IntelliCode
* Spring Boot Extension Pack VMware

## Dev Containers

[https://code.visualstudio.com/docs/remote/containers](https://code.visualstudio.com/docs/remote/containers)

The Visual Studio Code Dev Containers extension lets you use a container as a full-featured development environment. It allows you to open any folder inside (or mounted into) a container and take advantage of Visual Studio Code's full feature set. A devcontainer.json file in your project tells VS Code how to access (or create) a development container with a well-defined tool and runtime stack. This container can be used to run an application or to separate tools, libraries, or runtimes needed for working with a codebase.

You can use the Visual Studio Code Dev Containers extension to develop in a Docker container  
It is possible to create remote work sessions through the plugin [Remote-SSH extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh) [https://code.visualstudio.com/docs/remote/ssh](https://code.visualstudio.com/docs/remote/ssh)

* A container is launched into which extensions and a special server are installed, which allows the front-end to interact with the container over the network.
* The selected folder is mounted in the container, that is, any changes to files inside the container occur with files located on the file system of your operating system.
* All processes associated working with code, formatting and debugging are run inside the container.

## Spring boot application

Spring Boot Extension Pack VMware [https://marketplace.visualstudio.com/items?itemName=vmware.vscode-boot-dev-pack](https://marketplace.visualstudio.com/items?itemName=vmware.vscode-boot-dev-pack)

[https://kastroud.hashnode.dev/adding-env-variables-to-your-spring-boot-project-on-vs-code](https://kastroud.hashnode.dev/adding-env-variables-to-your-spring-boot-project-on-vs-code)

To setup VS Code for using Java and Spring Boot have a look at these links

1. [https://code.visualstudio.com/docs/languages/java](https://code.visualstudio.com/docs/languages/java)

2. [https://code.visualstudio.com/docs/java/java-tutorial](https://code.visualstudio.com/docs/java/java-tutorial)

3. [https://code.visualstudio.com/docs/java/java-spring-boot](https://code.visualstudio.com/docs/java/java-spring-boot)

To add Environment variables to your java project in vs code there are two methods

Visual Studio Code is an ideal lightweight development environment for Spring Boot application developers and there are several useful VS Code extensions including:

* [Spring Boot Tools](https://marketplace.visualstudio.com/items?itemName=vmware.vscode-spring-boot)
* [Spring Initializr](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-spring-initializr)
* [Spring Boot Dashboard](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-spring-boot-dashboard)

We recommend installing the [Spring Boot Extension Pack](https://marketplace.visualstudio.com/items?itemName=vmware.vscode-boot-dev-pack) that includes all of the extensions above.

### Env

Add env files in launch.json{#heading-add-env-files-in-launchjson}

opening run -\> add configuration. This will create a launch.json file in the .vscode folder  
"envFile": "${workspaceFolder}/.env"

### Create application

open the Command Palette (Ctrl+Shift+P) and type Spring Initializr to start generating a Maven or Gradle project and then follow the wizard.

### Run the application

In addition to using F5 to run your application, there's the Spring Boot Dashboard extension, which lets you view and manage all available Spring Boot projects in your workspace as well as quickly start, stop, or debug your project.

Alt

./mvnw spring-boot:run

mvn spring-boot:run

java -jar target/app-0.0.1-SNAPSHOT.jar

java -jar target/idea-ms-app-1.0.0.jar 'com.dionext.MainMsAppApplication'

## References

[https://www.youtube.com/watch?v=y-JNavSnjkQ](https://www.youtube.com/watch?v=y-JNavSnjkQ) Development Tools: Coding Spring Boot Applications in Visual Studio Code Microsoft Developer

[https://learn.microsoft.com/en-us/training/modules/use-docker-container-dev-env-vs-code/](https://learn.microsoft.com/en-us/training/modules/use-docker-container-dev-env-vs-code/)

[https://habr.com/ru/companies/ruvds/articles/717110/](https://habr.com/ru/companies/ruvds/articles/717110/)

[https://dev.to/rnds/dev-containers-vskrytiie-20o3](https://dev.to/rnds/dev-containers-vskrytiie-20o3)

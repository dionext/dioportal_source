---
title: "React"
description: ""
keywords: ""
lang: "en"
permalink: "frontend-react"
aliases:
  - "frontend-react"
---

# React

## Overview

[https://en.wikipedia.org/wiki/React\_(software](<https://en.wikipedia.org/wiki/React_(software>))

React (also known as React.js or ReactJS) is a free and open-source front-end JavaScript library that aims to make building user interfaces based on components more "seamless". It is maintained by Meta (formerly Facebook) and a community of individual developers and companies. React can be used to develop single-page, mobile, or server-rendered applications with frameworks like Next.js and Remix\[a\]. Because React is only concerned with the user interface and rendering components to the DOM, React applications often rely on libraries for routing and other client-side functionality. A key advantage of React is that it only re-renders those parts of the page that have changed, avoiding unnecessary re-rendering of unchanged DOM elements.

[https://en.wikipedia.org/wiki/Node.js](https://en.wikipedia.org/wiki/Node.js)

Node.js is a cross-platform, open-source JavaScript runtime environment that can run on Windows, Linux, Unix, macOS, and more. Node.js runs on the V8 JavaScript engine, and executes JavaScript code outside a web browser. Node.js lets developers use JavaScript to write command line tools and for server-side scripting. The ability to run JavaScript code on the server is often used to generate dynamic web page content before the page is sent to the user's web browser. Consequently, Node.js represents a "JavaScript everywhere" paradigm,\[6\] unifying web-application development around a single programming language, as opposed to using different languages for the server- versus client-side programming.

[https://en.wikipedia.org/wiki/TypeScript](https://en.wikipedia.org/wiki/TypeScript)

TypeScript (abbreviated as TS) is a free and open-source high-level programming language developed by Microsoft that adds static typing with optional type annotations to JavaScript. It is designed for the development of large applications and transpiles to JavaScript.\[6\] TypeScript may be used to develop JavaScript applications for both client-side and server-side execution (as with Node.js, Deno or Bun). Multiple options are available for transpilation. The default TypeScript Compiler can be used,\[7\] or the Babel compiler can be invoked to convert TypeScript to JavaScript.

[https://en.wikipedia.org/wiki/Npm](https://en.wikipedia.org/wiki/Npm)

npm is a package manager for the JavaScript programming language maintained by npm, Inc., a subsidiary of GitHub. npm is the default package manager for the JavaScript runtime environment Node.js and is included as a recommended feature in the Node.js installer.\[4\] It consists of a command line client, also called npm, and an online database of public and paid-for private packages, called the npm registry. The registry is accessed via the client, and the available packages can be browsed and searched via the npm website. The package manager and the registry are managed by npm, Inc.

Alternative package manager [https://yarnpkg.com/](https://yarnpkg.com/) Yarn is a package manager that doubles down as project manager. Whether you work on simple projects or industry monorepos, whether you're an open source developer or an enterprise user, Yarn has your back.

[https://en.wikipedia.org/wiki/Tailwind\_CSS](https://en.wikipedia.org/wiki/Tailwind_CSS)

Tailwind CSS is an open-source CSS framework. Unlike other frameworks, like Bootstrap, it does not provide a series of predefined classes for elements such as buttons or tables. Instead, it creates a list of "utility" CSS classes that can be used to style each element by mixing and matching.\[5\]\[6\] For example, in other traditional systems, there would be a class message-warning that would apply a yellow background color and bold text. To achieve this result in Tailwind, one would have to apply a set of classes created by the library: bg-yellow-300 and font-bold.

[https://lucide.dev/guide/](https://lucide.dev/guide/)

What is Lucide? Lucide is an open-source icon library that provides 1000+ vector (svg) files for displaying icons and symbols in digital and non-digital projects. The library aims to make it easier for designers and developers to incorporate icons into their projects by providing several official packages to make it easier to use these icons in your project.

[https://en.wikipedia.org/wiki/Vite\_(software](<https://en.wikipedia.org/wiki/Vite_(software>))

Vite (French: \[vit\], like "veet") is a local development server written by Evan You,\[1\] the creator of Vue.js, and used by default by Vue and for React project templates. It has support for TypeScript and JSX. It uses Rollup and esbuild internally for bundling.\[2\] It monitors files as they're being edited and upon file save the web browser reloads the code being edited through a process called Hot Module Replacement (HMR)\[3\] which works by just reloading the specific file being changed using ES6 modules (ESM) instead of recompiling the entire application. Vite provides built-in support for server-side rendering (SSR). By default, it listens on TCP port 5173. It is possible to configure Vite to serve content over HTTPS and proxy requests (including WebSocket) to a back-end web server (such as Apache HTTP Server or lighttpd).

[https://liquidhub.ru/blogs/blog/vite-js](https://liquidhub.ru/blogs/blog/vite-js)

ShadCN UI - Beautifully designed components that you can copy and paste into your apps. Made with Tailwind CSS. Open source. [https://ui.shadcn.com/](https://ui.shadcn.com/) [https://habr.com/ru/companies/timeweb/articles/781346/](https://habr.com/ru/companies/timeweb/articles/781346/)

[https://en.wikipedia.org/wiki/Redux\_(JavaScript\_library](<https://en.wikipedia.org/wiki/Redux_(JavaScript_library>))

Redux is an open-source JavaScript library for managing and centralizing application state. It is most commonly used with libraries such as React or Angular for building user interfaces. Similar to (and inspired by) Facebook's Flux architecture, [https://redux.js.org/](https://redux.js.org/)

## Installation

[https://nodejs.org/en/download/](https://nodejs.org/en/download/)

Check

node -v

npm -v

npm view react version

npm install web-vitals ( [https://stackoverflow.com/questions/65396568/react-js-npm-start-shows-failed-to-compile-web-vitals](https://stackoverflow.com/questions/65396568/react-js-npm-start-shows-failed-to-compile-web-vitals) )

## Working with projects

npx create-react-app front-app

cd front-app

npm start

You can use Ctrl + c to stop running the React app in your command line.

npm run dev For most React projects (especially if using Vite), this will start a development server, typically at http://localhost:5173/

npm init (create simple serverside app)

## React base knowledge

React is a JavaScript library for building user interfaces, particularly single-page applications. It was developed and is maintained by Facebook (now Meta) and a community of individual developers and companies.

Key concepts in React include:

* **Components:** React applications are built using components, which are reusable pieces of UI that manage their own content, presentation, and behavior.
* **JSX:** A syntax extension for JavaScript that allows you to write HTML-like code within JavaScript files.
* **Props:** Short for properties, props are how components pass data to each other.
* **State:** The data that determines how a component renders and behaves.
* **Virtual DOM:** React's mechanism for updating the UI efficiently by maintaining a lightweight copy of the actual DOM.

A simple React component example:

    function Welcome(props) {
      return <h1>Hello, {props.name}</h1>;
    }

## Additional resources

Check out this free resource from HubSpot that contains tons of coding snippets and templates: [https://clickhubspot.com/v5ox](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqa1hiSzhBcXVTRjBZeTFLN21KMmxzT2kwczB3d3xBQ3Jtc0tuUlp4RVA4T3Y5Y3kyb205UzBkS0plMXFFdDBZRVY4Z0dOVTJDY245V3VWWmNmRmFsU1M4YkpBMHdXSWROM0N1OTY5dnhZcDNtYVNDUWxST3JGbHgtbmY4YllySU9QcmlGbjNFZUFqSllDVWJrWVF1SQ&q=https%3A%2F%2Fclickhubspot.com%2Fv5ox&v=G6D9cBaLViA)

[https://github.com/remix-run/react-router#readme](https://github.com/remix-run/react-router#readme) [https://reactrouter.com/home](https://reactrouter.com/home) [https://www.npmjs.com/package/react-router-dom](https://www.npmjs.com/package/react-router-dom) React Router is a multi-strategy router for React bridging the gap from React 18 to React 19. You can use it maximally as a React framework or minimally as a library with your own architecture.

## Adding Bootstrap for Styling {\#adding-bootstrap-for-styling}

Add Bootstrap's CSS file to your React project to make your user interfaces look more appealing. This can be done by installing Bootstrap via npm and importing it into your React app.  
npm install bootstrap

alt  
npm i bootstrap@5 react-cookie@4 react-router-dom@6 [reactstrap@9](mailto:reactstrap@9)

Then, in your index.js or App.js file, add the following import statement:  
import 'bootstrap/dist/css/bootstrap.min.css';

```

```

[https://reactstrap.github.io/?path=/story/home-installation--page](https://reactstrap.github.io/?path=/story/home-installation--page) Reactstrap is a React component library for Bootstrap Reactstrap is currently compatible with Bootstrap 5.1. If you are using Bootstrap 4, you'll need to use Reactstrap v8  
[https://www.dhiwise.com/post/reactstrap-essentials-building-responsive-uis](https://www.dhiwise.com/post/reactstrap-essentials-building-responsive-uis) Reactstrap is a go-to library for integrating Bootstrap with React applications. It provides stateless React components for Bootstrap 5, allowing developers to use Bootstrap components as React components. This integration is key for those looking to build responsive, mobile-first projects on the web with the most popular front-end component library.

## Spring boot application integration

[https://www.youtube.com/watch?v=CADL467E2wI](https://www.youtube.com/watch?v=CADL467E2wI) Spring boot \& Websockets | ReactJs: Build Full-Stack Real-Time Chat App From Scratch \[2025\]

[https://www.baeldung.com/spring-boot-react-crud](https://www.baeldung.com/spring-boot-react-crud) CRUD Application With React and Spring Boot

[https://www.dhiwise.com/post/a-step-by-step-guide-to-implementing-react-spring-boot](https://www.dhiwise.com/post/a-step-by-step-guide-to-implementing-react-spring-boot)

You can use the frontend-maven-plugin to automate this process in a Maven-based Spring Boot project. This plugin will install Node and npm, run the build script for your React app, and copy the build artifacts to the src/main/resources/static directory in your Spring Boot project.

npx create-react-app front-app

cd front-app

to fix some errors

npm install web-vitals

npm install @testing-library/react@latest

npm install --save-dev @testing-library/user-event @testing-library/dom

install additional components

```
npm install --save bootstrap@5.3.3 react-cookie@4.1.1 react-router-dom@5.3.0 reactstrap@8.10.0
```

```
npm install --save bootstrap@latest react-cookie@latest react-router-dom@latest reactstrap@latest
```

Let's add Bootstrap's CSS file as an import in app/src/index.js:

```
import 'bootstrap/dist/css/bootstrap.min.css';
```

Configure proxy for development mode

For that, we'll include the URL for our API in package.json:

"proxy": "http://localhost:8080",

to start app in dev mode

npm start

Additional reference: [https://react.dev/learn/add-react-to-an-existing-project](https://react.dev/learn/add-react-to-an-existing-project) Add React to an Existing Project

## Deploying to production

npm run build

[https://github.com/eirslett/frontend-maven-plugin](https://github.com/eirslett/frontend-maven-plugin) This plugin downloads/installs Node and NPM locally for your project, runs npm install

+ maven-resources-plugin

[https://habr.com/ru/articles/735274/](https://habr.com/ru/articles/735274/) сомнительный вариант с разворчиванием собственного сервера React в отдельном контейнере и коммуникации между ними по внутриконтейнерному адресу

## References

[https://www.youtube.com/watch?v=G6D9cBaLViA](https://www.youtube.com/watch?v=G6D9cBaLViA) Learn React With This ONE Project - Tech With Tim

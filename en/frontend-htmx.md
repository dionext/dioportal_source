---
title: "HTMX"
description: ""
keywords: ""
lang: "en"
permalink: "frontend-htmx"
aliases:
  - "frontend-htmx"
---

# HTMX

## Overview

[https://htmx.org/](https://htmx.org/) htmx gives you access to AJAX, CSS Transitions, WebSockets and Server Sent Events directly in HTML, using attributes, so you can build modern user interfaces with the simplicity and power of hypertext htmx is small (~14k min.gz'd), dependency-free, extendable \& has reduced code base sizes by 67% when compared with react

## Some examples

### Click to Load

[https://htmx.org/examples/click-to-load/](https://htmx.org/examples/click-to-load/)

This example shows how to implement click-to-load the next page in a table of data. The crux of the demo is the final row:

```
<tr id="replaceMe">
  <td colspan="3">
    <button class='btn primary' hx-get="/contacts/?page=2"
                        hx-target="#replaceMe"
                        hx-swap="outerHTML">
         Load More Agents... <img class="htmx-indicator" src="/img/bars.svg">
    </button>
  </td>
</tr>
```

This row contains a button that will replace the entire row with the next page of results (which will contain a button to load the next page of results). And so on.

## References

[https://www.youtube.com/watch?v=cjL0n1NApRA](https://www.youtube.com/watch?v=cjL0n1NApRA) Getting started with HTMX in Spring Boot with Thymeleaf [https://github.com/danvega/hello-htmx](https://github.com/danvega/hello-htmx)

[https://www.youtube.com/watch?v=kFksiDRZ824](https://www.youtube.com/watch?v=kFksiDRZ824) Building a Dynamic Task Manager with Spring Boot, JTE, and HTMX [https://github.com/danvega/jte-tasks](https://github.com/danvega/jte-tasks)

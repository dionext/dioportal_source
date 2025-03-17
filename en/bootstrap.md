---
title: "Bootstrap"
description: "Using Bootstrap CSS framework for front-end web development"
keywords: "Bootstrap, CSS, framework"
lang: "en"
permalink: "bootstrap"
aliases:
  - "bootstrap"
---


# Bootstrap

## Overview

Bootstrap is a free and open-source CSS framework directed at responsive, mobile-first front-end web development. It contains HTML, CSS and JavaScript-based design templates for typography, forms, buttons, navigation, and other interface components. [https://en.wikipedia.org/wiki/Bootstrap\_(front-end\_framework](<https://en.wikipedia.org/wiki/Bootstrap_(front-end_framework>))

Official site: [https://getbootstrap.com/](https://getbootstrap.com/)

## Installation

Include via CDN

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">
```

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL" crossorigin="anonymous"></script>

Bootstrap uses modern CSS and HTML developments, so you need to be careful when supporting older browsers. Supported browsers [https://getbootstrap.com/docs/5.3/getting-started/browsers-devices/](https://getbootstrap.com/docs/5.3/getting-started/browsers-devices/)

## Themes

[https://themes.getbootstrap.com/guide/](https://themes.getbootstrap.com/guide/) Guide

Bootstrap Themes Shops

[https://themes.getbootstrap.com/](https://themes.getbootstrap.com/)

[https://themeforest.net/](https://themeforest.net/) (Envato Market)

[https://startbootstrap.com/](https://startbootstrap.com/)

[https://themewagon.com/theme-category/admin-dashboard/?swoof=1\&pa\_price=free\&paged=1\&pa\_frameworks=bootstrap-5\&really\_curr\_tax=15-product\_cat](https://themewagon.com/theme-category/admin-dashboard/?swoof=1&pa_price=free&paged=1&pa_frameworks=bootstrap-5&really_curr_tax=15-product_cat) (Filter: free admin themes for bootstrap 5)

Examples

[https://prium.github.io/phoenix/v1.20.1/index.html](https://prium.github.io/phoenix/v1.20.1/index.html) from $39

[https://themesbrand.com/velzon/spring-boot.html](https://themesbrand.com/velzon/spring-boot.html) from $25

[https://www.creative-tim.com/product/material-dashboard](https://www.creative-tim.com/product/material-dashboard) free (pro from $79)

[https://adminlte.io/](https://adminlte.io/) free

[https://keenthemes.com/metronic/bootstrap](https://keenthemes.com/metronic/bootstrap) from $49

## Tutorial

### Text

    <p class="display-2"> But, wait... </p> 
    
    <p class="text-justify">How is it that you have no ears </p> <p class="font-weight-bold"> How sad, Mr Bunny </p>
    
    <p class="font-italic">See him hop, hop, hop about on legs so very strong.</p>
    
    <strong class="font-weight-normal"> But ears, he has none </strong>

### Quotes

```html
<figure>
  <blockquote class="blockquote">
    <p>A well-known quote, contained in a blockquote element.</p>
  </blockquote>
  <figcaption class="blockquote-footer">
    Someone famous in <cite title="Source Title">Source Title</cite>
  </figcaption>
</figure>
```

[https://getbootstrap.com/docs/5.0/content/typography/#blockquotes](https://getbootstrap.com/docs/5.0/content/typography/#blockquotes)

[https://mdbootstrap.com/docs/standard/extended/quotes/](https://mdbootstrap.com/docs/standard/extended/quotes/)

### Lists

    <ul class="list-unstyled">  
    	<li>Thank you</li>  
    	<li>Muchas Gracias</li> 
    	<li>Merci</li>
    </ul>

```html

<ul class="list-inline"> 
	<li class="list-inline-item">Thank you</li> 
	<li class="list-inline-item">Muchas Gracias</li>
	<li class="list-inline-item">Merci</li>
</ul>
```

### Colors

```html

<p class="text-secondary">Hello World</p>
<p class="text-success">Hello World</p>
<p class="text-danger">Hello World</p>
<p class="text-warning">Hello World</p>
<p class="text-info">Hello World</p>
<p class="text-light">Hello World</p>
<p class="text-dark">Hello World</p>
```

### Picture

```html

<img src="https://static.pexels.com/photos/45201/kitty-cat-kitten-pet-45201.jpeg" class="img-fluid"/>
<img src="..." alt="..." class="img-thumbnail">  
```

Picture with text https://getbootstrap.com/docs/4.0/content/figures/

```html

<figure class="figure">
  <img src="..." class="figure-img img-fluid rounded" alt="A generic square placeholder image with rounded corners in a figure.">
  <figcaption class="figure-caption text-right">A caption for the above image.</figcaption>
</figure>
```

https://bootsnipp.com/snippets/9jA https://bootsnipp.com/snippets/92e5X

```html

<img src="https://static.pexels.com/photos/45201/kitty-cat-kitten-pet-45201.jpeg"     class="img-fluid rounded"/>
```

```html
img {   border-radius: 50px } 


<img src="https://static.pexels.com/photos/45201/kitty-cat-kitten-pet-45201.jpeg"     class="img-fluid rounded-circle"/> 
<img src="https://static.pexels.com/photos/45201/kitty-cat-kitten-pet-45201.jpeg"       class="rounded-circle float-left"/>
```

Centered

```html

<div class="text-center">   <img src="https://static.pexels.com/photos/45201/kitty-cat-kitten-pet-45201.jpeg" class="rounded img-restricted"/>
</div>
```

### Video

```html

<div class="embed-responsive embed-responsive-16by9"> <iframe 
	class="embed-responsive-item" src="https://www.youtube.com/embed/zpOULjyy-n8?rel=0" 
	allowfullscreen></iframe> 
</div> 
```

### Layout

[https://getbootstrap.com/docs/5.0/layout/containers/](https://getbootstrap.com/docs/5.0/layout/containers/)

```html

<div class="w-25 p-3" style="background-color: #eee;">Width 25%</div> 
<div class="w-50 p-3" style="background-color: #eee;">Width 50%</div> 
<div class="w-75 p-3" style="background-color: #eee;">Width 75%</div> 
<div class="w-100 p-3" style="background-color: #eee;">Width 100%</div> 
```

### Cards

[https://getbootstrap.com/docs/5.0/components/card/](https://getbootstrap.com/docs/5.0/components/card/)

### Banner

    .page-header h1 {
      margin-top: 0px;
    }
    .page-header {
      height: 60px;
      margin-top: 0px;
      background-size: cover;
      background-image: url(some/parth/to/image);
    }

```
<div class="page-header">
  <h1 class="text-primary">My awesome page header</h1>
</div>
```

### Navigation

[https://www.geeksforgeeks.org/how-to-change-navigation-bar-color-in-bootstrap/](https://www.geeksforgeeks.org/how-to-change-navigation-bar-color-in-bootstrap/) Colors

### Code

[https://getbootstrap.com/docs/4.0/content/code/#inline-code](https://getbootstrap.com/docs/4.0/content/code/#inline-code)

[https://www.geeksforgeeks.org/how-to-display-code-with-bootstrap/](https://www.geeksforgeeks.org/how-to-display-code-with-bootstrap/)

## Additional libraries

Lightbox (ekko-lightbox) is a JavaScript library that displays images and videos by filling the screen, and dimming out the rest of the web page

Note: For bootstrap 5 use [https://trvswgnr.github.io/bs5-lightbox/](https://trvswgnr.github.io/bs5-lightbox/)

* [https://github.com/feimosi/baguetteBox.js](https://github.com/feimosi/baguetteBox.js) (галерея [https://tutorialzine.com/2018/03/3-amazing-bootstrap-4-gallery-templates](https://tutorialzine.com/2018/03/3-amazing-bootstrap-4-gallery-templates) )
* [https://veno.es/](https://veno.es/) VenoBox 2 Just another jQuery Vanilla JS \[Lightbox\](https://en.wikipedia.org/wiki/Lightbox\_(JavaScript%2529) plugin, suitable for Images, Videos, Inline contents, iFrames, Ajax requests.
* [https://jonmiles.github.io/bootstrap-treeview/](https://jonmiles.github.io/bootstrap-treeview/)
* [https://demos.devexpress.com/Bootstrap/](https://demos.devexpress.com/Bootstrap/)

## Using in Spring Boot projects

[https://www.youtube.com/watch?v=u0uO5Q0GcM4](https://www.youtube.com/watch?v=u0uO5Q0GcM4) 4 ways to use Bootstrap in Spring Boot

## References

Countries flag css [https://cdnjs.cloudflare.com/ajax/libs/flag-icon-css/3.1.0/css/flag-icon.min.css](https://cdnjs.cloudflare.com/ajax/libs/flag-icon-css/3.1.0/css/flag-icon.min.css) [https://cdnjs.cloudflare.com/ajax/libs/flag-icon-css/3.1.0/flags/4x3/fr.svg](https://cdnjs.cloudflare.com/ajax/libs/flag-icon-css/3.1.0/flags/4x3/fr.svg)

[https://www.quackit.com/bootstrap/bootstrap\_4/tutorial/](https://www.quackit.com/bootstrap/bootstrap_4/tutorial/) Bootstrap 4 Tutorial

[https://proglib.io/p/bootstrap-4-part-1/](https://proglib.io/p/bootstrap-4-part-1/) [https://proglib.io/p/bootstrap-4-grid/](https://proglib.io/p/bootstrap-4-grid/) Bootstrap 4 Tutorial

Migrating to v5 [https://getbootstrap.com/docs/5.0/migration/](https://getbootstrap.com/docs/5.0/migration/) [https://getbootstrap.com/docs/5.0/components/navbar/](https://getbootstrap.com/docs/5.0/components/navbar/)

Interesting themes:

* [https://colorlib.com/wp/template/sensive/](https://colorlib.com/wp/template/sensive/)
* [https://themeforest.net/item/volare-trekking-sailing-diving-template/8047905?s\_rank=9](https://themeforest.net/item/volare-trekking-sailing-diving-template/8047905?s_rank=9)
* [https://themeforest.net/item/dolomia-hiking-outdoor-mountain-guide-html-template/18968959?s\_rank=5](https://themeforest.net/item/dolomia-hiking-outdoor-mountain-guide-html-template/18968959?s_rank=5)

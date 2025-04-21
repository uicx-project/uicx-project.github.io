---
layout: home
description: The UICX project is about building a exchange format between a back-end and a front-end app which will be based on WebViews and HTML.
---

## What is the UICX Project ?

The UICX project is about building a exchange format between a back-end and a front-end app which will be based on WebViews and HTML.

It may seems simple at first but when you want to build robust application you need a robust data exchange between these two.

## What are the specifications ?

{% assign basics = site.posts | where:"permalink","/basic-concept" %}
{% for post in basics %}
 {{ post.content | remove: '<h2 id="the-basics">The basics</h2>' }}
{% endfor %}
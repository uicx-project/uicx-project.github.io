---
name: Getting started
layout: default
category: getting started
description: Learn about the UICX architecture between front-end and back-end.
---

# {{ page.name }}

{{ page.description }}

{% for category in site.categories | where: 0, page.category %}
{% for post in category[1] %}
- [{{ post.title }}]({{ post.url | relative_url }}){% if post.description %}: {{ post.description }}{% endif %}
{% endfor %}
{% endfor %}
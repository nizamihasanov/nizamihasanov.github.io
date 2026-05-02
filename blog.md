---
layout: default
title: Blog
permalink: /blog/
---

{% for post in site.posts %}
  {% if post.category == "blog" %}
## [{{ post.title }}]({{ post.url }})
  {% endif %}
{% endfor %}

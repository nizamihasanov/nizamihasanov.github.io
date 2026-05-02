---
layout: default
title: Writeups
permalink: /writeups/
---

{% for post in site.posts %}
  {% if post.category == "writeup" %}
## [{{ post.title }}]({{ post.url }})
  {% endif %}
{% endfor %}

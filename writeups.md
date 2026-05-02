---
layout: default
title: Writeups
---

{% raw %}
{% for post in site.posts %}
  {% if post.category == "writeup" %}
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
  {% endif %}
{% endfor %}
{% endraw %}

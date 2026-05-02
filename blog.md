---
layout: default
title: Blog
---

{% raw %}
{% for post in site.posts %}
  {% if post.category == "blog" %}
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
  {% endif %}
{% endfor %}
{% endraw %}

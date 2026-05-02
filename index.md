---
layout: default
---

## Featured Projects

{% for project in site.projects %}
- [{{ project.title }}]({{ project.url }})
{% endfor %}

## Latest Writeups

{% assign writeups = site.posts | where: "category", "writeup" %}
{% for post in writeups limit:5 %}
- [{{ post.title }}]({{ post.url }})
{% endfor %}

## Latest Blog Posts
{% assign blogposts = site.posts | where: "category", "blog" %}
{% for post in blogposts limit:10 %}
- [{{ post.title }}]({{ post.url }})
{% endfor %}
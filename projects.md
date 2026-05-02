---
layout: default
title: Projects
---

{% raw %}
{% for project in site.projects %}
    <h2><a href="{{ project.url  }}">{{ project.title }}</a></h2>
{% endfor %}
{% endraw %}

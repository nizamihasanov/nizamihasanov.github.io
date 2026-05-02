---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Nizami Hasanov

Cybersecurity Engineering Student focused on Security Operations.

## Projects

{% for project in site.projects %}
>> <a href="{{ project.url }}">{{ project.title }}</a>
{% endfor %}

## Latest Writeups

{% assign writeups = site.posts | where: "category", "writeup" %}
{% for post in writeups limit:5 %}
>> <a href="{{ post.url }}">{{ post.title }}</a>
{% endfor %}

## Latest Blog Posts
{% for post in site.blog limit:10 %}
- [{{ post.title }}]({{ post.url }})
{% endfor %}

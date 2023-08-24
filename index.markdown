---
layout: default
title: Home
---

# Welcome to My Jekyll Site!

Hello, and welcome to my Jekyll-powered website. I'm excited to share my thoughts, ideas, and projects with you. Whether you're a fellow developer, a curious learner, or just someone passing by, I hope you'll find something interesting here.

## Recent Posts

{% for post in site.posts %}
### [{{ post.title }}]({{ post.url }})
{{ post.excerpt | markdownify }}
{% endfor %}

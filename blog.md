---
layout: page
status: publish
published: true
title: Recent Posts
author: Alex Chubaty
---

{% for post in site.posts %}
{{ post.date | date_to_string }} &raquo; <a href="{{ post.url }}">{{ post.title }}</a>
{% endfor %}


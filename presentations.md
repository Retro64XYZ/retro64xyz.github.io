---
layout: page
title: Presentations
permalink: /presentations/
---

These are my presentations.

<ul>
  {% for post in site.categories.presentations %}
    {% if post.url %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% elsif post.url == 0 %}
      <p>There are no presentations yet!</p>
    {% endif %}
  {% endfor %}
</ul>

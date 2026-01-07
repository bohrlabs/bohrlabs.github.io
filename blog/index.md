---
layout: default
title: Blog
permalink: /blog/
---

<h1>Blog</h1>

<p>
  General engineering notes and experiences – written in an abstract way, without company
  or product details. Focus: internal tools, simulation, visualization and incremental migration.
</p>

## Posts

<ul>
{% for post in site.posts %}
  <li>
    {{ post.date | date: "%Y-%m-%d" }} —
    <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>

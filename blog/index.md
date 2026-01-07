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
{% assign blog_pages = site.pages
  | where_exp: "p", "p.path contains 'blog/'"
  | where_exp: "p", "p.path != 'blog/index.md'"
  | sort: "path"
  | reverse %}

{% for p in blog_pages %}
  {% assign date_str = p.path | split: "/" | last | slice: 0, 10 %}
  <li>
    {{ date_str }} —
    <a href="{{ p.url }}">{{ p.title | default: p.name }}</a>
  </li>
{% endfor %}
</ul>

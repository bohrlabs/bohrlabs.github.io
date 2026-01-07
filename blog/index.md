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
  | where_exp: "p", "p.dir == '/blog/'"
  | sort: "name"
  | reverse %}

{% for p in blog_pages %}
  {% if p.name != "index.md" %}
    {% assign date_str = p.name | slice: 0, 10 %}
    <li>
      {{ date_str }} —
      <a href="{{ p.url }}">{{ p.title }}</a>
    </li>
  {% endif %}
{% endfor %}
</ul>

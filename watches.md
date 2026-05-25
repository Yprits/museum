---
layout: pgs
title: "Часовая экспозиция"
permalink: /watches/
---
## Котельная

Здесь представлены часы, таймеры, будильники, секундомеры, песочные часы, гномоны и еще много чего.

{% assign clocks = site.exhibits | where_exp: "item", "item.path contains 'watches/'" %}

<ul>
  {% for item in clocks %}
    <li><a href="{{ item.url | relative_url }}">{{ item.title }}</a> — [{{ item.condition }}]</li>
  {% endfor %}
</ul>

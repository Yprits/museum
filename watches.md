---
layout: page
title: "Часовая экспозиция"
permalink: /watches/
---
## Котельная

{% assign clocks = site.exhibits | where_exp: "item", "item.path contains 'watches/'" %}

<ul>
  {% for item in clocks %}
    <li><a href="{{ item.url | relative_url }}">{{ item.title }}</a> — [{{ item.condition }}]</li>
  {% endfor %}
</ul>

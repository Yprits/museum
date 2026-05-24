---
layout: page
title: "Кунсткамера"
permalink: /kunstkamera/
---
## Кабинет инженерных курьезов и парадоксов

Что-то просто должно остаться в истории - желательно в формалине и под слоем бетона.

<ul>
  {% for item in site.kunstkamera %}
    <li><a href="{{ item.url | relative_url }}">{{ item.title }}</a></li>
  {% endfor %}
</ul>

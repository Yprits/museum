---
layout: pgs
title: "Все экспонаты коллекции"
---

На этой странице - список всех экземпляров коллекции (без разбивки по моделям)

Чтобы посмотреть информацию про любой экземпляр, просто кликните на его номер в коллекции!

Хотите искать по моделям? Вам  <a href="https://yprits.github.io/museum">сюда</a>.

{% for exhibit in site.exhibits %}
<a href="{{ model.url | relative_url }}">
    {{ exhibit.innernumber }}
  </a>
  ({{ exhibit.model}})
{% endfor %}


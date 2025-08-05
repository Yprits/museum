---
layout: pgs
title: "Все экспонаты коллекции"
---

# На этой странице можно посмотреть все экспонаты в коллекции

Хотите узнать про какую-либо модель? Просто кликните на ее название!
Хотите искать по моделям? Вам  <a href="https://yprits.github.io/museum">сюда</a>

{% for exhibit in site.exhibits %}
<a href="{{ model.url | relative_url }}">
    {{ exhibit.innernumber }} ({{ exhibit.model}})
  </a>
{% endfor %}

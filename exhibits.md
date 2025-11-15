---
layout: pgs
title: "Все экспонаты коллекции"
---

На этой странице - список всех экземпляров коллекции (без разбивки по моделям).

<!-- На данный момент описано и опубликовано экспонатов: **{{ site.exhibits.size }}** -->

Чтобы посмотреть информацию про любой экземпляр, просто кликните на его номер в коллекции!

Хотите искать по моделям? Вам  <a href="https://yprits.github.io/museum/models">сюда</a>.


<table>
  {% for exhibit in site.exhibits %}
    {% if exhibit.innernumber %}
      <tr>
        <td> <a href= {{ exhibit.photo0 }} > <img src= {{ exhibit.prev0 }} alt= "Изображения пока нет"> </a> </td>
        <td> <a href="{{ exhibit.url | relative_url }}"> {{ exhibit.innernumber }} </a> - {{ exhibit.model}} ({{ exhibit.prodyear }}) </td>
      </tr>
  {% endif %}
  {% endfor %}  
</table>


{% for exhibit in site.exhibits %}
{% if exhibit.innernumber %}
<a href="{{ exhibit.url | relative_url }}"> {{ exhibit.innernumber }} </a> - {{ exhibit.model}} ({{ exhibit.prodyear }})
{% endif %}
{% endfor %}

<!-- Ну и что вы здесь ожидали увидеть? -->

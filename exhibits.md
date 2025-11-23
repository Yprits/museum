---
layout: pgs
title: "Все экспонаты коллекции"
---

На этой странице - список всех экземпляров коллекции (без разбивки по моделям).

<!-- На данный момент описано и опубликовано экспонатов: **{{ site.exhibits.size }}** -->

Чтобы посмотреть информацию про любой экземпляр, просто кликните на его номер в коллекции!

Хотите искать по моделям? Вам  <a href="https://yprits.github.io/museum/models">сюда</a>.

У экспонатов есть категории по странам:
 - [Советские](./exhibits/ussr) - все, связанные с СССР;
 - [Белорусские](./exhibits/belarus);
 - [Российские](./exhibits/russia);
 - [Китайские](./exhibits/china);
 - [Американские](./exhibits/usa);
 - [Японские](./exhibits/japan);
 - [Прочие](./exhibits/others) - в разработке.


<!--
 <div class="spisok">
   
<table>
  {% for exhibit in site.exhibits %}
    {% if exhibit.innernumber %}
      <tr>
        <td>
          {% if exhibit.photo0 and exhibit.prev0 %}
            <a href="{{ exhibit.photo0 }}"><img src="{{ exhibit.prev0 }}" alt="Изображения пока нет"></a>
          {% else %}
            <img src="https://placehold.co/128/png/?text=%D0%A4%D0%BE%D1%82%D0%BE\n%D0%BF%D0%BE%D0%BA%D0%B0\n%D0%BD%D0%B5%D1%82" alt="Фото нет">
          {% endif %}
        </td>
        <td><a href="{{ exhibit.url | relative_url }}">{{ exhibit.innernumber }}</a> <br> {{ exhibit.model}} <br> {{ exhibit.prodyear }} </td>
      </tr>
    {% endif %}
  {% endfor %}  
</table>


 </div>
-->

<div class="spisok">
<table>
  {% for exhibit in site.exhibits %}
    {% if exhibit.innernumber %}
      {% assign mod = forloop.index0 | modulo: 2 %}
      {% if mod == 0 %}<tr>{% endif %}
        <td>
          {% if exhibit.photo0 and exhibit.prev0 %}
            <a href="{{ exhibit.photo0 }}"><img src="{{ exhibit.prev0 }}" alt="Изображения пока нет"></a>
          {% else %}
            <img src="https://placehold.co/128/png/?text=%D0%A4%D0%BE%D1%82%D0%BE\n%D0%BF%D0%BE%D0%BA%D0%B0\n%D0%BD%D0%B5%D1%82" alt="Фото нет">
          {% endif %}
        </td>
        <td><a href="{{ exhibit.url | relative_url }}">{{ exhibit.innernumber }}</a> <br> {{ exhibit.model}} <br> {{ exhibit.prodyear | append: ""}} </td>
      {% if mod == 1 or forloop.last %}</tr>{% endif %}
    {% endif %}
  {% endfor %}  
</table>
</div>

<!-- Ну и что вы здесь ожидали увидеть? -->

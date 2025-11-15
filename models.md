---
layout: pgs
title: "Модели вычислительной техники"
---

Здесь Вы можете ознакомиться с различными моделями вычислителной техники.

Чтобы посмотреть информацию про любую модель, просто кликните на ее название!

Хотите искать по внутренним номерам? Вам  <a href="https://yprits.github.io/museum/exhibits">сюда</a>.

Вы знаете какую-то интересную модель, но в списке ее нет? Свяжитесь со мной!

На данный момент описано моделей: {{ site.models.size }}.

Модели расположены в алфавитном порядке.

{% for modell in site.models %}
<a href="{{ modell.url | relative_url }}"> {{ modell.title }} </a> - {{ modell.short }} ({{ modell.country}})
{% endfor %}

 <div class="spisok">
   
<table>
  {% for modell in site.models %}
    {% if modell.title %}
      <tr>
        <td>
          {% if modell.photo0 and modell.prev0 %}
            <a href="{{ modell.photo0 }}"><img src="{{ modell.prev0 }}" alt="Изображения пока нет"></a>
          {% else %}
            <img src="https://placehold.co/128/png/?text=%D0%A4%D0%BE%D1%82%D0%BE\n%D0%BF%D0%BE%D0%BA%D0%B0\n%D0%BD%D0%B5%D1%82" alt="Фото нет">
          {% endif %}
        </td>
        <td><a <a href="{{ modell.url | relative_url }}"> {{ modell.title }} </a> - {{ modell.short }} ({{ modell.country}})
      </tr>
    {% endif %}
  {% endfor %}  
</table>

 </div>

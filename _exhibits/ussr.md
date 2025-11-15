---
layout: taglist
title: Советская техника
tagz: ussr
---

# Модели с тегом "советская техника"

О советской технике ходило немало шуток. А здесь мы показываем ее такой, какая она была.


<table>
  {% for exhibit in site.exhibits %}
    {% if exhibit.tags contains page.tagz %}
      <tr>
        <td>
          {% if exhibit.photo0 and exhibit.prev0 %}
            <a href="{{ exhibit.photo0 }}"><img src="{{ exhibit.prev0 }}" alt="Изображения пока нет"></a>
          {% else %}
            <span>Нет изображения</span>
          {% endif %}
        </td>
        <td><a href="{{ exhibit.url | relative_url }}">{{ exhibit.innernumber }}</a> - {{ exhibit.model}} ({{ exhibit.prodyear }})</td>
      </tr>
    {% endif %}
  {% endfor %}  
</table>

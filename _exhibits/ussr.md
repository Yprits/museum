---
layout: pgs
title: Советская техника
tag: ussr
---

# Модели с тегом "советская техника"

О советской технике ходило немало шуток. А здесь мы показываем ее такой, какая она была.


{% for exhibit in site.exhibits %}
  {% if exhibit.tags contains page.tag %}
    <div class="exhibit-item">
      <a href="{{ exhibit.url }}">{{ exhibit.innernumber }}</a> - {{ exhibit.model }} ({{ exhibit.prodyear }})
    </div>
  {% endif %}
{% endfor %}

---
layout: pgs
title: Советская техника
tag: ussr
---

# Модели с тегом "советская техника"

О советской технике ходило немало шуток. А здесь мы показываем ее такой, какая она была.


<div class="exhibits-list">
{% for exhibit in site.exhibits %}
  {% if exhibit.tags contains page.tag %}
    <a href="{{ exhibit.url | relative_url }}"> {{ exhibit.innernumber }} </a> - {{ exhibit.model}} ({{ exhibit.prodyear }})<br>
  {% endif %}
{% endfor %}
</div>

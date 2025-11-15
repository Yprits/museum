---
layout: pages
title: "Советская техника"
tag: ussr
---

<h1>Модели с тегом "советская техника"</h1>

{% for exhibit in site.exhibits %}
  {% if exhibit.tags contains page.tag %}
    <div class="exhibit-item">
      <a href="{{ exhibit.url }}">{{ exhibit.innernumber }}</a> - {{ exhibit.model }} ({{ exhibit.prodyear }})
    </div>
  {% endif %}
{% endfor %}

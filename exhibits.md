---
layout: pages
title: "Все экспонаты коллекции"
---

{% raw %}{% assign exhibits = site.exhibits | sort: "prodyear" %}

<div class="exhibits-grid">
  {% for exhibit in exhibits %}
    <div class="exhibit-card">
      <a href="{{ exhibit.url }}">
        <h3>{{ exhibit.title }}</h3>
        <p>{{ exhibit.prodyear }} | {{ exhibit.manufacturer }}</p>
      </a>
    </div>
  {% endfor %}
</div>{% endraw %}

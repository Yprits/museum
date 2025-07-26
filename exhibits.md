---
layout: default
title: "Все экспонаты коллекции"
---

{% raw %}{% assign sorted_exhibits = site.exhibits | sort: "production_year" %}

<div class="exhibits-grid">
  {% for exhibit in sorted_exhibits %}
    <div class="exhibit-card">
      <a href="{{ exhibit.url }}">
        {% if exhibit.main_photo %}
          <img src="{{ exhibit.main_photo }}" alt="{{ exhibit.title }}" loading="lazy">
        {% endif %}
        <h3>{{ exhibit.title }}</h3>
      </a>
      <p class="meta">
        <span>{{ exhibit.production_year }}</span> | 
        <span>{{ exhibit.manufacturer }}</span>
      </p>
      <div class="tags">
        {% for tag in exhibit.exhibit_tags %}
          <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>
    </div>
  {% endfor %}
</div>{% endraw %}

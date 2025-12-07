---
layout: pgs
title: "Все экспонаты коллекции"
---

На этой странице - список всех экземпляров коллекции (без разбивки по моделям). 

Чтобы посмотреть информацию про любой экземпляр, просто кликните на его номер в коллекции!

Хотите искать по моделям? Вам <a href="https://yprits.github.io/museum/models">сюда</a>.

<div class="exhibits-grid items-grid">
  {% for exhibit in site.exhibits %}
    {% if exhibit.innernumber %}
      <div class="exhibit-card item-card">
        <div class="item-image">
          {% if exhibit.photo0 and exhibit.prev0 %}
            <a href="{{ exhibit.photo0 }}">
              <img src="{{ exhibit.prev0 }}" alt="{{ exhibit.model }}" loading="lazy">
            </a>
          {% else %}
            <img src="https://placehold.co/150x100/png?text=Фото+пока+нет&font=verdana" 
                 alt="Фото пока нет" loading="lazy">
          {% endif %}
        </div>
        <div class="item-info">
          <a href="{{ exhibit.url | relative_url }}" class="item-title">{{ exhibit.innernumber }}</a>
          <div class="item-description">{{ exhibit.model }}</div>
          <div class="item-meta">{{ exhibit.prodyear | replace: ".", "." }}</div>
        </div>
      </div>
    {% endif %}
  {% endfor %}
</div>

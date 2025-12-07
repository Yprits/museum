---
layout: pgs
title: "Модели вычислительной техники"
---

Здесь Вы можете ознакомиться с различными моделями вычислительной техники.

Чтобы посмотреть информацию про любую модель, просто кликните на ее название!

Хотите искать по внутренним номерам? Вам <a href="https://yprits.github.io/museum/exhibits">сюда</a>.

Вы знаете какую-то интересную модель, но в списке ее нет? Свяжитесь со мной!

На данный момент описано моделей: {{ site.models.size }}.

Модели расположены в алфавитном порядке.

<div class="models-grid items-grid">
  {% for modell in site.models %}
    {% if modell.title %}
      <div class="model-card item-card">
        <div class="item-image">
          {% if modell.photo0 and modell.prev0 %}
            <a href="{{ modell.photo0 }}">
              <img src="{{ modell.prev0 }}" alt="{{ modell.title }}" loading="lazy">
            </a>
          {% else %}
            <img src="https://placehold.co/150x100/png?text=Фото+пока+нет&font=verdana" 
                 alt="Фото пока нет" loading="lazy">
          {% endif %}
        </div>
        <div class="item-info">
          <a href="{{ modell.url | relative_url }}" class="item-title">{{ modell.title }}</a>
          <div class="item-description">{{ modell.short }}</div>
          <div class="item-meta">{{ modell.country }}</div>
        </div>
      </div>
    {% endif %}
  {% endfor %}
</div>

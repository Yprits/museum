---
layout: pgs
title: "Эфемеры"
---

Здесь представлены рекламные материалы, марки, визитки, календари и другая бумажная продукция, изначально не предназначенная к долговременному хранению.

{% if site.ephemera.size > 0 %}
<div class="ephemera-list-grid">
  {% for item in site.ephemera %}
    {% if item.title %}
    <div class="ephemera-list-card">
      <!-- Изображение -->
      <div class="ephemera-list-image">
        {% if item.photo0 and item.prev0 %}
          <a href="{{ item.url | relative_url }}">
            <img src="{{ item.prev0 }}" alt="{{ item.title }}" loading="lazy">
          </a>
        {% else %}
          <img src="https://placehold.co/250x180/png?text=Документ&font=verdana" 
               alt="Изображение отсутствует" loading="lazy">
        {% endif %}
      </div>
      
      <!-- Информация -->
      <div class="ephemera-list-info">
        <!-- Заголовок -->
        <a href="{{ item.url | relative_url }}" class="ephemera-list-title">{{ item.title }}</a>
        
        <!-- Описание -->
        <div class="ephemera-list-description">
          {{ item.description | default: "Без описания" | truncate: 120 }}
        </div>
        
        <!-- Основная мета-информация -->
        <div class="ephemera-list-meta">
          {% if item.type %}
          <div class="ephemera-list-meta-item">
            <strong>Тип:</strong> {{ item.type }}
          </div>
          {% endif %}
          
          {% if item.year %}
          <div class="ephemera-list-meta-item">
            <strong>Год:</strong> {{ item.year }}
          </div>
          {% endif %}
          
          {% if item.language %}
          <div class="ephemera-list-meta-item">
            <strong>Язык:</strong> {{ item.language }}
          </div>
          {% endif %}
          
          {% if item.pages %}
          <div class="ephemera-list-meta-item">
            <strong>Страниц:</strong> {{ item.pages }}
          </div>
          {% endif %}
        </div>
        
        <!-- Связанные модели (новое поле!) -->
        {% if item.models %}
        <div class="ephemera-list-models">
          <div class="ephemera-list-models-title">📱 Изображенные модели:</div>
          <div class="ephemera-list-models-list">
            {% assign model_refs = item.models | split: "," %}
            {% for model_ref in model_refs %}
              {% assign model_name = model_ref | strip %}
              {% if model_name != "" %}
                <!-- Ищем модель в коллекции -->
                {% assign found_model = site.models | where: "title", model_name | first %}
                {% if found_model %}
                  <a href="{{ found_model.url | relative_url }}">{{ model_name }}</a>{% unless forloop.last %}, {% endunless %}
                {% else %}
                  {{ model_name }}{% unless forloop.last %}, {% endunless %}
                {% endif %}
              {% endif %}
            {% endfor %}
          </div>
        </div>
        {% endif %}
        
        <!-- Бейджи -->
        <div class="ephemera-list-badges">
          {% if item.type %}
          <span class="ephemera-list-badge type" title="Тип документа">{{ item.type | truncate: 15 }}</span>
          {% endif %}
          
          {% if item.year %}
          <span class="ephemera-list-badge year" title="Год выпуска">{{ item.year }}</span>
          {% endif %}
          
          {% if item.rare %}
          <span class="ephemera-list-badge rare" title="Редкий документ">★ Редкий</span>
          {% endif %}
        </div>
      </div>
    </div>
    {% endif %}
  {% endfor %}
</div>

<p style="margin-top: 20px; color: #666; font-size: 0.9em;">
  Всего документов в коллекции: {{ site.ephemera.size }}
</p>

{% else %}
<div style="text-align: center; padding: 40px; background: #f8f9fa; border-radius: 8px; margin: 20px 0;">
  <p style="font-size: 1.2em; color: #666;">Коллекция эфемеров пока пуста</p>
  <p>Добавьте первый документ в папку <code>_ephemera</code></p>
</div>
{% endif %}

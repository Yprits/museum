---
layout: pgs
title: "Эфемеры"
---

Здесь представлены рекламные материалы, марки, визитки, календари и другая бумажная продукция, изначально не предназначенная к долговременному хранению. Сюда же идут карикатуры, интересные обложки, пропагандистские и информационные плакаты и прочее.

{% if site.ephemera.size > 0 %}
<div class="ephemera-list-grid">
  {% for item in site.ephemera %}
    {% if item.title %}
    <div class="ephemera-list-card">
      
      <!-- 1. Изображение -->
      <div class="ephemera-list-image">
        {% if item.photo0 and item.prev0 %}
          <a href="{{ item.url | relative_url }}">
            <img src="{{ item.prev0 }}" alt="{{ item.title }}" loading="lazy">
          </a>
        {% else %}
          <img src="https://placehold.co" 
               alt="Изображение отсутствует" loading="lazy">
        {% endif %}
      </div>
      
      <!-- 2. Блок информации -->
      <div class="ephemera-list-info">
        
        <!-- Заголовок -->
        <a href="{{ item.url | relative_url }}" class="ephemera-list-title">{{ item.title }}</a>
        
        <!-- Описание (очищаем от возможных случайных тегов ради безопасности) -->
        <div class="ephemera-list-description">
          {{ item.description | strip_html | default: "Без описания" }}
        </div>
        
        <!-- Техническая мета-информация (только то, чего нет в бейджах) -->
        {% if item.pages %}
        <div class="ephemera-list-meta">
          <div class="ephemera-list-meta-item">
            <strong>Страниц:</strong> {{ item.pages }}
          </div>
        </div>
        {% endif %}
        
        <!-- Связанные модели -->
        {% if item.models %}
        <div class="ephemera-list-models">
          <div class="ephemera-list-models-title">📱 Изображенные модели:</div>
          <div class="ephemera-list-models-items">
            {% assign model_refs = item.models | split: "," %}
            {% for model_ref in model_refs %}
              {% assign model_name = model_ref | strip %}
              {% if model_name != "" %}
                {% assign found_model = site.models | where_exp: "m", "m.title == model_name" | first %}
                {% if found_model %}
                  <a href="{{ found_model.url | relative_url }}" class="ephemera-list-model-item">{{ model_name }}</a>
                {% else %}
                  <span class="ephemera-list-model-item" style="background: #f0f0f0; color: #666; border-color: #ddd;">{{ model_name }}</span>
                {% endif %}
              {% endif %}
            {% endfor %}
          </div>
        </div>
        {% endif %}
        
        <!-- Визуальные Бейджи (выводятся строго один раз внизу) -->
        <div class="ephemera-list-badges">
          {% if item.type %}
          <span class="ephemera-list-badge type" title="Тип документа">{{ item.type }}</span>
          {% endif %}
          
          {% if item.year %}
          <span class="ephemera-list-badge year" title="Год выпуска">{{ item.year }}</span>
          {% endif %}
          
          {% if item.rare %}
          <span class="ephemera-list-badge rare" title="Редкий документ">★ Редкий</span>
          {% endif %}
          
          {% if item.language %}
          <span class="ephemera-list-badge language" title="Язык">{{ item.language }}</span>
          {% endif %}
        </div>

      </div> <!-- /ephemera-list-info -->
    </div> <!-- /ephemera-list-card -->
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

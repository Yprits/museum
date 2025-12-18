---
layout: pgs
title: "Все теги коллекции"
permalink: /exhibits/tags/
---

<h1>Все теги коллекции</h1>
<p>Список всех тегов, которые использовались для классификации экспонатов. Нажмите на тег, чтобы увидеть все экспонаты с этим тегом.</p>

{% comment %}
  Собираем все уникальные теги из всех экспонатов
{% endcomment %}

{% assign all_tags = "" | split: "" %}
{% for exhibit in site.exhibits %}
  {% if exhibit.tags and exhibit.tags.size > 0 %}
    {% for tag in exhibit.tags %}
      {% unless all_tags contains tag %}
        {% assign all_tags = all_tags | push: tag %}
      {% endunless %}
    {% endfor %}
  {% endif %}
{% endfor %}

{% if all_tags.size > 0 %}
  {% assign sorted_tags = all_tags | sort %}
  
  <div class="tags-container">
    {% for tag in sorted_tags %}
      {% assign exhibits_count = site.exhibits | where_exp: "item", "item.tags contains tag" | size %}
      
      <div class="tag-item">
        <a href="/exhibits/tag/{{ tag | slugify }}/" class="tag-link">
          <span class="tag-name">{{ tag }}</span>
          <span class="tag-count">{{ exhibits_count }}</span>
        </a>
      </div>
    {% endfor %}
  </div>
  
  <p class="tags-summary">Всего тегов: {{ all_tags.size }}. Экспонатов: {{ site.exhibits.size }}.</p>
{% else %}
  <p>Пока не добавлено ни одного тега.</p>
{% endif %}

<style>
.tags-container {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  margin: 30px 0;
}

.tag-item {
  display: inline-block;
}

.tag-link {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 10px 18px;
  background-color: #f5f5f5;
  border-radius: 24px;
  text-decoration: none;
  color: #333;
  border: 1px solid #ddd;
  transition: all 0.2s ease;
}

.tag-link:hover {
  background-color: #e8e8e8;
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}

.tag-name {
  font-weight: 600;
  font-size: 16px;
}

.tag-count {
  background-color: #4a90e2;
  color: white;
  font-size: 14px;
  font-weight: 500;
  padding: 2px 10px;
  border-radius: 12px;
  min-width: 24px;
  text-align: center;
}

.tags-summary {
  margin-top: 30px;
  padding: 15px;
  background-color: #f9f9f9;
  border-left: 4px solid #4a90e2;
  font-size: 16px;
  color: #555;
}

/* Адаптивность */
@media (max-width: 768px) {
  .tags-container {
    gap: 8px;
  }
  
  .tag-link {
    padding: 8px 14px;
  }
  
  .tag-name {
    font-size: 14px;
  }
  
  .tag-count {
    font-size: 12px;
    padding: 1px 8px;
  }
}
</style>

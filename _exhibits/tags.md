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
  
  <p>Всего уникальных тегов: {{ all_tags.size }}. Всего экспонатов в коллекции: {{ site.exhibits.size }}.</p>
  
  <div class="tags-column">
    {% for tag in sorted_tags %}
      {% assign exhibits_with_tag = site.exhibits | where_exp: "item", "item.tags contains tag" | sort: "basename" %}
      {% assign exhibits_count = exhibits_with_tag | size %}
   
      <div class="tag-section">
        <h3 class="tag-header">
          <a href="/exhibits/{{ tag | slugify }}/" class="tag-link">
            {{ tag }}
            <span class="tag-count">({{ exhibits_count }})</span>
          </a>
        </h3>
        
        <div class="exhibits-list">
          <ul>
            {% for exhibit in exhibits_with_tag %}
              <li>
                <a href="{{ exhibit.url | relative_url }}">
                  <strong>{{ exhibit.innernumber }}</strong> 
                  — {{ exhibit.model }}
                  {% if exhibit.category %}({{ exhibit.category }}){% endif %}
                  {% if exhibit.country %}[{{ exhibit.country }}]{% endif %}
                </a>
              </li>
            {% endfor %}
          </ul>
        </div>
      </div>
    {% endfor %}
  </div>
{% else %}
  <p>Пока не добавлено ни одного тега.</p>
{% endif %}

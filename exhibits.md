---
layout: pages
title: "Все экспонаты коллекции"
---

<h1>{{ page.title }}</h1>

<div class="models-grid">
  {% assign sorted_models = site.computers | sort: "year" %}
  {% for model in sorted_models %}
    <div class="model-card">
      <a href="{{ model.url }}">
        <h2>{{ model.title }}</h2>
        {% if model.image %}
          <img src="{{ model.image }}" alt="{{ model.title }}">
        {% endif %}
      </a>
      <p><strong>Год:</strong> {{ model.year }}</p>
      <p><strong>Производитель:</strong> {{ model.manufacturer }}</p>
    </div>
  {% endfor %}
</div>

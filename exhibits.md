---
layout: pages
title: "Все экспонаты коллекции"
---

TEST!!!

<h1>{{ page.title }}</h1>

<div class="models-grid">
  {% assign sorted_models = site.models %}
  {% for model in sorted_models %}
    <div class="model-card">
      <a href="{{ model.url }}">
        <h2>{{ model.title }}</h2>
        
      </a>
      
      <p><strong>Производитель:</strong> {{ model.manufacturer }}</p>
    </div>
  {% endfor %}
</div>

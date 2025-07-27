---
layout: pages
title: "Все экспонаты коллекции"
---

{% for model in site.models %}
  <h2>{{ model.title }} </h2>
  <p>{{ model.permalink }}</p>
{% endfor %}

TEST!!!



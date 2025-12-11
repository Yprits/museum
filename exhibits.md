---
layout: pgs
title: "Все экспонаты коллекции"
---

На этой странице - список всех экземпляров коллекции (без разбивки по моделям).

Чтобы посмотреть информацию про любой экземпляр, просто кликните на его номер в коллекции!

Хотите искать по моделям? Вам <a href="https://yprits.github.io/museum/models">сюда</a>.

<div class="filter-section">
  <details>
    <summary>Искать по типу</summary>
    <div class="filter-content">
      <ul>
        <li><a href="./exhibits/programmable">Программируемые калькуляторы и компьютеры</a></li>
        <li><a href="./exhibits/engineer">Инженерные калькуляторы</a></li>
        <li><a href="./exhibits/arithmetical">Арифметические калькуляторы</a></li>
        <li><a href="./exhibits/rules">Линейки логарифмические и не только</a></li>
        <li><a href="./exhibits/mech">Механические счетные устройства</a></li>
        <li><a href="./exhibits/premech">Домеханические цифровые счетные устройства (счеты, палочки и другое)</a></li>
        <li><a href="./exhibits/notebook">Электронные записные книжки</a></li>
        <li><a href="./exhibits/othercategory">Прочие</a> - в разработке.</li>
      </ul>
    </div>
  </details>

  <details>
    <summary>Искать по странам</summary>
    <div class="filter-content">
      <ul>
        <li><a href="./exhibits/ussr">Советские</a> - все, связанные с СССР</li>
        <li><a href="./exhibits/belarus">Белорусские</a></li>
        <li><a href="./exhibits/russia">Российские</a></li>
        <li><a href="./exhibits/china">Китайские</a></li>
        <li><a href="./exhibits/usa">Американские</a></li>
        <li><a href="./exhibits/germany">Немецкие</a></li>
        <li><a href="./exhibits/japan">Японские</a></li>
        <li><a href="./exhibits/othercountry">Прочие</a> - в разработке.</li>
      </ul>
    </div>
  </details>
</div>

<!-- Сортируем экспонаты по числовому номеру -->
{% assign sorted_exhibits = site.exhibits | sort: "basename" %}
<div class="exhibits-grid items-grid">
  {% for exhibit in sorted_exhibits %}
    {% if exhibit.innernumber %}
      <div class="exhibit-card item-card">
       <div class="item-image">
  {% if exhibit.photo0 %}
    {% capture generated_prev0 %}
      {% include get_imgbox_thumb.liquid url=exhibit.photo0 %}
    {% endcapture %}
    {% assign thumb_url = generated_prev0 | strip %}
    {% if thumb_url != "" %}
      <a href="{{ exhibit.photo0 }}" target="_blank" rel="noopener noreferrer">
        <img src="{{ thumb_url }}" alt="{{ exhibit.model }}" loading="lazy">
      </a>
    {% else %}
      <img src="https://placehold.co/150x100/png?text=Ошибка+ссылки&font=verdana" 
           alt="Ошибка в ссылке на фото" loading="lazy">
    {% endif %}
  {% else %}
    <img src="https://placehold.co/150x100/png?text=Фото+пока+нет&font=verdana" 
         alt="Фото пока нет" loading="lazy">
  {% endif %}
</div>
        <div class="item-info">
          <a href="{{ exhibit.url | relative_url }}" class="item-title">{{ exhibit.innernumber }}</a>
          <div class="item-description">{{ exhibit.model }}</div>
          <div class="item-meta">
            {% if exhibit.category %}({{ exhibit.category }}){% endif %}
            {% if exhibit.manufacturer %}<br>🏭 {{ exhibit.manufacturer }}{% endif %}
            {% if exhibit.prodyear %}<br>📅 {{ exhibit.prodyear }}{% endif %}
            {% if exhibit.country %}<br>🌍 {{ exhibit.country }}{% endif %}
            {% if exhibit.collectionstatus %}
              <br>
              {% assign status = exhibit.collectionstatus | default: "" | upcase %}
              {% if status == "ПОИСК" or status contains "ИЩУ" %}
                <span class="status-seek">{{ exhibit.collectionstatus }}</span>
              {% else %}
                {{ exhibit.collectionstatus }}
              {% endif %}
            {% endif %}
          </div>
        </div>
      </div>
    {% endif %}
  {% endfor %}
</div>

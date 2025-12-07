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
      <a href="./exhibits/programmable">Программируемые калькуляторы и компьютеры</a>
      <a href="./exhibits/engineer">Инженерные калькуляторы</a>
      <a href="./exhibits/arithmetical">Арифметические калькуляторы</a>
      <a href="./exhibits/rules">Линейки логарифмические и не только</a>
      <a href="./exhibits/mech">Механические счетные устройства</a>
      <a href="./exhibits/premech">Домеханические цифровые счетные устройства</a>
      <a href="./exhibits/notebook">Электронные записные книжки</a>
      <a href="./exhibits/othercategory">Прочие (в разработке)</a>
    </div>
  </details>

  <details>
    <summary>Искать по странам</summary>
    <div class="filter-content">
      <a href="./exhibits/ussr">Советские</a>
      <a href="./exhibits/belarus">Белорусские</a>
      <a href="./exhibits/russia">Российские</a>
      <a href="./exhibits/china">Китайские</a>
      <a href="./exhibits/usa">Американские</a>
      <a href="./exhibits/germany">Немецкие</a>
      <a href="./exhibits/japan">Японские</a>
      <a href="./exhibits/othercountry">Прочие (в разработке)</a>
    </div>
  </details>
</div>

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
          <div class="item-meta">
            ({{ exhibit.category }}) <br>
            🏭 {{ exhibit.manufacturer }} <br>
            📅 {{ exhibit.prodyear | replace: ".", "." }} <br>
            🌍 {{ exhibit.country }}
          </div>
        </div>
      </div>
    {% endif %}
  {% endfor %}
</div>

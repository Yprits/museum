---
layout: pgs
title: "Все экспонаты коллекции"
---

На этой странице - список всех экземпляров коллекции (без разбивки по моделям).

Чтобы посмотреть информацию про любой экземпляр, просто кликните на его номер в коллекции!

Хотите искать по моделям? Вам <a href="https://github.io">сюда</a>.

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
    <summary>Искать по странах</summary>
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

{% include exhibits_list.html sort_by="basename" %}

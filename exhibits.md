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
      {% capture details_content %}
      - [Программируемые](./exhibits/programmable) калькуляторы и компьютеры;
      - [Инженерные](./exhibits/engineer) калькуляторы;
      - [Арифметические](./exhibits/arithmetical) калькуляторы;
      - [Линейки](./exhibits/rules) логарифмические и не только;
      - [Механические](./exhibits/mech) счетные устройства;
      - [Домеханические](./exhibits/premech) цифровые счетные устройства (счеты, палочки и другое);
      - [Электронные записные книжки](./exhibits/notebook);
      - [Прочие](./exhibits/othercategory) - в разработке.
      {% endcapture %}
      {{ details_content | markdownify }}
    </div>
  </details>

  <details>
    <summary>Искать по странам</summary>
    <div class="filter-content">
      {% capture details_content %}
      - [Советские](./exhibits/ussr) - все, связанные с СССР;
      - [Белорусские](./exhibits/belarus);
      - [Российские](./exhibits/russia);
      - [Китайские](./exhibits/china);
      - [Американские](./exhibits/usa);
      - [Немецкие](./exhibits/germany);
      - [Японские](./exhibits/japan);
      - [Прочие](./exhibits/othercountry) - в разработке.
      {% endcapture %}
      {{ details_content | markdownify }}
    </div>
  </details>
</div>

{% assign sorted_exhibits = site.exhibits | sort: "innernumber" %}
{% include exhibits-list.html 
    collection=sorted_exhibits 
    subtitle="Всего экспонатов: " | append: sorted_exhibits.size 
%}

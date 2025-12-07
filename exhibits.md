---
layout: pgs
title: "Все экспонаты коллекции"
---

На этой странице - список всех экземпляров коллекции (без разбивки по моделям). 

<!-- На данный момент описано и опубликовано экспонатов: **{{ site.exhibits.size }}** -->

Чтобы посмотреть информацию про любой экземпляр, просто кликните на его номер в коллекции!

Хотите искать по моделям? Вам  <a href="https://yprits.github.io/museum/models">сюда</a>.

Для удобства поиска всем экспонатам присвоены теги, обозначающие категорию, страну, производителя и прочее.

<details>
<summary>Искать по типу</summary>

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

</details>


<details>
<summary>Искать по странам</summary>

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

</details>

<div class="exhibits-grid">
  {% for exhibit in site.exhibits %}
    {% if exhibit.innernumber %}
    <div class="exhibit-card">
      <div class="exhibit-image">
        {% if exhibit.photo0 and exhibit.prev0 %}
          <a href="{{ exhibit.photo0 }}"><img src="{{ exhibit.prev0 }}" alt="{{ exhibit.model | default: 'Изображение экспоната' }}" loading="lazy"></a>
        {% else %}
          <img src="https://placehold.co/150x100/png?text=Фото+пока+нет&font=verdana" alt="Фотография пока не добавлена" loading="lazy">
        {% endif %}
      </div>
      <div class="exhibit-info">
        <a href="{{ exhibit.url | relative_url }}" class="exhibit-number">{{ exhibit.innernumber }}</a>
        <div class="exhibit-model">{{ exhibit.model }}</div>
        <div class="exhibit-year">{{ exhibit.prodyear | replace: ".", "." }}</div>
      </div>
    </div>
    {% endif %}
  {% endfor %}
</div>

<!-- Ну и что вы здесь ожидали увидеть? -->

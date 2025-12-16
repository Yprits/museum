---
layout: page
title: Советская техника
---

Экспонаты с тегом "СССР" ☭

О советской технике ходило немало шуток. А здесь мы показываем ее такой, какая она была на самом деле.

К советским вычислительным машинам весьма близки [белорусские](../belarus), [российские](../russia) и некоторые [другие](../others). Возможно, вы найдете то, что ищете, там?

{% assign filtered_exhibits = site.exhibits | where_exp: "item", "item.tags contains 'ussr'" %}

{% include exhibits-list.html 
    collection=filtered_exhibits 
    title="Советские экспонаты" 
    subtitle="Техника произведенная в СССР" 
%}

---
layout: pgs
title: Категории экспонатов
---

<!-- Стили для красивого отображения дерева -->
<style>
  .museum-tree {
    font-family: "Courier New", Courier, monospace;
    font-size: 15px;
    line-height: 1.4;
    background-color: #1e1e1e;
    color: #d4d4d4;
    padding: 25px;
    border-radius: 5px;
    border: 1px solid #3c3c3c;
    overflow-x: auto;
  }
  .tree-root { color: #569cd6; font-weight: bold; }
  .tree-node { color: #4ec9b0; }
  .tree-leaf { color: #ce9178; }
</style>

<!-- Блок с деревом структуры -->
<pre class="museum-tree">
<span class="tree-root">КОЛЛЕКЦИЯ</span>
├── <span class="tree-node">[В] ВЫЧИСЛИТЕЛЬНАЯ ТЕХНИКА</span>
│   ├── <span class="tree-node">[Д] Цифровая Домеханическая</span>
│   │   └── <span class="tree-leaf">[С] Счеты, абак, кости</span>
│   ├── <span class="tree-node">[М] Цифровая Механическая</span>
│   │   ├── <span class="tree-leaf">[А] Арифмометры</span>
│   │   └── <span class="tree-leaf">[Т] Табуляторы</span>
│   ├── <span class="tree-node">[Э] Цифровая Электронная</span>
│   │   ├── <span class="tree-leaf">[А] Арифметические (простейшие) калькуляторы</span>
│   │   ├── <span class="tree-leaf">[И] Инженерные калькуляторы</span>
│   │   ├── <span class="tree-leaf">[П] Программируемые калькуляторы / ЭВМ</span>
│   │   ├── <span class="tree-leaf">[К] Записные книжки, словари</span>
│   │   └── <span class="tree-leaf">[Р] Развлечения, игры, тетрисы</span>
│   ├── <span class="tree-node">[А] Аналоговая</span>
│   │   └── <span class="tree-leaf">[Л] Линейки счетные</span>
│   └── <span class="tree-node">[Х] Гибриды и нестандартные системы</span>
│       └── <span class="tree-leaf">[Х] АЦВМ, спец-прототипы</span>
│
├── <span class="tree-node">[Ч] ЧАСЫ</span>
│   ├── <span class="tree-node">[М] Механические</span>
│   │   └── <span class="tree-leaf">[Х] Баланс, маятник, гири</span>
│   ├── <span class="tree-node">[Э] Электромеханические</span>
│   │   └── <span class="tree-leaf">[Х] Камертонные, баланс с батарейкой</span>
│   ├── <span class="tree-node">[К] Кварцевые</span>
│   │   └── <span class="tree-leaf">[Х] Стрелочные, гибриды</span>
│   ├── <span class="tree-node">[Ц] Цифровые</span>
│   │   └── <span class="tree-leaf">[Х] Электронные (LED, LCD, ВЛИ)</span>
│   └── <span class="tree-node">[Х] Нестандартные хронометры</span>
│       └── <span class="tree-leaf">[Х] Прототипы, гибридные схемы</span>
│
└── <span class="tree-node">[И] ИНСТРУМЕНТ (Резерв структуры)</span>
    └── <span class="tree-node">[Х] Неизвестный / Гибридный инструмент</span>
        └── <span class="tree-leaf">[Х] Специфические приборы</span>
</pre>

<!-- Блок с правилами маркировки (вставлять ниже дерева структуры) -->
<style>
  .museum-rules {
    font-family: "Courier New", Courier, monospace;
    font-size: 14px;
    line-height: 1.5;
    background-color: #1a1a1a;
    color: #858585;
    padding: 20px;
    border-radius: 5px;
    border: 1px dashed #3c3c3c;
    margin-top: 20px;
  }
  .rules-title { color: #569cd6; font-weight: bold; }
  .rules-alert { color: #d16969; }
</style>

<div class="museum-rules">
  <span class="rules-title">// ПРАВИЛА И НЮАНСЫ МАРКИРОВКИ КОЛЛЕКЦИИ</span>
  <hr style="border: 0; border-top: 1px dashed #3c3c3c; margin: 10px 0;">
  
  1. <span class="rules-alert">СКВОЗНОЙ НОМЕР</span>: Присваивается строго хронологически в момент добавления. 
     Номер монолитен. При изменении буквенного префикса номер НЕ меняется.
     
  2. <span class="rules-alert">КОМПЛЕКТНОСТЬ</span>: Мелкие детали и крышки отдельно не маркируются. 
     Крупные составные части комплекта маркируются через дефис.
     Пример: [ВЭП-0042] — сам калькулятор, [ВЭП-0042-1] — его родной БП.
     
  3. <span class="rules-alert">ДОНОРЫ И ДЕТАЛИ</span>: Доноры идут на общих основаниях либо без маркировки. 
     Отдельные детали не маркируются. Исключение — особо ценные платы или 
     детали на демонстрационных подложках (маркируются как экспонат).
     
  4. <span class="rules-alert">ФИЛОСОФИЯ БУКВЫ [Х]</span>: Полное отсутствие четких критериев. 
     Используется для абсолютных гибридов, непостижимых конструкций, АЦВМ 
     и экспонатов, которые ломают базовую логику классификатора.

</div>

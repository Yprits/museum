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
│   │   └── <span class="tree-leaf">[ВС] Счеты, абак, кости</span>
│   ├── <span class="tree-node">[М] Цифровая Механическая</span>
│   │   ├── <span class="tree-leaf">[МА] Арифмометры</span>
│   │   └── <span class="tree-leaf">[МТ] Табуляторы</span>
│   ├── <span class="tree-node">[Э] Цифровая Электронная</span>
│   │   ├── <span class="tree-leaf">[ЭА] Арифметические калькуляторы</span>
│   │   ├── <span class="tree-leaf">[ЭИ] Инженерные калькуляторы</span>
│   │   ├── <span class="tree-leaf">[ЭП] Программируемые калькуляторы / ЭВМ</span>
│   │   ├── <span class="tree-leaf">[ЭК] Записные книжки, словари</span>
│   │   └── <span class="tree-leaf">[ЭР] Развлечения, игры, тетрисы</span>
│   ├── <span class="tree-node">[А] Аналоговая</span>
│   │   └── <span class="tree-leaf">[АЛ] Линейки логарифмические</span>
│   └── <span class="tree-node">[Х] Гибриды и нестандартные системы</span>
│       └── <span class="tree-leaf">[ХХ] АЦВМ, спец-прототипы</span>
│
├── <span class="tree-node">[Ч] ЧАСЫ</span>
│   ├── <span class="tree-node">[М] Механические</span>
│   │   └── <span class="tree-leaf">[МХ] Баланс, маятник, гири</span>
│   ├── <span class="tree-node">[Э] Электромеханические</span>
│   │   └── <span class="tree-leaf">[ЭХ] Камертонные, баланс с батарейкой</span>
│   ├── <span class="tree-node">[К] Кварцевые</span>
│   │   └── <span class="tree-leaf">[КХ] Стрелочные, гибриды</span>
│   ├── <span class="tree-node">[Ц] Цифровые</span>
│   │   └── <span class="tree-leaf">[ЦХ] Электронные (LED, LCD, ВЛИ)</span>
│   └── <span class="tree-node">[Х] Нестандартные хронометры</span>
│       └── <span class="tree-leaf">[ХХ] Прототипы, гибридные схемы</span>
│
└── <span class="tree-node">[И] ИНСТРУМЕНТ (Резерв структуры)</span>
    └── <span class="tree-node">[Х] Неизвестный / Гибридный инструмент</span>
        └── <span class="tree-leaf">[ХХ] Специфические приборы</span>
</pre>


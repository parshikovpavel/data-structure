# Heap

Куча (*heap*) — древовидная структура данных (*tree-based data structure*), которая удовлетворяет следующему свойству (свойство кучи, *heap property*): 

- для *max-heap*: для любой  *node* `C`, если `P` – это *parent node* для `C`, то `key(P) ≥ key(C)`. Т.е. *node* с наибольшим *key* всегда является *root node*
- для *min-heap*: `key(P) ≤ key(C)`. Т.е. *node* с наименьшим *key* всегда является *root node*

![hashtable](https://parshikovpavel.github.io/img/algorithm/heap.svg)



Структуру данных *heap* не следует путать с понятием *heap* в динамическом распределении памяти. В некоторых ранних популярных языках программирования (Lisp) обеспечивалось динамическое распределение памяти с использованием структуры данных «*heap*», которая и дала своё имя выделяемому объёму памяти.

*Heap* — это одна из максимально эффективных реализаций [priority queue](https://en.wikipedia.org/wiki/Priority_queue), и на самом деле *priority queue* часто называют «*heap*», независимо от того, как они могут быть реализованы. *Heap* не является *sorted structure*; ее можно считать *partially ordered*. *Heap* является полезной *data structure*, когда необходимо несколько раз удалить объект с самым высоким (или самым низким) *priority* или когда *insertion*'s должны чередоваться с *removal*'s *root node* (как в задаче top-k).









Кучи обычно реализуются в виде массивов, что исключает наличие указателей между её элементами.

Над *heap* производят операции:

- *find min (max)* – найти максимум (минимум)
- *delete max (min)* – удалить максимум (минимум)
- *increase (decrease) key* – увеличить (уменьшить) ключ – обновить некоторый ключ в *heap*
- *insert* добавить – добавление нового ключа в кучу
- *meld* слияние – соединение двух куч с целью создания новой кучи, содержащей все элементы обеих исходных (и наверное создание *heap* из `array`).

| Operation | find min | delete min | increase key | insert    | meld   |
| --------- | -------- | ---------- | ------------ | --------- | ------ |
| Binary    | `O(1)`   | `O(logN)`  | `O(logN)`    | `O(logN)` | `O(N)` |

<ins>Применение</ins>:

- пирамидальная сортировка (*heapsort*)
- очередь с приоритетами (*priority queue*, [1](#priority-queue))



## Binary heap

Наиболее часто используется *binary heap*. При этом не существует никаких ограничений относительно того, сколько узлов-потомков имеет каждая *node*, однако чаще всего используется *binary heap*.

![](../img/Max-Heap-new.svg)

*Binary heap* – почти полное *binary tree*.

*Binary heap* была впервые предложена как *data structure* для алгоритма [heapsort](https://en.wikipedia.org/wiki/Heapsort) (пирамидальная сортировка).

*Binary heap* (двои́чная ку́ча**, **пирами́да) — такое *binary tree*, для которого выполнены три условия:

1. Значение в любой *node* больше либо равно `≥` (или меньше либо равно `≤`), чем значения в *node's children*
2. Глубина всех листьев (расстояние до корня) отличается не более чем на 1 слой.
3. Последний слой заполняется слева направо без «дырок».
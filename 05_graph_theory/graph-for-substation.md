# Graph Representation for Substation

## Model (EN)
Substation topology is represented as a graph:

- Nodes → ConnectivityNode
- Edges → electrical connections

## Модель (RU)
Топология подстанции представляется в виде графа:

- Вершины → ConnectivityNode
- Рёбра → электрические соединения

---

## Dynamic Behavior
Graph changes depending on switching device states.

## Динамика
Граф изменяется в зависимости от состояния коммутационных аппаратов.

---

## Algorithm Use
- BFS → energized detection
- connected components → isolated sections

## Использование алгоритмов
- BFS → определение под напряжением
- connected components → изолированные участки
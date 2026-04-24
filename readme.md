# WinCC OA Substation Topology Processing

## Overview
This project is focused on SCADA logic development for electrical substations using IEC 61850 data models and graph-based topology processing.

The main goal is to implement dynamic detection of energized sections and visualization in WinCC OA.

## Обзор
Проект направлен на разработку логики SCADA для электрических подстанций с использованием моделей данных IEC 61850 и алгоритмов обработки топологии на основе теории графов.

Основная цель — реализовать динамическое определение участков под напряжением и их визуализацию в WinCC OA.

---

## Key Features
- Graph-based topology traversal (BFS/DFS)
- Dynamic energized section detection
- Support of switching device states (breaker/disconnector)
- Handling multiple power sources
- Real-time SCADA visualization logic

## Ключевые возможности
- Обход топологии на основе графов (BFS/DFS)
- Динамическое определение участков под напряжением
- Учет состояния коммутационных аппаратов (выключатели, разъединители)
- Поддержка нескольких источников питания
- Логика визуализации в SCADA в реальном времени

---

## Technology Stack
- WinCC OA
- IEC 61850 (logical nodes, data attributes)
- Graph theory (topology processing)

## Технологии
- WinCC OA
- IEC 61850 (логические узлы, атрибуты данных)
- Теория графов (обработка топологии)

---

## Project Structure
- Substation model based on IEC 61850
- Graph representation (nodes/edges)
- SCADA datapoint mapping
- Visualization layer

## Структура проекта
- Модель подстанции на основе IEC 61850
- Представление в виде графа (вершины/рёбра)
- Связь с datapoint в SCADA
- Уровень визуализации

---

## Example Scenarios
- Single source substation
- Multiple sources
- Isolated sections
- Switching operations impact

## Примеры сценариев
- Подстанция с одним источником
- Несколько источников питания
- Изолированные участки
- Влияние коммутаций

---

## Skills Demonstrated
- Substation automation (SAS)
- SCADA system design
- Topology processing algorithms
- IEC 61850 integration

## Демонстрируемые навыки
- Автоматизация подстанций (SAS)
- Проектирование SCADA
- Алгоритмы обработки топологии
- Интеграция IEC 61850

---

## Status
In progress (training + prototype development)

## Статус
В разработке (обучение + прототип)
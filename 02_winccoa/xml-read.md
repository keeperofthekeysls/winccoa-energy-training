XML-парсер.

SCL — это XML-файл, поэтому в WinCC OA тебе нужен разбор XML.

Что изучить:

Тема → парсинг SCL/XML

Что изучить →

структура XML
элементы и атрибуты
дерево XML
поиск узлов Substation, VoltageLevel, Bay, ConductingEquipment, Terminal, ConnectivityNode

Функции WinCC OA посмотреть →

xmlOpenDocument()
xmlGetRoot()
xmlGetChildNodes()
xmlGetNodeName()
xmlGetAttribute()
xmlCloseDocument()

Порядок →

открыть SCL как XML;
найти Substation;
пройти VoltageLevel;
пройти Bay;
найти ConnectivityNode;
найти ConductingEquipment;
у оборудования прочитать Terminal;
связать Terminal.connectivityNode с нужным ConnectivityNode.
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

int int xmlDocumentFromFile(string fileName, string &errMsg, int &errLine, int &errColumn)
Открывает файл и считывает в память все содержание, формирующее структуру DOM. Возвращает идентификатор документа, передаваемый в будущем для других вызовов XML. Возвращаемый идентификатор действителен до вызова xmlCloseDocument()
```
	//Возвращает идентификатор документа, передаваемый в будущем в для других вызовов в XML;
	int xmlDocumentFromFile(string fileName, string &errMsg, int &errLine, int &errColumn);
	fileName - абсолютный путь к открываемому файлу;
	string errMsg - Сообщение предупреждающее об ошибке;
	int errLine - Строка документа в котором произошла ошибка;
	int errColumn - Столбец документа в котором произошла ошибка;
```

int xmlChildNodes(unsigned doc, unsigned node, dyn_uint &nodes)- записывает все дочерние узлы указанного узла в параметр ссылки узла.
```
int xmlChildNodes(unsigned doc, unsigned node, dyn_uint &nodes);
	unsigned doc - Идентификатор документа (например из функции int xmlOpenDocument)
	unsigned node - Идентификатор узла
	dyn_uint &nodes - Дочерние узлы.
```
xmlGetChildNodes()
```
```
xmlGetNodeName()
```
```
xmlGetAttribute()
```
```
xmlCloseDocument()
```
```

Правильнее использовать:

Задача	Функция WinCC OA
Открыть SCL/XML файл	xmlDocumentFromFile()
Получить корневой узел	xmlFirstChild(doc)
Получить дочерние узлы	xmlChildNodes()
Получить имя узла	xmlNodeName()
Получить атрибут	xmlGetElementAttribute()
Закрыть XML-документ	xmlCloseDocument()

Порядок →

открыть SCL как XML;
найти Substation;
пройти VoltageLevel;
пройти Bay;
найти ConnectivityNode;
найти ConductingEquipment;
у оборудования прочитать Terminal;
связать Terminal.connectivityNode с нужным ConnectivityNode.
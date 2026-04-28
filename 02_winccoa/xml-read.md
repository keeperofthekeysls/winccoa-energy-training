XML-парсер.

SCL — это XML-файл, поэтому в WinCC OA нужен разбор XML.

Что изучить:

Тема → парсинг SCL/XML

Что изучить →

структура XML
элементы и атрибуты
дерево XML
поиск узлов Substation, VoltageLevel, Bay, ConductingEquipment, Terminal, ConnectivityNode



Функции WinCC OA посмотреть →

__int xmlDocumentFromFile(string fileName, string &errMsg, int &errLine, int &errColumn)__

Открывает файл и считывает в память все содержание, формирующее структуру DOM. Возвращает идентификатор документа, передаваемый в будущем для других вызовов XML. Возвращаемый идентификатор действителен до вызова xmlCloseDocument()
```
int xmlDocumentFromFile(string fileName, string &errMsg, int &errLine, int &errColumn);
	string	fileName	абсолютный путь к открываемому файлу;
	string	errMsg		Сообщение предупреждающее об ошибке;
	int		errLine		Строка документа в котором произошла ошибка;
	int 	errColumn	Столбец документа в котором произошла ошибка;
```

__int xmlChildNodes(unsigned doc, unsigned node, dyn_uint &nodes)__

записывает все дочерние узлы указанного узла в параметр ссылки узла.
```
int xmlChildNodes(unsigned doc, unsigned node, dyn_uint &nodes);
	unsigned 	doc			Идентификатор документа (например из функции int xmlOpenDocument)
	unsigned 	node		Идентификатор узла
	dyn_uint 	&nodes		Дочерние узлы. (возвращаемый параметр)
	
Example: int k = xmlChildNodes(docNum,Pnode,nodes);
```

__string xmlNodeName()__

Возвращает имя узла.
```
string xmlNodeName(unsigned doc, unsigned node);
unsigned	doc		Идентификатор документа, возвращаемый, например, xmlNewDocument().
unsigned	node	Идентификатор узла.
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
Получить дочерние узлы	
Получить имя узла	
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
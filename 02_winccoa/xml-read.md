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

__string xmlNodeName(unsigned doc, unsigned node)__

Возвращает имя узла.
```
string xmlNodeName(unsigned doc, unsigned node);
unsigned	doc		Идентификатор документа, возвращаемый, например, xmlNewDocument().
unsigned	node	Идентификатор узла.
```
Возвращает имя узла.Значение имени зависит от типа опрашиваемого узла. Все указанные имена типа узла представляют собой целочисленные константы, которые доступны в сценарии CTRL во время использования расширения "CtrlXml".Определены следующие константы типа узла:

Константа						Значение
XML_ATTRIBUTE_NODE				Имя атрибута
XML_CDATA_						SECTION_NODE	Строка "#cdata-section"
XML_COMMENT_NODE				Строка "#comment"
XML_DOCUMENT_NODE				Строка "#document"
XML_DOCUMENT_FRAGMENT_NODE		Строка "#document-fragment"
XML_DOCUMENT_TYPE_NODE			Имя типа документа
XML_ELEMENT_NODE				Имя тега
XML_ENTITY_NODE					Имя узла
XML_ENTITY_REFERENCE_NODE		Имя узла ссылки
XML_NOTATION_NODE				Имя аларма
XML_PROCESSING_INSTRUCTION_NODE	Цель оператора обработки
XML_TEXT_NODE					Строка "#text"


__xmlGetElementAttribute()__
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
Получить атрибут	
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
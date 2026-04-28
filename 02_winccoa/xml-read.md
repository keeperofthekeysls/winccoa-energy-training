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


//Открывает файл и считывает в память все содержание, формирующее структуру DOM. Возвращает идентификатор документа, передаваемый в будущем для других вызовов XML. Возвращаемый идентификатор действителен до вызова //xmlCloseDocument()
int xmlOpenDocument () // не нашел данную функцию на ресурсе winccoa.com. Смотри вложенную функцию
{
	//есть функция
	//Возвращает идентификатор документа, передаваемый в будущем в для других вызовов в XML;
	int xmlDocumentFromFile(string fileName, string &errMsg, int &errLine, int &errColumn);
	fileName - абсолютный путь к открываемому файлу;
	string errMsg - Сообщение предупреждающее об ошибке;
	int errLine - Строка документа в котором произошла ошибка;
	int errColumn - Столбец документа в котором произошла ошибка;
}


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
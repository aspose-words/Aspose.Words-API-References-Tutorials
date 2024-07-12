---
title: Диапазон тегов структурированного документа. Начало сопоставления XML.
linktitle: Диапазон тегов структурированного документа. Начало сопоставления XML.
second_title: API обработки документов Aspose.Words
description: Узнайте, как настроить сопоставление XML для начала диапазона тегов структурированного документа в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

В этом руководстве объясняется, как настроить сопоставление XML для начала диапазона тегов структурированного документа в документе Word с помощью Aspose.Words для .NET. Сопоставление XML позволяет отображать определенные части источника данных XML в элементе управления содержимым.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ и создайте XML-часть.
 Загрузите документ Word, используя`Document`конструктор, передавая путь к документу в качестве параметра. Создайте часть XML, содержащую данные, которые вы хотите отобразить в теге структурированного документа.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Шаг 3. Установите сопоставление XML для тега структурированного документа
Получите диапазон тегов структурированного документа, начинающийся с документа. Затем настройте сопоставление XML для тега структурированного документа, чтобы отображать определенную часть пользовательской части XML с помощью выражения XPath.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Шаг 4. Сохраните документ
 Сохраните измененный документ в указанную директорию, используя команду`Save` метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Пример исходного кода для диапазона тегов структурированного документа. Начало сопоставления XML с использованием Aspose.Words для .NET. 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Создайте часть XML, содержащую данные, и добавьте ее в коллекцию CustomXmlPart документа.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Создайте StructuredDocumentTag, который будет отображать содержимое нашей CustomXmlPart в документе.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// Если мы установим сопоставление для нашего StructuredDocumentTag,
	//он будет отображать только часть CustomXmlPart, на которую указывает XPath.
	// Этот XPath будет указывать на содержимое второго элемента «<text>» первого элемента «<root>» нашей CustomXmlPart.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

Вот и все! Вы успешно настроили сопоставление XML для начала диапазона тегов структурированного документа в документе Word с помощью Aspose.Words для .NET.
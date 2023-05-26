---
title: Начало Xml-сопоставления диапазона тегов структурированного документа
linktitle: Начало Xml-сопоставления диапазона тегов структурированного документа
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как настроить сопоставление XML для диапазона тегов структурированного документа, начиная с документа Word, используя Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

В этом руководстве объясняется, как настроить сопоставление XML для начала диапазона тегов структурированного документа в документе Word с использованием Aspose.Words для .NET. Сопоставление XML позволяет отображать определенные части источника данных XML в элементе управления содержимым.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и работы с документами Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ и создайте часть XML
 Загрузите документ Word с помощью`Document` конструктор, передавая путь к документу в качестве параметра. Создайте часть XML, содержащую данные, которые вы хотите отобразить в теге структурированного документа.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Шаг 3. Установите сопоставление XML для тега структурированного документа
Получить диапазон тегов структурированного документа, начиная с документа. Затем задайте сопоставление XML для тега структурированного документа для отображения определенной части пользовательской части XML с использованием выражения XPath.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Шаг 4: Сохраните документ
 Сохраните измененный документ в указанную директорию с помощью`Save` метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Пример исходного кода для сопоставления начала Xml диапазона тегов структурированного документа с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Создайте часть XML, содержащую данные, и добавьте ее в коллекцию CustomXmlPart документа.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Создайте StructuredDocumentTag, который будет отображать содержимое нашего CustomXmlPart в документе.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// Если мы установим сопоставление для нашего StructuredDocumentTag,
	// он будет отображать только часть CustomXmlPart, на которую указывает XPath.
	// Этот XPath будет указывать на содержимое второго элемента "<text>" первого элемента "<root>" нашего CustomXmlPart.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

Вот и все! Вы успешно настроили сопоставление XML для начала диапазона тегов структурированного документа в документе Word с помощью Aspose.Words для .NET.
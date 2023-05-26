---
title: Создание повторяющегося раздела таблицы, сопоставленного с настраиваемой частью XML
linktitle: Создание повторяющегося раздела таблицы, сопоставленного с настраиваемой частью XML
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как создать таблицу с повторяющимся разделом, сопоставленным с CustomXmlPart в документе Word, используя Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

В этом руководстве показано, как создать таблицу с повторяющимся разделом, сопоставленным с пользовательской частью Xml в документе Word с помощью Aspose.Words для .NET. Повторяющийся раздел позволяет динамически добавлять строки на основе данных XML, хранящихся в пользовательской части Xml.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и работы с документами Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"`с фактическим путем к каталогу, в котором вы хотите сохранить документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте документ и DocumentBuilder
 Создайте новый экземпляр`Document` класс и`DocumentBuilder` для построения содержимого документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Добавьте пользовательские данные XML в CustomXmlPart
 Создать`CustomXmlPart` и добавьте к нему пользовательские XML-данные. В этом примере мы создаем строку XML, представляющую набор книг с их названиями и авторами.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Шаг 4: Создайте таблицу и структуру таблицы
 Начните создавать таблицу с помощью`StartTable` метод`DocumentBuilder` . Добавьте ячейки таблицы и содержимое, используя`InsertCell` и`Write` методы.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Шаг 5. Создайте повторяющийся раздел, сопоставленный с пользовательским XML
 Создать`StructuredDocumentTag` с`SdtType.RepeatingSection` для представления повторяющегося раздела. Задайте сопоставление XML для повторяющегося раздела с помощью`SetMapping` метод`XmlMapping` свойство. В этом примере мы сопоставляем повторяющийся раздел с`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Шаг 6: Создайте элемент повторяющегося раздела и добавьте ячейки
 Создать`StructuredDocumentTag` с`SdtType.RepeatingSectionItem` для представления повторяющегося элемента раздела. Добавьте его как дочерний к повторяющемуся разделу.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Создать`Row`для представления каждого элемента в повторяющемся разделе и добавления его к элементу повторяющегося раздела.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Шаг 7. Добавьте элементы управления содержимым в повторяющийся раздел
 Создавать`StructuredDocumentTag` объекты с`SdtType.PlainText`

  для представления элементов управления содержимым заголовка и автора. Задайте сопоставление XML для каждого элемента управления содержимым с помощью`SetMapping` метод`XmlMapping` свойство. В этом примере мы сопоставляем элемент управления title с`/books[1]/book[1]/title[1]` и автор контролирует`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Шаг 8: Сохраните документ
 Сохраните измененный документ в указанную директорию с помощью`Save` метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Пример исходного кода для создания повторяющегося раздела таблицы, сопоставленного с пользовательской частью XML, с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

Вот и все! Вы успешно создали таблицу с повторяющимся разделом, сопоставленным с CustomXmlPart в документе Word с помощью Aspose.Words для .NET.
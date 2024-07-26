---
title: Создание повторяющегося раздела таблицы, сопоставленного с пользовательской частью XML
linktitle: Создание повторяющегося раздела таблицы, сопоставленного с пользовательской частью XML
second_title: API обработки документов Aspose.Words
description: Узнайте, как создать таблицу с повторяющимся разделом, сопоставленным с CustomXmlPart в документе Word, с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

В этом руководстве показано, как создать таблицу с повторяющимся разделом, сопоставленную с пользовательской частью Xml в документе Word, с помощью Aspose.Words для .NET. Повторяющийся раздел позволяет динамически добавлять строки на основе данных XML, хранящихся в пользовательской части XML.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором вы хотите сохранить документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Создайте документ и DocumentBuilder
 Создайте новый экземпляр`Document` класс и`DocumentBuilder` для построения содержания документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Добавьте пользовательские XML-данные в CustomXmlPart.
 Создать`CustomXmlPart` и добавьте в него пользовательские XML-данные. В этом примере мы создаем строку XML, представляющую коллекцию книг с их названиями и авторами.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Шаг 4. Создайте таблицу и структуру таблицы.
Начните создавать таблицу с помощью`StartTable` метод`DocumentBuilder` . Добавьте ячейки и содержимое таблицы, используя`InsertCell`и`Write` методы.

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
 Создать`StructuredDocumentTag` с`SdtType.RepeatingSection` для обозначения повторяющегося раздела. Установите сопоставление XML для повторяющегося раздела с помощью`SetMapping` метод`XmlMapping` свойство. В этом примере мы сопоставляем повторяющийся раздел с`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Шаг 6. Создайте повторяющийся элемент раздела и добавьте ячейки
 Создать`StructuredDocumentTag` с`SdtType.RepeatingSectionItem` для представления повторяющегося элемента раздела. Добавьте его как дочерний элемент в повторяющийся раздел.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Создать`Row` для представления каждого элемента в повторяющемся разделе и добавления его к элементу повторяющегося раздела.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Шаг 7. Добавьте элементы управления содержимым в повторяющийся раздел.
 Создавать`StructuredDocumentTag` объекты с`SdtType.PlainText`

  для представления элементов управления заголовком и авторским контентом. Установите сопоставление XML для каждого элемента управления содержимым, используя`SetMapping` метод`XmlMapping` свойство. В этом примере мы сопоставляем элемент управления заголовком с`/books[1]/book[1]/title[1]` и автор контролирует`/books[1]/book[1]/author[1]`.

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
 Сохраните измененный документ в указанную директорию, используя команду`Save`метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Пример исходного кода для создания повторяющегося раздела таблицы, сопоставленного с пользовательской частью XML, с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
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

Вот и все! Вы успешно создали таблицу с повторяющимся разделом, сопоставленным с CustomXmlPart в вашем документе Word, используя Aspose.Words для .NET.
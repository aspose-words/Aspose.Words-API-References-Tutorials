---
title: Создание повторяющегося раздела таблицы, сопоставленного с пользовательской частью XML
linktitle: Создание повторяющегося раздела таблицы, сопоставленного с пользовательской частью XML
second_title: API обработки документов Aspose.Words
description: Узнайте, как создать таблицу с повторяющимся разделом, сопоставленным с CustomXmlPart в документе Word, с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---
## Введение

В этом руководстве мы рассмотрим процесс создания таблицы с повторяющимся разделом, который сопоставляется с пользовательской частью XML с помощью Aspose.Words для .NET. Это особенно полезно для динамического создания документов на основе структурированных данных.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующее:
1.  Установлена библиотека Aspose.Words для .NET. Вы можете скачать его с сайта[Веб-сайт Aspose](https://releases.aspose.com/words/net/).
2. Базовое понимание C# и XML.

## Импортировать пространства имен

Обязательно включите в свой проект необходимые пространства имен:

```csharp
using Aspose.Words;
using Aspose.Words.Markup;
using Aspose.Words.Tables;
```

## Шаг 1. Инициализируйте документ и DocumentBuilder

 Сначала создайте новый документ и инициализируйте`DocumentBuilder`:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Добавьте пользовательскую часть XML

Добавьте в документ пользовательскую часть XML. Этот XML содержит данные, которые мы хотим сопоставить с нашей таблицей:

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
    "<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
    "<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
    "<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Шаг 3. Создайте структуру таблицы

 Далее используйте`DocumentBuilder` чтобы создать заголовок таблицы:

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Шаг 4: Создайте повторяющийся раздел

 Создайте`StructuredDocumentTag` (SDT) для повторяющегося раздела и сопоставьте его с данными XML:

```csharp
StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Шаг 5. Создайте повторяющийся элемент раздела

Создайте SDT для элемента повторяющегося раздела и добавьте его в повторяющийся раздел:

```csharp
StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Шаг 6. Сопоставьте XML-данные с ячейками таблицы

Создайте SDT для названия и автора, сопоставьте их с данными XML и добавьте в строку:

```csharp
StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Шаг 7: Сохраните документ

Наконец, сохраните документ в указанном каталоге:

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

## Заключение

Выполнив эти шаги, вы успешно создали таблицу с повторяющимся разделом, сопоставленную с пользовательской частью XML с помощью Aspose.Words для .NET. Это позволяет создавать динамический контент на основе структурированных данных, что делает создание документов более гибким и эффективным.

## Часто задаваемые вопросы

### Что такое тег структурированного документа (SDT)?
SDT, также известный как элемент управления содержимым, представляет собой ограниченную область документа, которая используется для хранения структурированных данных.

### Могу ли я использовать другие типы данных в пользовательской части XML?
Да, вы можете структурировать свою пользовательскую часть XML с любыми типами данных и соответствующим образом сопоставить их.

### Как добавить больше строк в повторяющийся раздел?
Повторяющийся раздел автоматически реплицирует структуру строк для каждого элемента сопоставленного пути XML.
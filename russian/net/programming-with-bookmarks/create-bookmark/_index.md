---
title: Создать закладку
linktitle: Создать закладку
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как создавать закладки в документе и указывать уровни предварительного просмотра закладок в PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/create-bookmark/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию «Создать закладку» в библиотеке Aspose.Words для .NET. Эта функция позволяет создавать закладки в документе и указывать уровни предварительного просмотра закладок в выходном файле PDF.

## Предпосылки

- Базовые знания языка С#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1: Создание документа и генератора

 Перед созданием закладок нам нужно создать документ и конструктор документов с помощью`Document` и`DocumentBuilder` объекты:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2: Создание основной закладки

 Мы используем`StartBookmark` способ запуска основной закладки и`EndBookmark` способ покончить с этим. Между ними мы можем добавить текст и другие закладки:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Добавьте сюда больше закладок или текста.

builder. EndBookmark("My Bookmark");
```

## Шаг 3: Создание вложенных закладок

 Мы также можем создавать вложенные закладки внутри основной закладки. Мы используем то же самое`StartBookmark` и`EndBookmark` методы для создания и закрытия вложенных закладок:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Шаг 4. Указание уровней предварительного просмотра закладок в выходном PDF-файле

 Мы используем`PdfSaveOptions` объект, чтобы указать уровни предварительного просмотра закладок в выходном файле PDF. Мы используем`BookmarksOutlineLevels` свойство

  чтобы добавить основные закладки и вложенные закладки с соответствующими уровнями:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Пример исходного кода для создания закладки с использованием Aspose.Words для .NET

Вот полный пример исходного кода, демонстрирующий создание закладок с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию «Создать закладку» Aspose.Words для .NET. Мы следовали пошаговому руководству по созданию закладок в документе и указанию уровней предварительного просмотра закладок в выходном PDF-файле.
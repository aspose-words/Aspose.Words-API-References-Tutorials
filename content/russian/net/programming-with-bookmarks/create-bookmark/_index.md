---
title: Создать закладку в документе Word
linktitle: Создать закладку в документе Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как создавать закладки в документе Word и указывать уровни предварительного просмотра закладок в PDF-файлах с помощью Aspose.Words для .NET.
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

### Часто задаваемые вопросы

#### В: Каковы предварительные условия для использования функции «Создать закладки» в Aspose.Words для .NET?

О: Для использования функции "Создать закладки" в Aspose.Words for .NET необходимо иметь базовые знания языка C#. Вам также потребуется среда разработки .NET с установленной библиотекой Aspose.Words.

#### В: Как создать документ в Aspose.Words для .NET?

 О: Чтобы создать документ в Aspose.Words для .NET, вы можете использовать`Document`сорт. Вот пример кода:

```csharp
Document doc = new Document();
```

#### В: Как создать главную закладку в документе с помощью Aspose.Words для .NET?

 О: Чтобы создать основную закладку в документе с помощью Aspose.Words for .NET, вы можете использовать`StartBookmark` метод, чтобы запустить закладку, добавить текст или другие закладки внутрь, а затем использовать` EndBookmark` покончить с этим. Вот пример кода:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### В: Как создать вложенную закладку внутри основной закладки с помощью Aspose.Words для .NET?

 О: Чтобы создать вложенную закладку внутри основной закладки с помощью Aspose.Words for .NET, вы можете использовать тот же`StartBookmark` и`EndBookmark` методы запуска и завершения вложенной закладки. Вот пример кода:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### Вопрос. Как указать уровни предварительного просмотра закладок в выходном PDF-файле с помощью Aspose.Words для .NET?

 О: Чтобы указать уровни предварительного просмотра закладок в выходном PDF-файле с помощью Aspose.Words for .NET, вы можете использовать`PdfSaveOptions` класс и`BookmarksOutlineLevels` свойство. Вы можете добавить основные закладки и вложенные закладки с соответствующими уровнями. Вот пример кода:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### В: Как сохранить документ после создания закладок с помощью Aspose.Words для .NET?

 О: Чтобы сохранить документ после создания закладок с помощью Aspose.Words for .NET, вы можете использовать`Save` метод`Document` объект, указывающий путь к файлу назначения. Вот пример кода:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### Вопрос. Как указать уровни предварительного просмотра закладок в выходном PDF-файле с помощью Aspose.Words для .NET?

 О: Чтобы указать уровни предварительного просмотра закладок в выходном PDF-файле с помощью Aspose.Words for .NET, вы можете использовать`PdfSaveOptions` класс и`BookmarksOutlineLevels` свойство. Вы можете добавить основные закладки и вложенные закладки с соответствующими уровнями. Вот пример кода:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### В: Как создать вложенные закладки внутри основной закладки с помощью Aspose.Words для .NET?

 О: Чтобы создать вложенные закладки внутри основной закладки с помощью Aspose.Words for .NET, вы можете использовать тот же`StartBookmark` и`EndBookmark` методы запуска и завершения вложенных закладок. Обязательно укажите родительскую закладку в качестве параметра при вызове`StartBookmark` метод. Вот пример кода:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### В: Как добавить текст внутри закладки с помощью Aspose.Words для .NET?

 О: Чтобы добавить текст внутри закладки с помощью Aspose.Words for .NET, вы можете использовать`Write` метод`DocumentBuilder` объект, определяющий текст для добавления. Вот пример кода:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### В: Как создать главную закладку в документе с помощью Aspose.Words для .NET?

 О: Чтобы создать основную закладку в документе с помощью Aspose.Words for .NET, вы можете использовать`StartBookmark` способ запуска закладки и`EndBookmark` способ покончить с этим. Вот пример кода:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```
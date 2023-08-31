---
title: Столбцы таблицы закладок в документе Word
linktitle: Столбцы таблицы закладок в документе Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить в закладки столбец таблицы в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/bookmark-table-columns/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию столбцов таблицы закладок в библиотеке Aspose.Words для .NET. Эта функция позволяет вам добавить в закладки определенный столбец таблицы в документе Word и получить доступ к содержимому этого столбца.

## Предварительные условия

- Базовые знания языка C#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1: Создание таблицы

 Прежде чем создавать закладку в столбце таблицы, мы должны сначала создать таблицу, используя`DocumentBuilder` объект. В нашем примере мы создаем таблицу с двумя строками и двумя столбцами:

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## Шаг 2. Создание закладки столбца

 Мы используем`StartBookmark` метод для создания закладки в определенном столбце таблицы. В нашем примере мы используем имя «MyBookmark» для закладки:

```csharp
builder. StartBookmark("MyBookmark");
```

## Шаг 3. Получите доступ к содержимому столбца

 Проходимся по всем закладкам в документе и отображаем их названия. Если закладка представляет собой столбец, мы получаем доступ к содержимому этого столбца, используя индекс столбца и`GetText` метод:

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### Пример исходного кода для столбцов таблицы закладок с использованием Aspose.Words для .NET

Вот полный пример исходного кода, демонстрирующий создание закладки в столбце таблицы с помощью Aspose.Words для .NET:

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию столбцов таблицы закладок в Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы добавить в закладки определенный столбец таблицы в документе Word и перейти к содержимому этого столбца.

### Часто задаваемые вопросы по столбцам таблицы закладок в документе Word

#### Вопрос: Каковы необходимые условия для использования функции «Закладки для столбцов таблицы» в Aspose.Words for .NET?

О: Чтобы использовать функцию «Закладки для столбцов таблицы» в Aspose.Words for .NET, вам необходимо иметь базовые знания языка C#. Вам также потребуется среда разработки .NET с установленной библиотекой Aspose.Words.

#### Вопрос: Как создать таблицу со столбцами в документе Word с помощью Aspose.Words for .NET?

 О: Чтобы создать таблицу со столбцами в документе Word с помощью Aspose.Words for .NET, вы можете использовать`DocumentBuilder`объект для вставки ячеек и содержимого в таблицу. Вот пример кода:

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### Вопрос: Как добавить в закладки столбец таблицы с помощью Aspose.Words для .NET?

 О: Чтобы создать закладку в столбце таблицы с помощью Aspose.Words for .NET, вы можете использовать команду`StartBookmark` метод`DocumentBuilder` объект, чтобы начать закладку в определенном столбце таблицы. Вот пример кода:

```csharp
builder.StartBookmark("MyBookmark");
```

#### Вопрос: Как получить доступ к содержимому столбца таблицы из закладки с помощью Aspose.Words for .NET?

О: Чтобы получить доступ к содержимому столбца таблицы из закладки с помощью Aspose.Words для .NET, вы можете просмотреть все закладки в документе, проверить, является ли закладка столбцом, и использовать индекс столбца для доступа к содержимому этот столбец. Вот пример кода:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // Сделайте что-нибудь с содержимым столбца...
         }
     }
}
```

#### Вопрос: Существует ли ограничение на количество столбцов, которые я могу создать в таблице с закладками столбцов?

О: Не существует определенного ограничения на количество столбцов, которые вы можете создать в таблице с закладками столбцов, используя Aspose.Words для .NET. Ограничение в основном зависит от ресурсов, доступных в вашей системе, и характеристик используемого вами формата файла Word. Однако не рекомендуется создавать слишком большое количество столбцов, так как это может повлиять на производительность и читаемость итогового документа.
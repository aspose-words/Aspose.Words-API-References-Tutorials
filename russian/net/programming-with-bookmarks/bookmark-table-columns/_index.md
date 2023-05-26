---
title: Столбцы таблицы закладок
linktitle: Столбцы таблицы закладок
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как создать закладку для столбца таблицы в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/bookmark-table-columns/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию Bookmark Table Columns в библиотеке Aspose.Words для .NET. Эта функция позволяет добавить в закладки определенный столбец таблицы в документе Word и получить доступ к содержимому этого столбца.

## Предпосылки

- Базовые знания языка С#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1: Создание таблицы

 Перед созданием закладки в столбце таблицы мы должны сначала создать таблицу, используя`DocumentBuilder` объект. В нашем примере мы создаем таблицу с двумя строками и двумя столбцами:

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

## Шаг 2: Создание закладки столбца

 Мы используем`StartBookmark`способ создания закладки в определенном столбце таблицы. В нашем примере мы используем имя «MyBookmark» для закладки:

```csharp
builder. StartBookmark("MyBookmark");
```

## Шаг 3. Доступ к содержимому столбца

 Проходим по всем закладкам в документе и выводим их названия. Если закладка является столбцом, мы получаем доступ к содержимому этого столбца, используя индекс столбца и`GetText` метод:

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

Вот полный образец исходного кода, демонстрирующий создание закладки в столбце таблицы с помощью Aspose.Words для .NET:

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

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию столбцов таблицы закладок Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы добавить в закладки определенный столбец таблицы в документе Word и перейти к содержимому этого столбца.
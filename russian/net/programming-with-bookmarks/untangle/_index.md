---
title: распутать
linktitle: распутать
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как распутать вложенные закладки в соседних строках таблицы с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/untangle/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию Untangle в библиотеке Aspose.Words для .NET. Эта функция раскрывает вложенные закладки, находящиеся в соседних строках таблицы.

## Предпосылки

- Базовые знания языка С#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1. Просмотр закладок документа

Мы используем цикл foreach для перебора всех закладок, присутствующих в документе:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Код для обработки закладок здесь
}
```

## Шаг 2. Получите родительские строки из закладок

 Мы используем`GetAncestor` методы для получения родительских строк начального и конечного узлов закладки:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## Шаг 3. Распутайте вложенные закладки

Если обе родительские строки найдены и закладка начинается и заканчивается в соседних строках, мы перемещаем конечный узел закладки в конец последнего абзаца последней ячейки в верхней строке:

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Пример исходного кода для Untangle с использованием Aspose.Words для .NET

Вот полный пример исходного кода для распутывания вложенных закладок с помощью Aspose.Words для .NET:

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// Получите родительскую строку как закладки, так и конечного узла закладки.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// Если обе строки найдены в порядке, а начало и конец закладки содержатся в соседних строках,
		// переместите конечный узел закладки в конец последнего абзаца в последней ячейке верхней строки.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию Untangle Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы распутать вложенные закладки в соседних строках таблицы.
---
title: Распутать ряд закладок
linktitle: Распутать ряд закладок
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как распутать вложенные закладки строк, чтобы удалить определенные строки, не затрагивая другие закладки.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/untangle-row-bookmarks/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию Untangle Row Bookmarks в библиотеке Aspose.Words для .NET. Эта функция позволяет ставить концы закладок строк в той же строке, что и начала закладок.

## Предпосылки

- Базовые знания языка С#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1: Загрузка документа

 Мы используем`Document` класс для загрузки существующего документа из файла:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Шаг 2: распутать закладки линий

 Мы используем`Untangle` функция для распутывания закладок из строк. Эта функция выполняет пользовательскую задачу по размещению концов строк закладки в той же строке, где начинается закладка:

```csharp
Untangle(doc);
```

## Шаг 3. Удалить строку по закладке

 Мы используем`DeleteRowByBookmark` функция для удаления определенной строки по ее закладке:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Шаг 4. Проверьте целостность других закладок

Мы проверяем, что другие закладки не были повреждены, проверяя, присутствует ли конец закладки:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Пример исходного кода для Untangle Row Bookmarks с использованием Aspose.Words для .NET**

Вот полный пример исходного кода для распутывания закладок из строк с помощью Aspose.Words для .NET:


```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Это выполняет пользовательскую задачу по размещению концов закладки строки в той же строке, где начинается закладка.
	Untangle(doc);

	// Теперь мы можем легко удалять строки по закладке, не повреждая закладки других строк.
	DeleteRowByBookmark(doc, "ROW2");

	// Это просто для проверки того, что другая закладка не была повреждена.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию Untangle Row Bookmarks в Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы распутать закладки строк и удалить определенную строку, не повреждая другие закладки.
---
title: Показать скрыть закладки
linktitle: Показать скрыть закладки
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как показать или скрыть определенную закладку в документе с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/show-hide-bookmarks/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию Show Hide Bookmarks в библиотеке Aspose.Words для .NET. Эта функция позволяет отображать или скрывать определенные закладки в документе.

## Предпосылки

- Базовые знания языка С#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1: Загрузка документа

 Мы используем`Document` класс для загрузки существующего документа из файла:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Шаг 2. Показать или скрыть определенную закладку

 Мы используем`ShowHideBookmarkedContent` функция, чтобы показать или скрыть определенную закладку в документе. Эта функция принимает в качестве параметров документ, имя закладки и логическое значение, указывающее, показывать или скрывать закладку:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Шаг 3: Сохранение измененного документа

 Мы используем`Save` метод сохранения измененного документа в файл:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Пример исходного кода для отображения скрытых закладок с использованием Aspose.Words для .NET

Вот полный пример исходного кода, демонстрирующий отображение или скрытие определенной закладки с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию Show Hide Bookmarks в Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы показать или скрыть определенную закладку в документе.
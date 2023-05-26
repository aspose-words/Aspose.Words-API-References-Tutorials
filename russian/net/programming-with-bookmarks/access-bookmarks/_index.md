---
title: Доступ к закладкам
linktitle: Доступ к закладкам
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как получить доступ к закладкам в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/access-bookmarks/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию Access Bookmarks в библиотеке Aspose.Words для .NET. Эта функция обеспечивает доступ к определенным закладкам в документе Word.

## Предпосылки

- Базовые знания языка С#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1: Загрузка документа

 Прежде чем мы начнем получать доступ к закладкам, нам нужно загрузить документ Word, используя Aspose.Words для .NET. Это можно сделать, создав экземпляр`Document` объект, указывающий путь к файлу документа:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Шаг 2. Доступ к закладкам

После загрузки документа мы можем получить доступ к закладкам в документе. Существует два способа доступа к закладкам: по индексу и по имени.

- Доступ по индексу: в нашем примере мы используем индекс 0 для доступа к первой закладке документа:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Доступ по имени: в нашем примере мы используем имя «MyBookmark3» для доступа к определенной закладке в документе:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

### Пример исходного кода для доступа к закладкам с использованием Aspose.Words для .NET

Вот полный пример исходного кода, демонстрирующий доступ к закладкам с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");
	
	// По индексу:
	Bookmark bookmark1 = doc.Range.Bookmarks[0];
	// По имени:
	Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
   
```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию Access Bookmarks в Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы загрузить документ и получить доступ к закладкам, используя индекс и имя.
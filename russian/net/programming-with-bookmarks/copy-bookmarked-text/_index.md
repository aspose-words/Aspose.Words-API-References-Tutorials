---
title: Копировать текст с закладками
linktitle: Копировать текст с закладками
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как скопировать текст закладки из исходного документа в другой документ с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/copy-bookmarked-text/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию «Копировать текст с закладками» в библиотеке Aspose.Words для .NET. Эта функция позволяет копировать содержимое определенной закладки из исходного документа в другой документ.

## Предпосылки

- Базовые знания языка С#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1: Загрузка исходного документа

 Перед копированием текста закладки нам нужно загрузить исходный документ в`Document` объект, используя путь к файлу:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Шаг 2: Получение исходной закладки

 Мы используем`Bookmarks` диапазон исходного документа, чтобы получить конкретную закладку, которую мы хотим скопировать:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Шаг 3: Создание целевого документа

Мы создаем новый документ, который будет служить целевым документом для копирования содержимого закладки:

```csharp
Document dstDoc = new Document();
```

## Шаг 4: Указание места для копирования

Мы указываем место, куда мы хотим добавить скопированный текст. В нашем примере мы добавляем текст в конец тела последнего раздела целевого документа:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Шаг 5. Импортируйте и скопируйте текст закладки

 Мы используем`NodeImporter`объект для импорта и копирования текста закладки из исходного документа в целевой документ:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Пример исходного кода для копирования текста с закладками с использованием Aspose.Words для .NET

Вот полный пример исходного кода, демонстрирующий копирование текста из закладки с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Это закладка, содержимое которой мы хотим скопировать.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Мы будем дополнять этот документ.
	Document dstDoc = new Document();

	// Допустим, мы будем добавлены в конец тела последнего раздела.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Если вы импортируете несколько раз без единого контекста, это приведет к созданию множества стилей.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию «Копировать текст с закладками» из Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы скопировать содержимое закладки из исходного документа в другой документ.
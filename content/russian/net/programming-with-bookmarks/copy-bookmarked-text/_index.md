---
title: Копировать текст с закладками в документ Word
linktitle: Копировать текст с закладками в документ Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как скопировать текст закладки из документа Word в другой документ с помощью Aspose.Words для .NET.
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

 Мы используем`NodeImporter` объект для импорта и копирования текста закладки из исходного документа в целевой документ:

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

	//Допустим, мы будем добавлены в конец тела последнего раздела.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Если вы импортируете несколько раз без единого контекста, это приведет к созданию множества стилей.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию «Копировать текст с закладками» из Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы скопировать содержимое закладки из исходного документа в другой документ.

### Часто задаваемые вопросы по копированию текста с закладками в документе Word

#### В: Каковы требования для использования функции «Копировать текст с закладками» в Aspose.Words для .NET?

О: Чтобы использовать функцию "Копировать текст с закладками" в Aspose.Words для .NET, вам необходимо иметь базовые знания языка C#. Вам также потребуется среда разработки .NET с установленной библиотекой Aspose.Words.

#### В: Как загрузить исходный документ в Aspose.Words для .NET?

 О: Чтобы загрузить исходный документ в Aspose.Words для .NET, вы можете использовать`Document`class, указав путь к файлу документа. Вот пример кода:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### В: Как получить содержимое определенной закладки в исходном документе с помощью Aspose.Words для .NET?

 О: Чтобы получить содержимое определенной закладки в исходном документе с помощью Aspose.Words for .NET, вы можете получить доступ к`Bookmarks` свойство диапазона исходного документа и использовать имя закладки для извлечения конкретной закладки. Вот пример кода:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### В: Как указать расположение копии текста закладки в целевом документе с помощью Aspose.Words for .NET?

 О: Чтобы указать, куда вы хотите добавить скопированный текст закладки в целевом документе с помощью Aspose.Words для .NET, вы можете перейти к основной части последнего раздела целевого документа. Вы можете использовать`LastSection` свойство для доступа к последнему разделу и`Body` свойство для доступа к телу этого раздела. Вот пример кода:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### В: Как импортировать и копировать текст закладки из исходного документа в целевой документ с помощью Aspose.Words для .NET?

О: Чтобы импортировать и копировать текст закладки из исходного документа в целевой документ с помощью Aspose.Words for .NET, вы можете использовать`NodeImporter` класс, указывающий исходный документ, целевой документ и режим форматирования, который необходимо сохранить. Затем вы можете использовать`AppendBookmarkedText` способ добавления текста закладки в конечный документ. Вот пример кода:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### В: Как сохранить целевой документ после копирования текста закладки с помощью Aspose.Words для .NET?

 О: Чтобы сохранить целевой документ после копирования текста из закладки с помощью Aspose.Words for .NET, вы можете использовать`Save` метод`Document` объект, указывающий путь к файлу назначения. Вот пример кода:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```
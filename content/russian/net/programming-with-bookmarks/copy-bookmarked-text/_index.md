---
title: Копировать текст с закладкой в документ Word
linktitle: Копировать текст с закладкой в документ Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как скопировать текст закладки из документа Word в другой документ с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/copy-bookmarked-text/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию копирования текста с закладками в библиотеке Aspose.Words для .NET. Эта функция позволяет копировать содержимое определенной закладки из исходного документа в другой документ.

## Предварительные условия

- Базовые знания языка C#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1. Загрузка исходного документа

 Прежде чем копировать текст закладки, нам необходимо загрузить исходный документ в`Document` объект, используя путь к файлу:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Шаг 2. Получение исходной закладки

 Мы используем`Bookmarks` свойство диапазона исходного документа, чтобы получить конкретную закладку, которую мы хотим скопировать:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Шаг 3. Создание целевого документа

Мы создаем новый документ, который будет служить целевым документом для копирования содержимого закладки:

```csharp
Document dstDoc = new Document();
```

## Шаг 4. Указание места копирования

Указываем место, куда хотим добавить скопированный текст. В нашем примере мы добавляем текст в конец тела последнего раздела целевого документа:

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

	// Допустим, мы добавимся в конец тела последнего раздела.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Если вы импортируете несколько раз без единого контекста, это приведет к созданию множества стилей.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию «Копировать текст с закладками» из Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы скопировать содержимое закладки из исходного документа в другой документ.

### Часто задаваемые вопросы по копированию текста с закладкой в документ Word

#### Вопрос: Каковы требования для использования функции «Копировать текст с закладками» в Aspose.Words for .NET?

О: Чтобы использовать функцию «Копировать текст с закладками» в Aspose.Words for .NET, вам необходимо иметь базовые знания языка C#. Вам также потребуется среда разработки .NET с установленной библиотекой Aspose.Words.

#### Вопрос: Как загрузить исходный документ в Aspose.Words для .NET?

 О: Чтобы загрузить исходный документ в Aspose.Words for .NET, вы можете использовать`Document` class, указав путь к файлу документа. Вот пример кода:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### Вопрос: Как получить содержимое определенной закладки в исходном документе с помощью Aspose.Words for .NET?

 О: Чтобы получить содержимое определенной закладки в исходном документе с помощью Aspose.Words for .NET, вы можете получить доступ к`Bookmarks` свойство диапазона исходного документа и используйте имя закладки для получения конкретной закладки. Вот пример кода:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### Вопрос: Как указать расположение текстовой копии закладки в целевом документе с помощью Aspose.Words for .NET?

О: Чтобы указать, где вы хотите добавить скопированный текст закладки в целевой документ, используя Aspose.Words for .NET, вы можете перейти к телу последнего раздела целевого документа. Вы можете использовать`LastSection` свойство для доступа к последнему разделу и`Body` свойство для доступа к телу этого раздела. Вот пример кода:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### Вопрос: Как импортировать и скопировать текст закладки из исходного документа в целевой документ с помощью Aspose.Words для .NET?

 О: Чтобы импортировать и скопировать текст закладки из исходного документа в целевой документ с помощью Aspose.Words for .NET, вы можете использовать команду`NodeImporter` класс, определяющий исходный документ, целевой документ и режим форматирования, который необходимо сохранить. Затем вы можете использовать`AppendBookmarkedText` метод для добавления текста закладки в целевой документ. Вот пример кода:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### Вопрос: Как сохранить целевой документ после копирования текста закладки с помощью Aspose.Words для .NET?

О: Чтобы сохранить целевой документ после копирования текста из закладки с помощью Aspose.Words for .NET, вы можете использовать команду`Save` метод`Document` объект, указывающий путь к файлу назначения. Вот пример кода:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```
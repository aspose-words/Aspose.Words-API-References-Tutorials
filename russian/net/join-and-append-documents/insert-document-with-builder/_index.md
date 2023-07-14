---
title: Вставить документ с помощью Builder
linktitle: Вставить документ с помощью Builder
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить документ в конец другого документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/insert-document-with-builder/
---

 В этом руководстве объясняется, как использовать Aspose.Words для .NET для вставки документа в другой документ с помощью`DocumentBuilder` сорт. Предоставленный исходный код демонстрирует, как вставить документ в конец другого документа с сохранением исходного форматирования.

## Шаг 1: Настройте проект

Убедитесь, что у вас есть следующие предварительные условия:

- Установлена библиотека Aspose.Words for .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов NuGet для его установки.
- Путь к каталогу документов, в котором находятся исходный и конечный документы.

## Шаг 2. Откройте исходный и конечный документы

 Откройте исходный и конечный документы с помощью`Document` конструктор класса. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к вашему каталогу документов.

```csharp
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3: Инициализируйте DocumentBuilder

 Создайте новый экземпляр`DocumentBuilder` class и передать целевой документ в качестве параметра.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Шаг 4: Разместите DocumentBuilder

 Переместите`DocumentBuilder` в конец документа с помощью`MoveToDocumentEnd` метод. Вставьте разрыв страницы, чтобы отделить существующее содержимое от вставленного документа.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Шаг 5: Вставьте исходный документ

 Использовать`InsertDocument` метод`DocumentBuilder` класс, чтобы вставить исходный документ в целевой документ. Установите режим формата импорта на`ImportFormatMode.KeepSourceFormatting` чтобы сохранить исходное форматирование.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 6: Сохраните измененный документ

 Наконец, сохраните измененный целевой документ, используя`Save` метод`Document` объект.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

На этом реализация вставки документа в другой документ с помощью Aspose.Words for .NET завершена.

### Пример исходного кода для вставки документа с помощью Builder с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```
---
title: Вставить документ с помощью Builder
linktitle: Вставить документ с помощью Builder
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить документ в конец другого документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/insert-document-with-builder/
---

 В этом руководстве объясняется, как использовать Aspose.Words для .NET для вставки документа в другой документ с помощью`DocumentBuilder` сорт. Предоставленный исходный код демонстрирует, как вставить документ в конец другого документа, сохраняя исходное форматирование.

## Шаг 1. Настройте проект

Убедитесь, что у вас есть следующие предварительные условия:

-  Установлена библиотека Aspose.Words для .NET. Вы можете скачать его с[Aspose.Releases]https://releases.aspose.com/words/net/ или используйте менеджер пакетов NuGet для его установки.
- Путь к каталогу документов, в котором расположены исходные и целевые документы.

## Шаг 2. Откройте исходный и целевой документы.

 Откройте исходный и целевой документы с помощью`Document` конструктор класса. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3. Инициализируйте DocumentBuilder

 Создайте новый экземпляр`DocumentBuilder` class и передайте целевой документ в качестве параметра.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Шаг 4. Разместите DocumentBuilder

Переместите`DocumentBuilder` до конца документа с помощью`MoveToDocumentEnd` метод. Вставьте разрыв страницы, чтобы отделить существующее содержимое от вставленного документа.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Шаг 5. Вставьте исходный документ.

 Использовать`InsertDocument` метод`DocumentBuilder` класс для вставки исходного документа в целевой документ. Установите режим формата импорта на`ImportFormatMode.KeepSourceFormatting` чтобы сохранить исходное форматирование.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 6. Сохраните измененный документ.

Наконец, сохраните измененный целевой документ, используя команду`Save` метод`Document` объект.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

На этом реализация вставки документа в другой документ с помощью Aspose.Words for .NET завершена.

### Пример исходного кода для вставки документа с помощью Builder с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```
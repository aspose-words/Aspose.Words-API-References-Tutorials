---
title: Сохранить исходное форматирование
linktitle: Сохранить исходное форматирование
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить исходный документ к целевому документу, сохранив исходное форматирование с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/keep-source-formatting/
---

В этом руководстве показано, как добавить исходный документ к целевому документу, сохранив при этом исходное форматирование исходного документа с помощью Aspose.Words для .NET.

## Шаг 1: Настройте проект

Убедитесь, что у вас есть следующие предварительные условия:

- Установлена библиотека Aspose.Words for .NET. Вы можете скачать его с[Aspose.Releases]https://releases.aspose.com/words/net/ или используйте диспетчер пакетов NuGet для его установки.
- Путь к каталогу документов, в котором будут сохранены исходный и конечный документы.

## Шаг 2. Создайте целевой и исходный документы

 Создание экземпляров`Document` для целевых и исходных документов.

```csharp
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## Шаг 3. Добавьте исходный документ к целевому документу.

 Использовать`AppendDocument`метод целевого документа для добавления исходного документа. Проходить`ImportFormatMode.KeepSourceFormatting` в качестве режима формата импорта, чтобы сохранить исходное форматирование исходного документа.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 4: Сохраните измененный документ

 Сохраните измененный документ с помощью`Save` метод`Document` объект.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

На этом завершается реализация добавления исходного документа к целевому документу с сохранением исходного форматирования с использованием Aspose.Words для .NET.

### Пример исходного кода для сохранения исходного форматирования с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Добавьте исходный документ к целевому документу.
	// Передайте режим форматирования, чтобы сохранить исходное форматирование исходного документа при его импорте.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```
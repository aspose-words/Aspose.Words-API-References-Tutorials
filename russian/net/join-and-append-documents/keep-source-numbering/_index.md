---
title: Сохраняйте нумерацию источников
linktitle: Сохраняйте нумерацию источников
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как добавить документ, сохранив исходное форматирование нумерации в Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/keep-source-numbering/
---

В этом руководстве объясняется, как добавить исходный документ к целевому документу, сохранив исходное форматирование нумерации пронумерованных абзацев с помощью Aspose.Words для .NET.

## Шаг 1: Настройте проект

Убедитесь, что у вас есть следующие предпосылки:

- Установлена библиотека Aspose.Words for .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов NuGet для его установки.
- Путь к каталогу документов, в котором будут сохранены исходный и конечный документы.

## Шаг 2. Создайте целевой и исходный документы

 Создание экземпляров`Document` для целевых и исходных документов.

```csharp
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3. Сохраняйте нумерацию источников при импорте

 Чтобы сохранить формат нумерации нумерованных абзацев из исходного документа, создайте экземпляр`ImportFormatOptions` и установить`KeepSourceNumbering` к`true` Использовать`NodeImporter` импортировать узлы из исходного документа в целевой документ, указав`ImportFormatMode.KeepSourceFormatting` и`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Шаг 4. Импортируйте и добавьте абзацы

 Переберите абзацы в исходном документе и импортируйте каждый абзац в целевой документ, используя`importer`. Добавьте импортированные узлы к телу целевого документа.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Шаг 5: Сохраните измененный документ

Сохраните измененный документ с помощью`Save` метод`Document` объект.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

На этом завершается реализация добавления исходного документа к целевому документу с сохранением исходного форматирования нумерации с использованием Aspose.Words для .NET.

### Пример исходного кода для сохранения нумерации источников с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Сохраняйте форматирование исходного списка при импорте пронумерованных абзацев.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```
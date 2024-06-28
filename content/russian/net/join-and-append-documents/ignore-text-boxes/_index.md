---
title: Игнорировать текстовые поля
linktitle: Игнорировать текстовые поля
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить документ, игнорируя форматирование текстового поля, с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/ignore-text-boxes/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для добавления документа с сохранением форматирования текстовых полей. Предоставленный исходный код демонстрирует, как настроить параметры формата импорта для включения текстовых полей в процессе добавления.

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

## Шаг 3. Настройте параметры формата импорта

 Создайте экземпляр`ImportFormatOptions` класс и установите`IgnoreTextBoxes`собственность`false`. Это гарантирует, что текстовые поля будут включены в процесс добавления с сохранением их форматирования.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## Шаг 4. Добавьте содержимое текстового поля

 Создать`NodeImporter`объект и используйте его для импорта узлов текстового поля из исходного документа в целевой документ. Перейдите по каждому абзацу исходного документа и импортируйте его в целевой документ.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Шаг 5. Сохраните целевой документ.

Наконец, сохраните измененный целевой документ, используя команду`Save` метод`Document` Объект Object.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

На этом реализация добавления документа с сохранением форматирования текстового поля завершена с использованием Aspose.Words для .NET.

### Пример исходного кода для игнорирования текстовых полей с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Сохраняйте форматирование исходных текстовых полей при импорте.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```
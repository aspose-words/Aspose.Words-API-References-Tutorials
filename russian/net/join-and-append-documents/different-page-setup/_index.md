---
title: Различные настройки страницы
linktitle: Различные настройки страницы
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как добавить документ с различными настройками страницы с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/different-page-setup/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для добавления документа с другими настройками страницы к другому документу. Предоставленный исходный код демонстрирует, как настроить различные параметры страницы для исходного и целевого документов и обеспечить правильное продолжение и нумерацию.

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

## Шаг 3. Настройте параметры страницы для исходного документа

 Настройте параметры страницы исходного документа, чтобы обеспечить правильное продолжение и нумерацию. В этом примере мы устанавливаем начало раздела на`SectionStart.Continuous` и перезапустите нумерацию страниц. Мы также следим за тем, чтобы ширина, высота и ориентация страницы соответствовали последнему разделу целевого документа.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Шаг 4. Измените форматирование абзаца

Чтобы сохранить правильное форматирование, просмотрите все абзацы в исходном документе и установите`KeepWithNext` собственность на`true`. Это гарантирует, что абзацы останутся вместе во время процесса добавления.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Шаг 5. Добавьте исходный документ к целевому документу.

 Использовать`AppendDocument` метод целевого документа для добавления измененного исходного документа к целевому документу с сохранением исходного форматирования.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 6: Сохраните целевой документ

 Наконец, сохраните измененный целевой документ, используя`Save` метод`Document` объект.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

На этом завершается реализация добавления документа с различными настройками настройки страницы с помощью Aspose.Words для .NET.

### Пример исходного кода для настройки другой страницы с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Установите исходный документ, чтобы он продолжался сразу после окончания целевого документа.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Перезапустите нумерацию страниц в начале исходного документа.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// Чтобы этого не произошло, если исходный документ имеет другие параметры настройки страницы, убедитесь, что
	// настройки идентичны между последним разделом целевого документа.
	//Если в исходном документе есть дополнительные непрерывные разделы,
	// это нужно будет повторить для этих разделов.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Повторите все разделы в исходном документе.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```
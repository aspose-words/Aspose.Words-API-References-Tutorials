---
title: Различные настройки страницы
linktitle: Различные настройки страницы
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить документ с различными настройками страницы с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/different-page-setup/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для добавления документа с другими настройками страницы в другой документ. Предоставленный исходный код демонстрирует, как настроить различные параметры страницы для исходных и целевых документов, а также обеспечить правильное продолжение и нумерацию.

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

## Шаг 3. Настройте параметры страницы для исходного документа.

 Настройте параметры страницы исходного документа, чтобы обеспечить правильное продолжение и нумерацию. В этом примере мы устанавливаем начало раздела на`SectionStart.Continuous`и возобновите нумерацию страниц. Мы также следим за тем, чтобы ширина, высота и ориентация страницы соответствовали последнему разделу целевого документа.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Шаг 4. Измените форматирование абзаца

 Чтобы сохранить правильное форматирование, просмотрите все абзацы исходного документа и установите`KeepWithNext`собственность`true`. Это гарантирует, что абзацы останутся вместе во время процесса добавления.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Шаг 5. Добавьте исходный документ в целевой документ.

 Использовать`AppendDocument` метод целевого документа для добавления измененного исходного документа в целевой документ, сохраняя исходное форматирование.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 6. Сохраните целевой документ

Наконец, сохраните измененный целевой документ, используя команду`Save` метод`Document` объект.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

На этом реализация добавления документа с различными настройками страницы с использованием Aspose.Words для .NET завершена.

### Пример исходного кода для настройки различных страниц с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Настройте исходный документ так, чтобы он продолжался сразу после окончания целевого документа.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Перезапустите нумерацию страниц с начала исходного документа.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	//Чтобы этого не произошло, если исходный документ имеет другие параметры настройки страницы, убедитесь, что
	// настройки в последнем разделе целевого документа идентичны.
	// Если в исходном документе есть дополнительные непрерывные разделы,
	// это необходимо будет повторить для этих разделов.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Перебрать все разделы исходного документа.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```
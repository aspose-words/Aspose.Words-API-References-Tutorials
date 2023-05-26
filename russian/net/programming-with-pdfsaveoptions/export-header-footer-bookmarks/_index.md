---
title: Экспорт закладок верхнего колонтитула
linktitle: Экспорт закладок верхнего колонтитула
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по экспорту закладок верхнего и нижнего колонтитула с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

В этой статье представлено пошаговое руководство по использованию функции экспорта закладок верхнего и нижнего колонтитула с Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как экспортировать закладки из верхних и нижних колонтитулов документа и создавать PDF-файл с соответствующими закладками.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на веб-сайте Aspose.

## Шаг 1: Определите каталог документов

 Для начала вам нужно указать путь к каталогу, в котором находятся ваши документы. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите документ

Далее нам нужно загрузить документ, который мы хотим обработать. В этом примере мы предполагаем, что документ называется «Закладки в верхних и нижних колонтитулах.docx» и находится в указанном каталоге документов.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Шаг 3. Настройте параметры сохранения в формате PDF.

 Чтобы экспортировать закладки верхнего и нижнего колонтитула, нам нужно настроить`PdfSaveOptions` объект. В этом примере мы устанавливаем уровень структуры закладки по умолчанию равным 1, а режим экспорта закладок верхнего и нижнего колонтитула — «Первый».

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Шаг 4. Сохраните документ в формате PDF с закладками верхнего и нижнего колонтитула.

Наконец, мы можем сохранить документ в формате PDF, используя параметры сохранения, настроенные ранее.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Вот и все ! Вы успешно экспортировали закладки верхнего и нижнего колонтитула из документа и создали PDF-файл с соответствующими закладками, используя Aspose.Words для .NET.

### Пример исходного кода для экспорта закладок верхнего и нижнего колонтитула с помощью Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

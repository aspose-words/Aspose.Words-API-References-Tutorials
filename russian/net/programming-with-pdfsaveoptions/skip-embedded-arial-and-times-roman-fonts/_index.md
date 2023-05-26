---
title: Пропустить встроенные шрифты Arial и Times Roman
linktitle: Пропустить встроенные шрифты Arial и Times Roman
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по созданию PDF без встраивания шрифтов Arial и Times Roman с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

В этой статье представлено пошаговое руководство по использованию функции пропуска встроенных шрифтов Arial и Times Roman до размера метафайла с помощью Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как настроить параметр режима встраивания шрифта в документ и создать PDF-файл без встраивания шрифтов Arial и Times Roman.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на веб-сайте Aspose.

## Шаг 1: Определите каталог документов

 Для начала вам нужно указать путь к каталогу, в котором находятся ваши документы. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите документ

Далее нам нужно загрузить документ, который мы хотим обработать. В этом примере предполагается, что документ называется «Rendering.docx» и находится в указанном каталоге документов.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Шаг 3. Настройте параметры сохранения в формате PDF с встраиванием шрифта

 Чтобы пропустить встраивание шрифтов Arial и Times Roman в сгенерированный PDF-файл, нам нужно настроить`PdfSaveOptions` объект и установить`FontEmbeddingMode` собственность на`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Шаг 4. Сохраните документ в формате PDF без встроенных шрифтов.

Наконец, мы можем сохранить документ в формате PDF, используя параметры сохранения, настроенные ранее.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Вот и все ! Вы успешно создали PDF-файл без встраивания шрифтов Arial и Times Roman с помощью Aspose.Words для .NET.

### Пример исходного кода для пропуска встроенных шрифтов Arial и Times Roman при размере метафайла с помощью Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

---
title: Встроенные подмножества шрифтов
linktitle: Встроенные подмножества шрифтов
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по внедрению подмножеств шрифтов в PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

В этой статье представлено пошаговое руководство по использованию функции встраивания подмножества шрифтов в Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как встраивать подмножества шрифтов в документ и создавать PDF-файл, содержащий только глифы, используемые в документе.

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

## Шаг 3. Настройте параметры сохранения в формате PDF.

 Чтобы создать PDF-файл, содержащий только подмножества шрифтов, используемых в документе, нам нужно настроить`PdfSaveOptions` объект с`EmbedFullFonts` свойство установлено на`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Шаг 4. Сохраните документ в формате PDF с подмножествами шрифтов.

 Наконец, мы можем сохранить документ в формате PDF, используя подмножества шрифтов. Укажите имя выходного файла и`saveOptions` объект, который мы настроили на предыдущем шаге.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Вот и все ! Вы успешно внедрили подмножества шрифтов в документ и создали PDF-файл, содержащий только глифы, используемые в документе, с помощью Aspose.Words для .NET.

### Пример исходного кода для внедрения подмножеств шрифтов с помощью Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Выходной PDF-файл будет содержать подмножества шрифтов в документе.
	// В шрифты PDF включаются только глифы, используемые в документе.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

---
title: Установить параметры контура
linktitle: Установить параметры контура
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по настройке параметров структуры в документе PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/set-outline-options/
---

В этой статье представлено пошаговое руководство о том, как использовать функцию установки параметров структуры для размера метафайла с Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как установить параметры структуры в документе и создать PDF-файл с соответствующими параметрами структуры.

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

## Шаг 3. Настройте параметры сохранения в формате PDF с параметрами плана

 Чтобы установить параметры контура в сгенерированном PDF-файле, нам нужно настроить`PdfSaveOptions` объект. Мы можем установить количество уровней структуры заголовка (`HeadingsOutlineLevels`) и количество расширенных уровней структуры (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Шаг 4. Сохраните документ в формате PDF с параметрами структуры

Наконец, мы можем сохранить документ в формате PDF, используя параметры сохранения, настроенные ранее.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

Вот и все ! Вы успешно установили параметры структуры в документе и создали PDF-файл с соответствующими параметрами структуры, используя Aspose.Words для .NET.

### Пример исходного кода для установки параметров плана на размер метафайла с помощью Aspose.Words для .NET


```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

---
title: Интерполировать изображения
linktitle: Интерполировать изображения
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по включению интерполяции изображений с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/interpolate-images/
---

В этой статье представлено пошаговое руководство по использованию функции интерполяции изображений с Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как включить интерполяцию изображения при преобразовании в PDF.

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

## Шаг 3. Настройте параметры для сохранения в формате PDF с интерполяцией кадров

 Чтобы включить интерполяцию изображений при конвертации в PDF, нам нужно настроить`PdfSaveOptions` объект, установив`InterpolateImages` собственность на`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { InterpolateImages = true };
```

## Шаг 4. Сохраните документ в формате PDF с интерполяцией кадров.

Наконец, мы можем сохранить документ в формате PDF, используя параметры сохранения, настроенные ранее.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.InterpolateImages.pdf", saveOptions);
```

Вот и все ! Вы успешно включили интерполяцию изображений при преобразовании документа в PDF с помощью Aspose.Words для .NET.

### Пример исходного кода для интерполяции изображений с помощью Aspose.Words для .NET


```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { InterpolateImages = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.InterpolateImages.pdf", saveOptions);

```

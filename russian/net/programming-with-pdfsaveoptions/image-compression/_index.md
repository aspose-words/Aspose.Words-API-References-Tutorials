---
title: Сжатие изображения
linktitle: Сжатие изображения
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по сжатию изображений с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/image-compression/
---

В этой статье представлено пошаговое руководство по использованию функции сжатия изображений в Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как сжимать изображения в документе и создавать PDF-файл с правильным сжатием изображений.

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

## Шаг 3. Настройте параметры сохранения в формате PDF со сжатием изображений.

 Для сжатия изображений при конвертации в PDF нам нужно настроить`PdfSaveOptions` объект. При необходимости мы можем установить тип сжатия изображения, качество JPEG и другие параметры соответствия PDF.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Шаг 4. Сохраните документ в формате PDF со сжатием изображения.

Наконец, мы можем сохранить документ в формате PDF, используя параметры сохранения, настроенные ранее.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Шаг 5. Настройте параметры для сохранения в формате PDF/A-2u со сжатием изображения.

Если вы хотите создать PDF-файл, совместимый с PDF/A-2u, со сжатием изображения, вы можете настроить дополнительные параметры сохранения.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Используйте сжатие JPEG с качеством 50%, чтобы уменьшить размер файла.
};
```

## Шаг 6. Сохраните документ в формате PDF/A-2u со сжатием изображения.

Сохраните документ в формате PDF/A-2u, используя настроенные ранее дополнительные параметры сохранения.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



Вот и все ! Вы успешно сжали изображения в документе и создали PDF-файл с надлежащим сжатием изображений с помощью Aspose.Words для .NET.

### Пример исходного кода для сжатия изображений с помощью Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Используйте сжатие JPEG с качеством 50%, чтобы уменьшить размер файла.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

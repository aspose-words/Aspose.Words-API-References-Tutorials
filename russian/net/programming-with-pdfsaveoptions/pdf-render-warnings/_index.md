---
title: Предупреждения об отображении PDF
linktitle: Предупреждения об отображении PDF
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по работе с предупреждениями об отображении PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

В этой статье представлено пошаговое руководство по использованию функции предупреждений об отображении PDF в Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как бороться с предупреждениями об отображении при преобразовании в PDF.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на веб-сайте Aspose.

## Шаг 1: Определите каталог документов

 Для начала вам нужно указать путь к каталогу, в котором находятся ваши документы. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите документ

Далее нам нужно загрузить документ, который мы хотим обработать. В этом примере мы предполагаем, что документ называется «WMF с изображением.docx» и находится в указанном каталоге документов.

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## Шаг 3. Настройте параметры сохранения в формате PDF с предупреждениями об отображении

Чтобы обрабатывать предупреждения рендеринга при преобразовании в PDF, нам нужно настроить`MetafileRenderingOptions` объект, чтобы указать, как метафайлы отображаются. Мы также используем`HandleDocumentWarnings` возможность обработки предупреждений, генерируемых при сохранении документа.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     EmulateRasterOperations = false,
     RenderingMode = MetafileRenderingMode.VectorWithFallback
};

PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
```

## Шаг 4. Сохраните документ в формате PDF с предупреждениями об отображении

Наконец, мы можем сохранить документ в формате PDF, используя параметры сохранения, настроенные ранее.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
```

## Шаг 5. Обработка предупреждений рендеринга

Предупреждения об отображении, созданные при сохранении документа, можно получить с помощью пользовательского обработчика предупреждений. В этом примере мы просто печатаем описание каждого предупреждения.

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

Вот и все ! Вы успешно обработали предупреждения рендеринга при преобразовании документа

  в PDF с помощью Aspose.Words для .NET.

### Пример исходного кода для предупреждений об отображении PDF с помощью Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with image.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		EmulateRasterOperations = false, RenderingMode = MetafileRenderingMode.VectorWithFallback
	};

	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	// Если Aspose.Words не может правильно отобразить некоторые записи метафайла
	// в векторную графику, то Aspose.Words преобразует этот метафайл в растровое изображение.
	HandleDocumentWarnings callback = new HandleDocumentWarnings();
	doc.WarningCallback = callback;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);

	// Пока файл сохраняется успешно, здесь собираются предупреждения рендеринга, возникшие во время сохранения.
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```

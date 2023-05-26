---
title: Масштабировать шрифты Wmf по размеру метафайла
linktitle: Масштабировать шрифты Wmf по размеру метафайла
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по настройке размера шрифта WMF при преобразовании в PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

В этой статье представлено пошаговое руководство по использованию функции масштабирования шрифта WMF по размеру метафайла с Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как включить или отключить масштабирование шрифта WMF при преобразовании в PDF.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на веб-сайте Aspose.

## Шаг 1: Определите каталог документов

 Для начала вам нужно указать путь к каталогу, в котором находятся ваши документы. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите документ

Далее нам нужно загрузить документ, который мы хотим обработать. В этом примере предполагается, что документ называется «WMF with text.docx» и находится в указанном каталоге документов.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Шаг 3. Настройте параметры рендеринга метафайлов.

 Чтобы включить или отключить масштабирование шрифта WMF до размера метафайла, нам нужно настроить`MetafileRenderingOptions` объект. В этом примере мы отключаем масштабирование шрифта, установив`ScaleWmfFontsToMetafileSize` собственность на`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Шаг 4. Настройте параметры сохранения в формате PDF с параметрами рендеринга метафайлов.

Наконец, мы можем настроить параметры сохранения в PDF, используя ранее настроенные параметры рендеринга метафайлов.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Шаг 5. Сохраните документ в формате PDF с параметрами рендеринга метафайла

Сохраните документ в формате PDF, используя ранее настроенные параметры сохранения.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

Вот и все ! Вы успешно включили или отключили масштабирование шрифта WMF до размера метафайла при преобразовании

PDF-документ с использованием Aspose.Words для .NET.

### Пример исходного кода для масштабирования шрифтов WMF до размера метафайла с помощью Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// Если Aspose.Words не может правильно преобразовать некоторые записи метафайла в векторную графику
	// затем Aspose.Words преобразует этот метафайл в растровое изображение.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

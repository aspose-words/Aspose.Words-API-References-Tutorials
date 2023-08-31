---
title: Предупреждения об отображении PDF
linktitle: Предупреждения об отображении PDF
second_title: API обработки документов Aspose.Words
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

	//Если Aspose.Words не может правильно отобразить некоторые записи метафайла
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

### Часто задаваемые вопросы

#### В: Какова функциональность предупреждений об отображении PDF с помощью Aspose.Words для .NET?
Функция предупреждений об отображении PDF в Aspose.Words для .NET помогает управлять предупреждениями, генерируемыми при преобразовании документа в PDF. Он предоставляет способ обнаружения и устранения предупреждений об отображении для обеспечения качества и целостности преобразованного документа.

#### В: Как я могу использовать эту функцию с Aspose.Words для .NET?
Чтобы использовать эту функцию с Aspose.Words для .NET, выполните следующие действия:

Задайте каталог документов, указав путь к каталогу, в котором находятся ваши документы.

 Загрузите документ для обработки с помощью`Document` метод и указать путь к файлу.

 Настройте параметры сохранения в PDF, создав экземпляр`PdfSaveOptions` сорт. Использовать`MetafileRenderingOptions` класс, чтобы указать, как метафайлы отображаются, и установить`MetafileRenderingOptions.RenderingMode` к`MetafileRenderingMode.VectorWithFallback`.

 Использовать`HandleDocumentWarnings` класс для обработки предупреждений о рендеринге. Набор`doc.WarningCallback` к экземпляру этого класса.

 Использовать`Save` способ сохранения документа в формате PDF с указанием параметров сохранения.

Затем вы можете обрабатывать предупреждения рендеринга с помощью`HandleDocumentWarnings` сорт. Например, вы можете отобразить описание каждого предупреждения, используя цикл.

#### В: Как узнать, были ли какие-либо предупреждения при рендеринге при преобразовании документа в PDF?
 Вы можете использовать`HandleDocumentWarnings` класс для получения предупреждений об отрисовке, сгенерированных при сохранении документа. Этот класс содержит`mWarnings` список, в котором хранится информация о предупреждениях. Вы можете просмотреть этот список и получить доступ к свойствам каждого предупреждения, таким как описание, чтобы предпринять соответствующие действия.

#### В: Какие предупреждения рендеринга могут появляться при преобразовании в PDF?
Предупреждения об отображении при преобразовании в PDF могут включать предупреждения, связанные с макетом, отсутствующими шрифтами, неподдерживаемыми изображениями, проблемами совместимости и т. д. Конкретные предупреждения будут зависеть от содержимого исходного документа и используемых параметров преобразования.

#### В: Можно ли обрабатывать предупреждения рендеринга по-своему?
 Да, вы можете настроить обработку предупреждений рендеринга, настроив`HandleDocumentWarnings`сорт. Вы можете добавить дополнительные функции для управления предупреждениями, характерными для вашего приложения, такими как регистрация предупреждений, создание отчетов, отправка предупреждений и т. д.
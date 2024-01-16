---
title: Предупреждения при рендеринге PDF
linktitle: Предупреждения при рендеринге PDF
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по устранению предупреждений при рендеринге PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

В этой статье представлено пошаговое руководство по использованию функции предупреждений при рендеринге PDF в Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как бороться с предупреждениями при рендеринге при преобразовании в PDF.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на сайте Aspose.

## Шаг 1. Определите каталог документов.

 Для начала вам необходимо определить путь к каталогу, в котором находятся ваши документы. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ

Далее нам нужно загрузить документ, который мы хотим обработать. В этом примере мы предполагаем, что документ называется «WMF with image.docx» и находится в указанном каталоге документов.

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## Шаг 3. Настройте параметры сохранения в формате PDF с предупреждениями об отрисовке.

 Чтобы обрабатывать предупреждения о рендеринге при преобразовании в PDF, нам необходимо настроить`MetafileRenderingOptions` объект, чтобы указать, как отображаются метафайлы. Мы также используем`HandleDocumentWarnings` опция для обработки предупреждений, возникающих при сохранении документа.

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

## Шаг 4. Сохраните документ в формате PDF с предупреждениями об отображении.

Наконец, мы можем сохранить документ в формате PDF, используя ранее настроенные параметры сохранения.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
```

## Шаг 5. Обработка предупреждений рендеринга

Предупреждения рендеринга, сгенерированные при сохранении документа, можно получить с помощью специального обработчика предупреждений. В этом примере мы просто печатаем описание каждого предупреждения.

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

Вот и все ! Вы успешно обработали предупреждения об отображении при преобразовании документа.

  в PDF с помощью Aspose.Words для .NET.

### Пример исходного кода для предупреждений о рендеринге PDF с помощью Aspose.Words для .NET

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

	// При успешном сохранении файла здесь собираются предупреждения рендеринга, возникшие во время сохранения.
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```

### Часто задаваемые вопросы

#### Вопрос: Какова функциональность предупреждений о рендеринге PDF с помощью Aspose.Words для .NET?
Функция предупреждений о рендеринге PDF в Aspose.Words для .NET помогает управлять предупреждениями, генерируемыми при преобразовании документа в PDF. Он обеспечивает возможность обнаружения и устранения предупреждений рендеринга, чтобы гарантировать качество и целостность преобразованного документа.

#### Вопрос: Как я могу использовать эту функцию с Aspose.Words для .NET?
Чтобы использовать эту функцию с Aspose.Words для .NET, выполните следующие действия:

Задайте каталог документов, указав путь к каталогу, в котором находятся ваши документы.

 Загрузите документ для обработки с помощью`Document` метод и указав путь к файлу.

 Настройте параметры сохранения в PDF, создав экземпляр`PdfSaveOptions` сорт. Использовать`MetafileRenderingOptions` класс, чтобы указать, как отображаются метафайлы, и установить`MetafileRenderingOptions.RenderingMode` к`MetafileRenderingMode.VectorWithFallback`.

 Использовать`HandleDocumentWarnings` класс для обработки предупреждений отрисовки. Набор`doc.WarningCallback` к экземпляру этого класса.

 Использовать`Save` метод сохранения документа в формате PDF с указанием параметров сохранения.

Затем вы можете обрабатывать предупреждения рендеринга, используя`HandleDocumentWarnings` сорт. Например, вы можете отобразить описание каждого предупреждения с помощью цикла.

#### Вопрос: Как узнать, были ли какие-либо предупреждения о рендеринге при преобразовании документа в PDF?
 Вы можете использовать`HandleDocumentWarnings` класс для получения предупреждений рендеринга, сгенерированных при сохранении документа. Этот класс содержит`mWarnings` список, в котором хранится информация о предупреждениях. Вы можете просмотреть этот список и получить доступ к свойствам каждого предупреждения, например к описанию, чтобы предпринять соответствующие действия.

#### Вопрос: Какие предупреждения о рендеринге могут появиться при конвертации в PDF?
Предупреждения отображения при преобразовании в PDF могут включать предупреждения, связанные с макетом, отсутствующими шрифтами, неподдерживаемыми изображениями, проблемами совместимости и т. д. Конкретные предупреждения будут зависеть от содержимого исходного документа и используемых параметров преобразования.

#### Вопрос: Можно ли обрабатывать предупреждения при рендеринге по-своему?
 Да, вы можете настроить обработку предупреждений о рендеринге, настроив`HandleDocumentWarnings`сорт. Вы можете добавить дополнительные функции для управления предупреждениями, специфичными для вашего приложения, например регистрацию предупреждений, создание отчетов, отправку предупреждений и многое другое.
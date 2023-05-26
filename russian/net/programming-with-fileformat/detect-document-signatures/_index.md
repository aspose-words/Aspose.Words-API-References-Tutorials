---
title: Обнаружение подписей документов
linktitle: Обнаружение подписей документов
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по обнаружению цифровых подписей в документе с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-fileformat/detect-document-signatures/
---

В этой статье представлено пошаговое руководство по использованию функции обнаружения подписи документа с Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как обнаруживать цифровые подписи в документе.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на веб-сайте Aspose.

## Шаг 1: Определите каталог документов

 Для начала вам нужно указать путь к каталогу, в котором находятся ваши документы. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Обнаружение цифровых подписей

 Далее мы используем`DetectFileFormat` метод`FileFormatUtil` класс для обнаружения информации о формате файла. В этом примере предполагается, что документ называется «Цифровая подпись.docx» и находится в указанном каталоге документов.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");
```

## Шаг 3. Проверьте цифровые подписи.

 Проверяем наличие в документе ЭЦП с помощью`HasDigitalSignature` собственность`FileFormatInfo` объект. Если цифровые подписи обнаружены, мы показываем сообщение о том, что подписи будут потеряны, если документ будет открыт/сохранен с помощью Aspose.Words.

```csharp
if (info.HasDigitalSignature)
{
	Console.WriteLine(
		$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
		"they will be lost if you open/save this document with Aspose.Words.");
}
```

Вот и все ! Вы успешно обнаружили цифровые подписи в документе с помощью Aspose.Words for .NET.

### Пример исходного кода для обнаружения подписей документов с помощью Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");

	if (info.HasDigitalSignature)
	{
		Console.WriteLine(
			$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
			"they will be lost if you open/save this document with Aspose.Words.");
	}
	
        
```

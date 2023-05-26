---
title: Предпочтительный тип управления
linktitle: Предпочтительный тип управления
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по указанию предпочтительного типа элемента управления при загрузке HTML-документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-htmlloadoptions/preferred-control-type/
---

В этой статье представлено пошаговое руководство по использованию функции предпочтительного типа элемента управления с Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как указать предпочтительный тип элемента управления при загрузке HTML-документа.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на веб-сайте Aspose.

## Шаг 1. Определите HTML-код

 Для начала вам нужно определить код HTML, который вы хотите загрузить как документ. В этом примере мы определили`html` переменная, содержащая HTML-код селектора с опциями.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## Шаг 2. Установите параметры загрузки HTML

 Далее мы создаем`HtmlLoadOptions` объект и установить`PreferredControlType` собственность на`HtmlControlType.StructuredDocumentTag`. Это говорит Aspose.Words использовать StructuredDocumentTags для представления HTML при загрузке.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Шаг 3: Загрузите и сохраните документ

 Мы используем`Document` класс для загрузки HTML-кода из потока памяти с параметрами загрузки, определенными ранее. Затем мы сохраняем документ в указанную директорию с`.docx` формат файла.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Пример исходного кода для предпочтительного типа элемента управления с Aspose.Words для .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

Вот и все ! Вы успешно указали предпочтительный тип элемента управления при загрузке HTML-документа с помощью Aspose.Words для .NET.
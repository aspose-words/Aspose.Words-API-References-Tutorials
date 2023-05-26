---
title: Побег Ури
linktitle: Побег Ури
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по экранированию Uri с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/escape-uri/
---

В этой статье представлено пошаговое руководство по использованию функции экранирования Uri с Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как вставлять гиперссылки с экранированным Uri в документ.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на веб-сайте Aspose.

## Шаг 1: Определите каталог документов

 Для начала вам нужно указать путь к каталогу, в котором находятся ваши документы. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте документ и DocumentBuilder

 Далее нам нужно создать новый`Document` объект и`DocumentBuilder` объект для построения документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Вставьте гиперссылки с экранированным кодом Uri.

 Использовать`InsertHyperlink` метод`DocumentBuilder`объект для вставки гиперссылок в документ. Uri должен быть экранирован с помощью`Uri.EscapeUriString` функция, позволяющая избежать ошибок формата.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), ложь);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), ложь);
```

## Шаг 4. Сохраните документ в формате PDF.

 Наконец, мы можем сохранить документ в формате PDF, используя`Save` метод`Document` объект. Укажите имя выходного файла.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

Вот и все ! Вы успешно вставили гиперссылки с экранированными Uri в документ с помощью Aspose.Words для .NET.

### Пример исходного кода для экранирования Uri с помощью Aspose.Words для .NET


```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", false);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", false);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

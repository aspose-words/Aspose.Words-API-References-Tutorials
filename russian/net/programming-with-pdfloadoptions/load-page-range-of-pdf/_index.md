---
title: Загрузить диапазон страниц PDF
linktitle: Загрузить диапазон страниц PDF
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по загрузке определенного диапазона страниц PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

В этом руководстве мы расскажем, как загрузить определенный диапазон страниц из документа PDF с помощью Aspose.Words для .NET. Выполните следующие действия:

## Шаг 1. Загрузка диапазона страниц PDF

Используйте следующий код для загрузки определенного диапазона страниц из документа PDF:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 В этом примере мы загружаем первую страницу документа PDF. Вы можете изменить значения`PageIndex` и`PageCount` к нужному диапазону страниц.

## Шаг 2: Сохранение документа

 Наконец, вы можете сохранить документ, содержащий определенный диапазон страниц, используя`Save` метод:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Обязательно укажите правильный путь для сохранения отредактированного документа.

Вот и все ! Теперь вы загрузили определенный диапазон страниц из документа PDF с помощью Aspose.Words для .NET.

### Пример исходного кода для загрузки диапазона страниц из Pdf с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Не забудьте указать правильный путь к каталогу ваших PDF-документов.




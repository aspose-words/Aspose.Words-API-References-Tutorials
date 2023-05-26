---
title: Преобразование в PDF 17
linktitle: Преобразование в PDF 17
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как конвертировать документы в формат PDF 1.7 с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

В этом руководстве мы покажем вам, как конвертировать в PDF 1.7 с помощью Aspose.Words для .NET. Преобразование в PDF 1.7 позволяет создавать PDF-файлы, соответствующие стандарту PDF 1.7. Выполните следующие действия:

## Шаг 1: Загрузка документа

Начните с загрузки документа, который вы хотите преобразовать в PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Обязательно укажите правильный путь к документу.

## Шаг 2. Установите параметры преобразования PDF

Создайте экземпляр класса PdfSaveOptions и укажите версию стандарта PDF, которую вы хотите использовать:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

Этот параметр гарантирует, что сгенерированный PDF-файл соответствует стандарту PDF 1.7.

## Шаг 3. Конвертируйте документ в PDF

 Использовать`Save` метод преобразования документа в PDF с указанием параметров преобразования:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Обязательно укажите правильный путь для сохранения конвертированного PDF-файла.

### Пример исходного кода для преобразования в Pdf 17 с использованием Aspose.Words для .NET

Вот полный исходный код для преобразования в PDF 1.7 с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

Следуя этим шагам, вы сможете легко конвертировать в PDF 1.7 с помощью Aspose.Words для .NET.


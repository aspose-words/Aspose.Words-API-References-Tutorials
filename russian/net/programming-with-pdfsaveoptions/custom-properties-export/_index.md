---
title: Экспорт пользовательских свойств
linktitle: Экспорт пользовательских свойств
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как экспортировать пользовательские свойства при преобразовании документов в PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/custom-properties-export/
---

В этом руководстве мы покажем вам, как экспортировать пользовательские свойства документа с помощью Aspose.Words для .NET. Экспорт пользовательских свойств позволяет включать дополнительную информацию в сгенерированный документ PDF. Выполните следующие действия:

## Шаг 1. Создание документа и добавление пользовательских свойств

Начните с создания экземпляра класса Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Шаг 2. Добавьте настраиваемые свойства
Затем добавьте нужные пользовательские свойства. Например, чтобы добавить свойство «Компания» со значением «Aspose», используйте метод`Add` метод коллекции CustomDocumentProperties:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Вы можете добавить столько настраиваемых свойств, сколько необходимо.

## Шаг 3. Установите параметры экспорта PDF

Создайте экземпляр класса PdfSaveOptions и укажите, как экспортировать пользовательские свойства:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Этот параметр управляет экспортом пользовательских свойств при преобразовании в PDF.

## Шаг 4. Конвертируйте документ в PDF

 Использовать`Save` метод преобразования документа в PDF с указанием параметров преобразования:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Обязательно укажите правильный путь для сохранения конвертированного PDF-файла.

### Пример исходного кода для экспорта пользовательских свойств с использованием Aspose.Words для .NET

Вот полный исходный код для экспорта пользовательских свойств из документа с использованием Aspose.Words для .NET:


```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Следуя этим шагам, вы можете легко экспортировать пользовательские свойства документа при преобразовании в PDF с помощью Aspose.Words для .NET.


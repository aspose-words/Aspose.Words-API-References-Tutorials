---
title: Дополнительное позиционирование текста
linktitle: Дополнительное позиционирование текста
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как управлять размещением дополнительного текста при преобразовании документов Word в PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/additional-text-positioning/
---

В этом руководстве мы покажем вам, как использовать дополнительную функцию позиционирования текста в Aspose.Words для .NET. Эта функция позволяет контролировать размещение дополнительного текста при преобразовании документа Word в PDF. Выполните следующие действия:

## Шаг 1: Загрузка документа

Начните с загрузки документа Word, который вы хотите преобразовать в PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Обязательно укажите правильный путь к документу Word.

## Шаг 2. Установите параметры преобразования PDF

Создайте экземпляр класса PdfSaveOptions и включите дополнительное позиционирование текста:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };
```

Этот параметр управляет точным размещением дополнительного текста в PDF-файле.

## Шаг 3. Конвертируйте документ в PDF

 Использовать`Save` метод преобразования документа Word в PDF, указав параметры преобразования:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
```

Обязательно укажите правильный путь для сохранения конвертированного PDF-файла.

### Пример исходного кода для дополнительного позиционирования текста с использованием Aspose.Words для .NET

Вот полный исходный код для использования дополнительных функций позиционирования текста с Aspose.Words для .NET:


```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);

```
Следуя этим шагам, вы можете легко контролировать расположение дополнительного текста при преобразовании документа Word в PDF с помощью Aspose.Words для .NET.


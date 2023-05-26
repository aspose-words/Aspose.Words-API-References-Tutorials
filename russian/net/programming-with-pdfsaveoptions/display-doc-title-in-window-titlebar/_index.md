---
title: Отображать заголовок документа в заголовке окна
linktitle: Отображать заголовок документа в заголовке окна
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как отобразить заголовок документа в строке заголовка окна при преобразовании в PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

В этом руководстве мы покажем вам, как отобразить заголовок документа в строке заголовка окна с помощью Aspose.Words для .NET. Эта функция позволяет отображать заголовок документа в строке заголовка окна при открытии сгенерированного PDF-документа. Выполните следующие действия:

## Шаг 1: Загрузка документа

Начните с загрузки документа, который вы хотите преобразовать в PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Обязательно укажите правильный путь к документу.

## Шаг 2. Настройте параметры сохранения PDF

Создайте экземпляр класса PdfSaveOptions и включите отображение заголовка документа в строке заголовка окна:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

Этот параметр включает отображение заголовка документа в строке заголовка окна при преобразовании в PDF.

## Шаг 3. Конвертируйте документ в PDF

 Использовать`Save` метод преобразования документа в PDF с указанием параметров преобразования:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

Обязательно укажите правильный путь для сохранения конвертированного PDF-файла.

### Пример исходного кода для отображения заголовка документа в заголовке окна с использованием Aspose.Words для .NET

Вот полный исходный код для отображения заголовка документа в строке заголовка окна в документе PDF с Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
Следуя этим шагам, вы можете легко отобразить заголовок документа в строке заголовка окна при преобразовании в PDF с помощью Aspose.Words для .NET.


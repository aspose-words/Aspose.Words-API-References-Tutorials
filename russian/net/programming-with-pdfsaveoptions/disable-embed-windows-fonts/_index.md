---
title: Отключить встроенные шрифты Windows
linktitle: Отключить встроенные шрифты Windows
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как отключить встраивание шрифтов Windows при преобразовании документов в PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

В этом руководстве мы покажем вам, как отключить встраивание шрифтов Windows в документ PDF с помощью Aspose.Words для .NET. Отключив встраивание шрифтов, вы можете уменьшить размер создаваемого PDF-файла. Выполните следующие действия:

## Шаг 1: Загрузка документа

Начните с загрузки документа, который вы хотите преобразовать в PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Обязательно укажите правильный путь к документу.

## Шаг 2. Установите параметры сохранения PDF

Создайте экземпляр класса PdfSaveOptions и укажите, как встраивать шрифты:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Этот параметр позволяет отключить интеграцию шрифтов Windows в сгенерированный PDF-файл.

## Шаг 3. Конвертируйте документ в PDF

 Использовать`Save` метод преобразования документа в PDF с указанием параметров преобразования:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Обязательно укажите правильный путь для сохранения конвертированного PDF-файла.

### Пример исходного кода для отключения встроенных шрифтов Windows с использованием Aspose.Words для .NET

Вот полный исходный код для отключения встраивания шрифтов Windows в документ PDF с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Выходной PDF-файл будет сохранен без встраивания стандартных шрифтов Windows.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Следуя этим шагам, вы можете легко отключить встраивание шрифтов Windows в документ PDF с помощью Aspose.Words для .NET.


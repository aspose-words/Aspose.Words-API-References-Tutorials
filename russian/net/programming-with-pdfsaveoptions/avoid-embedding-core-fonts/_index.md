---
title: Избегайте встраивания основных шрифтов
linktitle: Избегайте встраивания основных шрифтов
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как избежать базового встраивания шрифтов при преобразовании документов Word в PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

В этом руководстве мы покажем вам, как использовать функцию «Избежать базового встраивания шрифтов» в Aspose.Words для .NET. Эта функция позволяет вам контролировать, должны ли базовые шрифты, такие как Arial, Times New Roman и т. д., быть встроены в PDF-файл при преобразовании документа Word. Выполните следующие действия:

## Шаг 1: Загрузка документа

Начните с загрузки документа Word, который вы хотите преобразовать в PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Обязательно укажите правильный путь к документу Word.

## Шаг 2. Установите параметры преобразования PDF

Создайте экземпляр класса PdfSaveOptions и включите базовое предотвращение встраивания шрифтов:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Этот параметр определяет, должны ли базовые шрифты быть встроены в PDF-файл или нет.

## Шаг 3. Конвертируйте документ в PDF

 Использовать`Save` метод преобразования документа Word в PDF, указав параметры преобразования:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Обязательно укажите правильный путь для сохранения конвертированного PDF-файла.

### Пример исходного кода для предотвращения встраивания основных шрифтов с использованием Aspose.Words для .NET

Вот полный исходный код для использования этой функции, чтобы избежать встраивания основного шрифта с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// В выходной PDF-файл не будут встроены основные шрифты, такие как Arial, Times New Roman и т. д.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Следуя этим шагам, вы можете легко контролировать, следует ли встраивать базовые шрифты в PDF-файл при преобразовании документа Word с помощью Aspose.Words для .NET.


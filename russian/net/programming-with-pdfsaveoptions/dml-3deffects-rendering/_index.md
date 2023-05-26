---
title: Рендеринг Dml 3DEffects
linktitle: Рендеринг Dml 3DEffects
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как включить рендеринг эффектов 3D DML при преобразовании в PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

В этом руководстве мы покажем вам, как включить рендеринг эффекта 3D DML при преобразовании в PDF с помощью Aspose.Words для .NET. Это сохраняет 3D-эффекты в сгенерированном PDF-документе. Выполните следующие действия:

## Шаг 1: Загрузка документа

Начните с загрузки документа, который вы хотите преобразовать в PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Обязательно укажите правильный путь к документу.

## Шаг 2. Настройте параметры сохранения PDF

Создайте экземпляр класса PdfSaveOptions и включите расширенную визуализацию 3D-эффектов DML:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

Этот параметр сохраняет 3D-эффекты в сгенерированном документе PDF.

## Шаг 3. Конвертируйте документ в PDF

 Использовать`Save` метод преобразования документа в PDF с указанием параметров сохранения:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

Обязательно укажите правильный путь для сохранения конвертированного PDF-файла.

### Пример исходного кода для рендеринга Dml 3DEffects с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

Следуя этим шагам, вы можете легко включить рендеринг эффектов 3D DML при преобразовании в PDF с помощью Aspose.Words для .NET.




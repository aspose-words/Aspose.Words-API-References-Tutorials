---
title: Рендеринг 3D DML 3DEffects в PDF-документе
linktitle: Рендеринг 3D DML 3DEffects в PDF-документе
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

## Заключение

В этом руководстве мы объяснили, как включить рендеринг эффектов 3D DML при преобразовании в PDF с помощью Aspose.Words для .NET. Следуя описанным шагам, вы можете легко сохранить 3D-эффекты в сгенерированном PDF-документе. Используйте эту функцию, чтобы сохранить важные визуальные эффекты исходного документа.


### Часто задаваемые вопросы

#### Вопрос. Что такое рендеринг эффектов 3D DML в документе PDF?
О: Рендеринг 3D-эффектов DML в документе PDF относится к способности сохранять 3D-эффекты при преобразовании документа в формат PDF. Это сохраняет визуальные эффекты и гарантирует, что сгенерированный документ PDF будет выглядеть как исходный документ.

#### Вопрос. Как включить рендеринг эффектов 3D DML при преобразовании в PDF с помощью Aspose.Words для .NET?
О: Чтобы включить рендеринг эффектов 3D DML при преобразовании в PDF с помощью Aspose.Words для .NET, выполните следующие действия:

 Создайте экземпляр`Document` класс, указывающий путь к документу Word.

 Создайте экземпляр`PdfSaveOptions` класс и установить`Dml3DEffectsRenderingMode` собственность на`Dml3DEffectsRenderingMode.Advanced` для включения расширенного рендеринга эффектов 3D DML.

 Использовать`Save` метод`Document`class, чтобы сохранить документ в формате PDF, указав параметры сохранения.

#### В: Как я могу проверить, были ли визуализированы эффекты 3D DML в сгенерированном документе PDF?
О: Чтобы проверить, были ли визуализированы эффекты 3D DML в сгенерированном документе PDF, откройте файл PDF в совместимом средстве просмотра PDF, таком как Adobe Acrobat Reader, и просмотрите документ. Вы должны увидеть 3D-эффекты, как они выглядят в исходном документе.




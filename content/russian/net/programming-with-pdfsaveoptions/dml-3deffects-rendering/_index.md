---
title: Рендеринг 3D DML 3DEffects в PDF-документе
linktitle: Рендеринг 3D DML 3DEffects в PDF-документе
second_title: API обработки документов Aspose.Words
description: Узнайте, как включить рендеринг эффектов 3D DML при преобразовании в PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

В этом уроке мы покажем вам, как включить рендеринг эффекта 3D DML при преобразовании в PDF с помощью Aspose.Words для .NET. Это сохранит 3D-эффекты в созданном PDF-документе. Выполните следующие действия:

## Шаг 1: Загрузка документа

Начните с загрузки документа, который вы хотите конвертировать в PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Обязательно укажите правильный путь к вашему документу.

## Шаг 2. Настройте параметры сохранения PDF-файла.

Создайте экземпляр класса PdfSaveOptions и включите расширенную отрисовку 3D-эффектов DML:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

Этот параметр сохраняет 3D-эффекты в созданном PDF-документе.

## Шаг 3. Конвертируйте документ в PDF

 Использовать`Save` метод преобразования документа в PDF с указанием параметров сохранения:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

Обязательно укажите правильный путь для сохранения преобразованного PDF-файла.

### Пример исходного кода для рендеринга Dml 3DEffects с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

Выполнив эти шаги, вы можете легко включить рендеринг эффектов 3D DML при преобразовании в PDF с помощью Aspose.Words для .NET.

## Заключение

В этом руководстве мы объяснили, как включить рендеринг эффектов 3D DML при преобразовании в PDF с помощью Aspose.Words для .NET. Следуя описанным шагам, вы сможете легко сохранить 3D-эффекты в созданном PDF-документе. Используйте эту функцию, чтобы сохранить важные визуальные эффекты исходного документа.


### Часто задаваемые вопросы

#### Вопрос: Что такое рендеринг 3D-эффектов DML в PDF-документе?
О: Рендеринг 3D-эффектов DML в документе PDF означает возможность сохранения 3D-эффектов при преобразовании документа в формат PDF. Это сохраняет визуальные эффекты и гарантирует, что созданный PDF-документ будет выглядеть как исходный документ.

#### Вопрос: Как включить рендеринг эффектов 3D DML при преобразовании в PDF с помощью Aspose.Words для .NET?
О: Чтобы включить рендеринг эффектов 3D DML при преобразовании в PDF с помощью Aspose.Words for .NET, выполните следующие действия:

 Создайте экземпляр`Document` класс, указывающий путь к документу Word.

 Создайте экземпляр`PdfSaveOptions`класс и установите`Dml3DEffectsRenderingMode` собственность`Dml3DEffectsRenderingMode.Advanced` чтобы включить расширенный рендеринг 3D-эффектов DML.

 Использовать`Save` метод`Document`class для сохранения документа в формате PDF, указав параметры сохранения.

#### Вопрос: Как проверить, были ли визуализированы эффекты 3D DML в созданном PDF-документе?
О: Чтобы проверить, были ли визуализированы 3D-эффекты DML в созданном PDF-документе, откройте PDF-файл с помощью совместимого средства просмотра PDF-файлов, например Adobe Acrobat Reader, и изучите документ. Вы должны увидеть 3D-эффекты в том виде, в котором они представлены в исходном документе.




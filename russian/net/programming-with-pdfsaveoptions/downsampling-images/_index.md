---
title: Понижение разрешения изображений
linktitle: Понижение разрешения изображений
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как уменьшить разрешение изображения при преобразовании в PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/downsampling-images/
---

В этом руководстве мы покажем вам, как уменьшить разрешение изображения при преобразовании в PDF с помощью Aspose.Words для .NET. Это уменьшает размер создаваемого PDF-файла. Выполните следующие действия:

## Шаг 1: Загрузка документа

Начните с загрузки документа, который вы хотите преобразовать в PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Обязательно укажите правильный путь к документу.

## Шаг 2. Настройте параметры сохранения PDF

Создайте экземпляр класса PdfSaveOptions и задайте параметры уменьшения масштаба изображения:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

`Resolution` свойство указывает целевое разрешение изображений и`ResolutionThreshold` Свойство указывает минимальное разрешение, ниже которого изображения не будут уменьшаться.

## Шаг 3. Конвертируйте документ в PDF

 Использовать`Save` метод преобразования документа в PDF с указанием параметров сохранения:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Обязательно укажите правильный путь для сохранения конвертированного PDF-файла.

### Пример исходного кода для понижения разрешения изображений с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//Мы можем установить минимальный порог для понижения частоты дискретизации.
	// Это значение предотвратит понижение разрешения второго изображения во входном документе.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Следуя этим шагам, вы можете легко уменьшить разрешение изображения при преобразовании в PDF с помощью Aspose.Words для .NET.



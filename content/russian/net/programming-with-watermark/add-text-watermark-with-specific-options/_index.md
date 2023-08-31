---
title: Добавить текстовый водяной знак с определенными параметрами
linktitle: Добавить текстовый водяной знак с определенными параметрами
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить текстовый водяной знак с определенными параметрами, используя Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

В этом руководстве мы расскажем, как добавить текстовый водяной знак с определенными параметрами, используя Aspose.Words для .NET. Текстовый водяной знак — это текст, наложенный на документ, чтобы указать, что он является черновиком, конфиденциальным и т. д.

## Шаг 1: Использование генератора документов

Во-первых, мы будем использовать генератор документов, чтобы добавить содержимое в наш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузка документа

Мы загрузим существующий документ, используя путь к документу.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Шаг 3. Добавьте текстовый водяной знак с определенными параметрами.

 Мы создадим экземпляр`TextWatermarkOptions` class и установите желаемые параметры для текстового водяного знака.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## Шаг 4: Сохраните документ

Наконец, мы можем сохранить документ с добавленным текстовым водяным знаком.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Пример исходного кода для добавления текстового водяного знака с определенными параметрами с помощью Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

Поздравляем! Теперь вы узнали, как добавить текстовый водяной знак с определенными параметрами, используя Aspose.Words для .NET.


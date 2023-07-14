---
title: Применение границ и заливки к абзацу
linktitle: Применение границ и заливки к абзацу
second_title: API обработки документов Aspose.Words
description: Узнайте, как применить границы и затенение к абзацу с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-formatting/apply-borders-and-shading-to-paragraph/
---

В этом уроке мы покажем вам, как применить границы и затенение к абзацу, используя функциональные возможности Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и применить изменения форматирования.

## Шаг 1: Создание и настройка документа

Для начала создайте новый документ и связанный с ним объект DocumentBuilder. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2: Настройка границы

Теперь давайте настроим границы абзаца, указав стиль границы для каждой стороны. Вот как:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Шаг 3: Настройка заполнения

Теперь мы настроим заливку абзаца, указав текстуру и цвета заливки. Вот как:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Шаг 4: Добавьте контент

Мы собираемся добавить в абзац некоторый форматированный контент. Вот как:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Шаг 3: Сохранение документа

 После вставки поля формы ввода текста сохраните документ в нужное место с помощью кнопки`Save` метод. Обязательно укажите правильный путь к файлу:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Пример исходного кода для применения границ и заливки к абзацу с использованием Aspose.Words для .NET

Вот полный исходный код для функции «Применить границы» и «Затенение абзаца» с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

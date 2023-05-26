---
title: Создайте диаграмму, используя фигуру
linktitle: Создайте диаграмму, используя фигуру
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как создать и настроить диаграмму с помощью фигуры в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-charts/create-chart-using-shape/
---

В этом руководстве объясняется, как создать диаграмму с использованием фигуры в документе Word с помощью Aspose.Words для .NET.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и работы с документами Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"`с фактическим путем к каталогу, в котором вы хотите сохранить документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте новый документ и DocumentBuilder
 Создайте новый экземпляр`Document` класс и`DocumentBuilder` объект для работы с документом.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Вставьте и настройте фигуру диаграммы
 Вставьте фигуру диаграммы в документ, используя`InsertChart` метод`DocumentBuilder` объект. Установите желаемый тип диаграммы и размеры.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Шаг 4: Настройте диаграмму
Настройте диаграмму, изменив различные свойства, такие как заголовок и легенда диаграммы.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Шаг 5: Сохраните документ
 Сохраните документ в указанную директорию с помощью`Save`метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithCharts.CreateChartUsingShape.docx».

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Пример исходного кода для создания диаграммы с помощью формы с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Обратите внимание, если в качестве текста заголовка указано нулевое или пустое значение, будет отображаться автоматически сгенерированный заголовок.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

Вот и все! Вы успешно создали диаграмму, используя фигуру в документе Word, используя Aspose.Words для .NET.
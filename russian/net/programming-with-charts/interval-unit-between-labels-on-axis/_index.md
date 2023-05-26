---
title: Единица интервала между метками на оси
linktitle: Единица интервала между метками на оси
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как установить единицу измерения интервала между метками на оси диаграммы с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для установки единицы интервала между метками на оси диаграммы. В предоставленном исходном коде показано, как создать диаграмму, добавить ряд данных и настроить метки осей.

## Шаг 1: Настройте проект

Убедитесь, что у вас есть следующие предварительные условия:

- Установлена библиотека Aspose.Words for .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов NuGet для его установки.
- Путь к каталогу документа, в котором будет сохранен выходной документ.

## Шаг 2. Создайте новый документ и вставьте диаграмму

 Создать новый`Document` объект и`DocumentBuilder` для построения документа.

```csharp
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Далее используйте`InsertChart` метод`DocumentBuilder` чтобы вставить столбчатую диаграмму в документ.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Шаг 3. Добавьте ряд данных на диаграмму.

Добавьте ряд данных на диаграмму. В этом примере мы добавим пять элементов с соответствующими значениями.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Шаг 4. Настройте метки осей

 Чтобы установить единицу измерения интервала между метками по оси X, откройте`AxisX` свойство диаграммы и установить`TickLabelSpacing` свойства до желаемого значения. В этом примере мы устанавливаем интервал равным 2.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## Шаг 5: Сохраните документ

 Наконец, сохраните документ в указанный каталог, используя`Save` метод`Document` объект.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

На этом реализация установки единицы интервала между метками на оси с помощью Aspose.Words for .NET завершена.

### Пример исходного кода для Interval Unit Between Labels On Axis с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```
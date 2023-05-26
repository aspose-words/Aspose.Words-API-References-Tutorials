---
title: Скрыть ось диаграммы
linktitle: Скрыть ось диаграммы
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как скрыть ось диаграммы в документе с помощью Aspose.Words для .NET. Скройте ось для более четкого и сфокусированного отображения диаграммы.
type: docs
weight: 10
url: /ru/net/programming-with-charts/hide-chart-axis/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET, чтобы скрыть ось диаграммы в документе. В предоставленном исходном коде показано, как создать диаграмму, добавить ряд данных и скрыть ось диаграммы.

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

 Затем вставьте диаграмму в документ с помощью кнопки`InsertChart` метод`DocumentBuilder`. В этом примере мы вставим столбчатую диаграмму.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Шаг 3. Добавьте ряд данных на диаграмму.

Добавьте ряд данных на диаграмму. В этом примере мы добавим пять элементов и соответствующие им значения.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Шаг 4. Скройте ось диаграммы

 Чтобы скрыть ось диаграммы, откройте`AxisY` свойство диаграммы и установить`Hidden` собственность на`true`.

```csharp
chart.AxisY.Hidden = true;
```

В этом примере мы скрываем ось Y диаграммы.

## Шаг 5: Сохраните документ

 Наконец, сохраните документ в указанный каталог, используя`Save` метод`Document` объект.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

На этом реализация скрытия оси диаграммы с помощью Aspose.Words for .NET завершена.

### Пример исходного кода для скрытия оси диаграммы с использованием Aspose.Words для .NET 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```
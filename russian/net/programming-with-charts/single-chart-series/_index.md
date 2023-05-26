---
title: Серия одиночных диаграмм
linktitle: Серия одиночных диаграмм
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как настроить отдельные серии диаграмм на диаграмме с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-charts/single-chart-series/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для настройки отдельных рядов диаграмм на диаграмме. В предоставленном исходном коде показано, как создать диаграмму, получить доступ к определенным рядам и изменить их свойства.

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

 Далее используйте`InsertChart` метод`DocumentBuilder` чтобы вставить линейную диаграмму в документ.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Шаг 3. Получите доступ к серии диаграмм и настройте ее

 Чтобы изменить отдельные серии диаграмм, вам необходимо получить доступ к`ChartSeries` объекты диаграммы.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Шаг 4: Сохраните документ

 Наконец, сохраните документ в указанный каталог, используя`Save` метод`Document` объект.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

На этом реализация настройки одной серии диаграмм с помощью Aspose.Words for .NET завершена.

### Пример исходного кода для серии одиночных диаграмм с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// Вы также можете указать, будет ли линия, соединяющая точки на графике, сглаживаться с помощью сплайнов Катмулла-Рома.
	series0.Smooth = true;
	series1.Smooth = true;
	// Указывает, должен ли родительский элемент по умолчанию инвертировать свои цвета, если значение отрицательное.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```
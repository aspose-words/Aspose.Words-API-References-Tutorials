---
title: Параметры по умолчанию для меток данных
linktitle: Параметры по умолчанию для меток данных
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как установить параметры по умолчанию для меток данных на диаграмме с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-charts/default-options-for-data-labels/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для установки параметров по умолчанию для меток данных на диаграмме. Предоставленный код демонстрирует, как создать диаграмму, добавить ряды данных и настроить метки данных с помощью Aspose.Words.

## Шаг 1: Настройте проект

Прежде чем мы начнем, убедитесь, что у вас есть следующие требования:

- Установлена библиотека Aspose.Words for .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов NuGet для его установки.
- Путь к каталогу документа, в котором будет сохранен выходной документ.

## Шаг 2. Создайте новый документ и вставьте диаграмму

 Сначала создадим новый`Document` объект и`DocumentBuilder` для построения документа.

```csharp
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Далее мы вставляем диаграмму в документ, используя`InsertChart` метод`DocumentBuilder`. В этом примере мы вставим круговую диаграмму.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Шаг 3. Добавьте ряды данных на диаграмму.

Теперь давайте добавим ряд данных на диаграмму. В этом примере мы добавим три категории и соответствующие им значения.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Шаг 4. Настройте метки данных

 Чтобы настроить метки данных на диаграмме, нам нужно получить доступ к`ChartDataLabelCollection` объект, связанный с сериалом.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Затем мы можем изменить различные свойства`labels` объект, чтобы установить нужные параметры для меток данных. В этом примере мы включим отображение процента и значения, отключим линии выноски и установим пользовательский разделитель.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Шаг 5: Сохраните документ

 Наконец, мы сохраняем документ в указанный каталог, используя`Save` метод`Document` объект.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

На этом реализация настройки параметров по умолчанию для меток данных на диаграмме с использованием Aspose.Words for .NET завершена.

### Пример исходного кода для параметров по умолчанию для меток данных с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```
---
title: Номер формата метки данных
linktitle: Номер формата метки данных
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как отформатировать количество меток данных на диаграмме с помощью Aspose.Words для .NET. Легко настраивайте числовые форматы для меток данных.
type: docs
weight: 10
url: /ru/net/programming-with-charts/format-number-of-data-label/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для форматирования количества меток данных на диаграмме. В предоставленном исходном коде показано, как создать диаграмму, добавить ряд данных и настроить числовой формат меток данных.

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

 Затем вставьте диаграмму в документ с помощью кнопки`InsertChart` метод`DocumentBuilder`В этом примере мы вставим линейный график.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Шаг 3. Добавьте ряд данных на диаграмму.

Добавьте ряд данных на диаграмму. В этом примере мы добавим три категории и соответствующие им значения.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Шаг 4. Настройте числовой формат меток данных

 Чтобы отформатировать количество меток данных, откройте`DataLabels` коллекция, связанная с сериалом.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

В этом примере мы устанавливаем разные числовые форматы для каждой метки данных. Первая метка данных отформатирована как денежная единица, вторая — как дата, а третья — как процент.

## Шаг 5: Сохраните документ

 Наконец, сохраните документ в указанный каталог, используя`Save` метод`Document` объект.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

На этом реализация форматирования количества меток данных на диаграмме с помощью Aspose.Words for .NET завершена.

### Пример исходного кода для формата номера метки данных с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Удалить серию, сгенерированную по умолчанию.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Или вы можете установить код формата, который будет связан с исходной ячейкой,
	// в этом случае NumberFormat будет сброшен на общий и унаследован от исходной ячейки.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```
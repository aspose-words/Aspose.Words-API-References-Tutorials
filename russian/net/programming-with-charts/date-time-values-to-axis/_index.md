---
title: Значения даты и времени по оси
linktitle: Значения даты и времени по оси
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как добавить значения даты и времени на ось диаграммы с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-charts/date-time-values-to-axis/
---

В этом руководстве объясняется, как добавить значения даты и времени на ось диаграммы с помощью Aspose.Words для .NET.

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
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Шаг 4: Добавьте данные на диаграмму
Добавьте данные в серию диаграмм, включая значения даты и времени.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Шаг 5: Настройте ось
Настройте ось X диаграммы для отображения значений даты и времени.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Шаг 6: Сохраните документ
 Сохраните документ в указанную директорию с помощью`Save`метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithCharts.DateTimeValuesToAxis.docx».

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Пример исходного кода для значений даты и времени по оси с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// Установите основные единицы на неделю и второстепенные единицы на день.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Этот пример кода создает новый документ Word, вставляет столбчатую диаграмму со значениями даты и времени по оси X и сохраняет документ в указанном каталоге.
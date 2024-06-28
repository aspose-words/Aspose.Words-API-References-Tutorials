---
title: Добавьте значения даты и времени на ось диаграммы
linktitle: Добавьте значения даты и времени на ось диаграммы
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить значения даты и времени на ось диаграммы с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-charts/date-time-values-to-axis/
---

В этом руководстве объясняется, как добавить значения даты и времени на ось диаграммы с помощью Aspose.Words для .NET.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором вы хотите сохранить документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Создайте новый документ и DocumentBuilder
 Создайте новый экземпляр`Document` класс и`DocumentBuilder` объект для работы с документом.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Вставьте и настройте фигуру диаграммы
 Вставьте фигуру диаграммы в документ, используя`InsertChart` метод`DocumentBuilder` Объект Object. Установите желаемый тип и размеры диаграммы.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Шаг 4. Добавьте данные в диаграмму
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
 Сохраните документ в указанную директорию, используя команду`Save` метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithCharts.DateTimeValuesToAxis.docx».

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Пример исходного кода для значений даты и времени по оси с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
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
	// Установите основные единицы на неделю, а второстепенные — на день.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

В этом примере кода создается новый документ Word, вставляется столбчатая диаграмма со значениями даты и времени по оси X и сохраняется документ в указанном каталоге.

## Заключение
В этом уроке вы узнали, как добавить значения даты и времени на ось диаграммы с помощью Aspose.Words для .NET. Следуя пошаговому руководству, вы сможете создать диаграмму, добавить в ряд значения даты и времени и настроить ось для точного отображения значений даты и времени. Aspose.Words for .NET предоставляет мощный набор функций для обработки слов с диаграммами в документах Word, что позволяет вам эффективно представлять и визуализировать данные со значениями даты и времени.

### Часто задаваемые вопросы

#### Вопрос 1. Могу ли я добавить значения даты и времени на ось диаграммы с помощью Aspose.Words для .NET?
Да, с помощью Aspose.Words for .NET вы можете добавлять и отображать значения даты и времени на оси диаграммы в документе Word. Aspose.Words предоставляет API и функциональные возможности для работы с различными диаграммами и настройки их внешнего вида, включая типы, обрабатывающие значения даты и времени на оси.

#### В2. Как добавить значения даты и времени в серию диаграмм?
 Чтобы добавить значения даты и времени в серию диаграмм, вы можете использовать команду`Add`метод серии диаграммы. Предоставьте массив значений даты и времени в качестве данных категории (ось X) вместе с соответствующими значениями серий. Это позволяет вам отображать точки данных со значениями даты и времени на диаграмме.

#### Вопрос 3. Как настроить ось для отображения значений даты и времени?
 Вы можете настроить ось диаграммы для отображения значений даты и времени, задав соответствующие свойства. Например, вы можете указать минимальное и максимальное значения для оси с помощью`Scaling.Minimum` и`Scaling.Maximum` свойства соответственно. Кроме того, вы можете установить основные и второстепенные единицы измерения, чтобы определить интервал и отметки для оси.

---
title: Добавить значения даты и времени к оси диаграммы
linktitle: Добавить значения даты и времени к оси диаграммы
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить значения даты и времени на ось диаграммы с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-charts/date-time-values-to-axis/
---

В этом руководстве объясняется, как добавить значения даты и времени на ось диаграммы с помощью Aspose.Words для .NET.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и Word Processing с документами Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором вы хотите сохранить документ.

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
 Сохраните документ в указанную директорию с помощью`Save` метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithCharts.DateTimeValuesToAxis.docx».

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Пример исходного кода для значений даты и времени по оси с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
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

## Заключение
В этом руководстве вы узнали, как добавлять значения даты и времени на ось диаграммы с помощью Aspose.Words для .NET. Следуя пошаговому руководству, вы можете создать диаграмму, добавить значения даты и времени в ряд и настроить ось для точного отображения значений даты и времени. Aspose.Words для .NET предоставляет мощный набор функций для обработки Word с диаграммами в документах Word, позволяя вам эффективно представлять и визуализировать данные со значениями даты и времени.

### Часто задаваемые вопросы

#### Q1. Могу ли я добавить значения даты и времени на ось диаграммы, используя Aspose.Words для .NET?
Да, с помощью Aspose.Words для .NET вы можете добавлять и отображать значения даты и времени на оси диаграммы в документе Word. Aspose.Words предоставляет API и функции для работы с различными типами диаграмм и настройки их внешнего вида, включая обработку значений даты и времени на оси.

#### Q2. Как добавить значения даты и времени в серию диаграмм?
 Чтобы добавить значения даты и времени в серию диаграммы, вы можете использовать`Add`метод серий графиков. Укажите массив значений даты и времени в качестве данных категории (ось X) вместе с соответствующими значениями ряда. Это позволяет отображать точки данных со значениями даты и времени на диаграмме.

#### Q3. Как настроить ось для отображения значений даты и времени?
 Вы можете настроить ось диаграммы для отображения значений даты и времени, задав соответствующие свойства. Например, вы можете указать минимальное и максимальное значения для оси, используя`Scaling.Minimum` и`Scaling.Maximum` свойства соответственно. Кроме того, вы можете установить основные и второстепенные единицы измерения, чтобы определить интервал и деления для оси.

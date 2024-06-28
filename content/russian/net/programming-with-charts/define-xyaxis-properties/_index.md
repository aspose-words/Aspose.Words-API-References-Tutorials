---
title: Определение свойств оси XY на диаграмме
linktitle: Определение свойств оси XY на диаграмме
second_title: API обработки документов Aspose.Words
description: Узнайте, как определить свойства оси XY на диаграмме с помощью Aspose.Words для .NET. Демонстрируются возможности настройки осей X и Y.
type: docs
weight: 10
url: /ru/net/programming-with-charts/define-xyaxis-properties/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для определения свойств осей X и Y на диаграмме. Предоставленный исходный код демонстрирует, как создать диаграмму, добавить данные серии и настроить свойства оси.

## Шаг 1. Настройте проект

Убедитесь, что у вас есть следующие предварительные условия:

- Установлена библиотека Aspose.Words для .NET. Вы можете загрузить его, используя для установки диспетчер пакетов NuGet.
- Путь к каталогу документов, в котором будет сохранен выходной документ.

## Шаг 2. Создайте новый документ и вставьте диаграмму.

 Создать новый`Document` объект и`DocumentBuilder` для построения документа.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Затем вставьте диаграмму в документ, используя`InsertChart` метод`DocumentBuilder`. В этом примере мы вставим диаграмму с областями.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Шаг 3. Добавьте данные серии на диаграмму

Добавьте данные серии на диаграмму. В этом примере мы добавим пять точек данных с соответствующими датами и значениями.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## Шаг 4. Настройте свойства осей X и Y.

 Чтобы настроить свойства осей X и Y, откройте`ChartAxis` объекты, связанные с диаграммой.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Измените свойства`xAxis` и`yAxis`объекты, чтобы установить нужные параметры для осей X и Y. В этом примере мы продемонстрируем некоторые общие свойства, которые можно настроить.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Шаг 5: Сохраните документ

 Наконец, сохраните документ в указанном каталоге, используя команду`Save` метод`Document` Объект Object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

На этом реализация определения свойств оси XY на диаграмме с использованием Aspose.Words для .NET завершена.

### Пример исходного кода для определения свойств XYAxis с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Вставить диаграмму
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// Измените ось X на категорию вместо даты, чтобы все точки были расположены с одинаковым интервалом на оси X.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; //Измеряется в единицах отображения по оси Y (сотни).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Заключение

В этом руководстве вы узнали, как определить свойства осей X и Y на диаграмме с помощью Aspose.Words для .NET. Следуя пошаговому руководству, вы сможете создать диаграмму, добавить данные серии и настроить свойства оси в соответствии с вашими конкретными требованиями. Aspose.Words for .NET предоставляет комплексный API для обработки слов с диаграммами в документах Word, что позволяет вам манипулировать различными аспектами диаграммы, включая оси.

Получив доступ к`ChartAxis` У объектов, связанных с диаграммой, можно изменять такие свойства, как тип категории, кресты осей, деления, положения меток, масштабирование и многое другое. Такая гибкость позволяет настроить внешний вид и поведение осей диаграммы для эффективного представления данных.

Используя Aspose.Words для .NET, вы можете легко интегрировать возможности создания и настройки диаграмм в свои .NET-приложения и автоматизировать создание профессионально выглядящих документов с богатой визуализацией.

### Часто задаваемые вопросы

#### Вопрос 1. Что такое Aspose.Words для .NET?
Aspose.Words for .NET — это мощная библиотека обработки документов, которая позволяет разработчикам создавать, манипулировать и сохранять документы Word программным способом в приложениях .NET. Он предоставляет широкий спектр функций для обработки текстов с элементами документа, включая диаграммы.

#### В2. Как установить Aspose.Words для .NET?
Вы можете установить Aspose.Words для .NET, загрузив его с помощью диспетчера пакетов NuGet в Visual Studio. Просто найдите «Aspose.Words» в менеджере пакетов NuGet и установите его в свой проект.

#### Вопрос 3. Могу ли я настроить другие аспекты диаграммы с помощью Aspose.Words для .NET?
Да, Aspose.Words for .NET предоставляет широкие возможности для настройки различных аспектов диаграммы. Помимо определения свойств оси, вы можете изменить тип диаграммы, ряды данных, легенду, заголовок, область графика, метки данных и многие другие элементы диаграммы. API предлагает детальный контроль над внешним видом и поведением диаграмм.

#### Вопрос 4. Могу ли я создавать различные типы диаграмм с помощью Aspose.Words для .NET?
 Да, Aspose.Words for .NET поддерживает широкий спектр типов диаграмм, включая область, гистограмму, линию, круговую диаграмму, точечную диаграмму и многое другое. Вы можете использовать`ChartType` перечисление для указания желаемого типа диаграммы при вставке фигуры диаграммы в документ Word.

#### Вопрос 5. Могу ли я сохранить диаграмму в разных форматах?
Да, Aspose.Words for .NET позволяет сохранять документ-диаграмму в различных форматах, таких как DOCX, PDF, HTML и других. Вы можете выбрать подходящий формат в зависимости от ваших требований и использовать`Save` метод`Document` объект для сохранения документа.

#### Вопрос 6. Могу ли я применить эти методы к нескольким диаграммам в документе?
 Да, вы можете применить эти методы к нескольким диаграммам в документе, повторяя необходимые шаги для каждой диаграммы. Вы можете создать отдельные`Chart` и`ChartAxis` объекты для каждой диаграммы и соответствующим образом настройте их свойства. Aspose.Words for .NET обеспечивает полную поддержку обработки текстов с несколькими диаграммами в одном документе.
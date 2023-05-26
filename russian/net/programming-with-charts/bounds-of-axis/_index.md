---
title: Границы оси
linktitle: Границы оси
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как установить границы оси на диаграмме с помощью Aspose.Words для .NET, управляя диапазоном значений, отображаемых на оси.
type: docs
weight: 10
url: /ru/net/programming-with-charts/bounds-of-axis/
---

В этом руководстве объясняется, как установить границы оси на диаграмме с помощью Aspose.Words для .NET. Вставив диаграмму, добавив ряд данных и настроив масштабирование оси, вы можете определить минимальное и максимальное значения для оси.

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

## Шаг 3. Вставьте и настройте диаграмму
 Вставьте диаграмму в документ с помощью кнопки`InsertChart` метод`DocumentBuilder` объект. Установите желаемый тип диаграммы и размеры.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Шаг 4: Добавьте данные серии
Очистите все существующие ряды на диаграмме и добавьте данные новых рядов. В этом примере мы добавляем серию с метками от «Элемент 1» до «Элемент 5» и соответствующими значениями.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Шаг 5: Установите границы оси
 Настройте масштабирование по оси Y, установив минимальное и максимальное значения с помощью`Scaling.Minimum` и`Scaling.Maximum` свойства оси.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Шаг 6: Сохраните документ
 Сохраните документ в указанную директорию с помощью`Save` метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithCharts.BoundsOfAxis.docx».

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Пример исходного кода для Bounds Of Axis с использованием Aspose.Words для .NET 

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
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

Вот и все! Вы успешно установили границы оси на диаграмме с помощью Aspose.Words для .NET.
---
title: Формат числа для оси
linktitle: Формат числа для оси
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как установить числовой формат для оси на диаграмме с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-charts/number-format-for-axis/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET, чтобы задать числовой формат для оси на диаграмме. В предоставленном исходном коде показано, как создать диаграмму, добавить ряд данных и отформатировать метки осей.

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
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Шаг 4. Отформатируйте метки осей

 Чтобы установить числовой формат для меток оси Y, откройте`AxisY` свойство диаграммы и установить`NumberFormat.FormatCode` свойства в нужный формат. В этом примере мы устанавливаем формат «#,##0» для отображения чисел с разделителями тысяч.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Шаг 5: Сохраните документ

 Наконец, сохраните документ в указанный каталог, используя`Save` метод`Document` объект.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

На этом реализация установки числового формата для оси с помощью Aspose.Words for .NET завершена.

### Пример исходного кода для числового формата для оси с использованием Aspose.Words для .NET 

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
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```
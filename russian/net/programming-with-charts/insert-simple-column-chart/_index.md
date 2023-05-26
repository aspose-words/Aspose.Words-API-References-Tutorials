---
title: Вставить простую столбчатую диаграмму
linktitle: Вставить простую столбчатую диаграмму
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставить простую столбчатую диаграмму в документ с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-charts/insert-simple-column-chart/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для вставки простой гистограммы в документ. В предоставленном исходном коде показано, как создать диаграмму, добавить ряд данных и сохранить документ.

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

 Далее используйте`InsertChart` метод`DocumentBuilder` чтобы вставить столбчатую диаграмму в документ. Вы можете указать различные типы и размеры диаграмм в соответствии с вашими требованиями.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Шаг 3. Добавьте ряд данных на диаграмму.

Добавьте ряд данных на диаграмму. В этом примере мы добавим несколько серий по две категории в каждой.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## Шаг 4: Сохраните документ

 Наконец, сохраните документ в указанный каталог, используя`Save` метод`Document` объект.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

На этом реализация вставки простой гистограммы с использованием Aspose.Words for .NET завершена.

### Пример исходного кода для вставки простой гистограммы с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Вы можете указать различные типы и размеры диаграмм.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Удалить серию, сгенерированную по умолчанию.
	seriesColl.Clear();
	// Создайте массив имен категорий, в этом уроке у нас есть две категории.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Обратите внимание, что массивы данных не должны быть пустыми, а массивы должны быть одного размера.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```
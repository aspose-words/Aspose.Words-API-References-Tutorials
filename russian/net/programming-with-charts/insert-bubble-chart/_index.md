---
title: Вставить пузырьковую диаграмму
linktitle: Вставить пузырьковую диаграмму
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставить пузырьковую диаграмму в документ с помощью Aspose.Words для .NET. Добавьте ряд данных со значениями X, Y и размера пузырьков.
type: docs
weight: 10
url: /ru/net/programming-with-charts/insert-bubble-chart/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для вставки пузырьковой диаграммы в документ. В предоставленном исходном коде показано, как создать диаграмму, добавить ряд данных и сохранить документ.

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

 Далее используйте`InsertChart` метод`DocumentBuilder` чтобы вставить пузырьковую диаграмму в документ.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## Шаг 3. Добавьте ряд данных на диаграмму.

Добавьте ряд данных на диаграмму. В этом примере мы добавим три точки данных с соответствующими значениями X, Y и размера пузырьков.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## Шаг 4: Сохраните документ

 Наконец, сохраните документ в указанный каталог, используя`Save` метод`Document` объект.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

На этом реализация вставки пузырьковой диаграммы с использованием Aspose.Words for .NET завершена.

### Пример исходного кода для вставки пузырьковой диаграммы с использованием Aspose.Words для .NET 

```csharp
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```
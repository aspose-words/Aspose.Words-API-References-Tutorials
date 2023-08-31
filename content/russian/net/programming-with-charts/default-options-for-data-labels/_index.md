---
title: Установите параметры по умолчанию для меток данных на диаграмме
linktitle: Установите параметры по умолчанию для меток данных на диаграмме
second_title: API обработки документов Aspose.Words
description: Узнайте, как установить параметры по умолчанию для меток данных на диаграмме с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-charts/default-options-for-data-labels/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для установки параметров по умолчанию для меток данных на диаграмме. Предоставленный код демонстрирует, как создать диаграмму, добавить ряды данных и настроить метки данных с помощью Aspose.Words.

## Шаг 1: Настройте проект

Прежде чем мы начнем, убедитесь, что у вас есть следующие требования:

- Установлена библиотека Aspose.Words for .NET. Вы можете загрузить его с помощью диспетчера пакетов NuGet, чтобы установить его.
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

 Затем мы можем изменить различные свойства`labels`объект, чтобы установить нужные параметры для меток данных. В этом примере мы включим отображение процента и значения, отключим линии выноски и установим пользовательский разделитель.

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
	//Путь к вашему каталогу документов
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

## Заключение

В этом руководстве вы узнали, как установить параметры по умолчанию для меток данных на диаграмме с помощью Aspose.Words для .NET. Следуя пошаговому руководству, вы сможете создать диаграмму, добавить ряды данных и настроить метки данных в соответствии со своими конкретными требованиями. Aspose.Words для .NET предоставляет мощный API для обработки Word с диаграммами в документах Word, позволяя вам манипулировать различными элементами диаграмм и добиваться желаемого внешнего вида и функциональности.

 Задав свойства`ChartDataLabelCollection`объекта, связанного с серией диаграммы, можно управлять отображением меток данных, включая такие параметры, как отображение процентов, значений, линий выноски и настраиваемых разделителей. Такая гибкость позволяет эффективно представлять данные и улучшать визуальное представление ваших диаграмм.

### Часто задаваемые вопросы

#### Q1. Что такое Aspose.Words для .NET?
Aspose.Words for .NET — это библиотека, которая позволяет разработчикам программно создавать, обрабатывать и сохранять документы Word с помощью приложений .NET. Он предоставляет широкий спектр функций для обработки текстов с элементами документа, включая диаграммы.

#### Q2. Как я могу установить Aspose.Words для .NET?
Вы можете установить Aspose.Words для .NET, загрузив его с помощью диспетчера пакетов NuGet в Visual Studio. Просто найдите «Aspose.Words» в диспетчере пакетов NuGet и установите его в свой проект.

#### Q3. Могу ли я настроить другие аспекты диаграммы с помощью Aspose.Words для .NET?
Да, Aspose.Words для .NET позволяет настраивать различные аспекты диаграммы, такие как тип диаграммы, метки осей, легенда, область построения и многое другое. Вы можете получить доступ к различным свойствам объекта диаграммы и изменить их, чтобы добиться желаемого внешнего вида и поведения.

#### Q4. Могу ли я сохранить диаграмму в разных форматах?
 Да, Aspose.Words для .NET поддерживает сохранение документа, содержащего диаграмму, в различных форматах, включая DOCX, PDF, HTML и другие. Вы можете выбрать подходящий формат в зависимости от ваших требований и использовать`Save` метод`Document` объект для сохранения документа.

#### Q5. Могу ли я применить эти методы к другим типам диаграмм?
Да, методы, описанные в этом руководстве, можно применять к другим типам диаграмм, поддерживаемым Aspose.Words для .NET. Ключ в том, чтобы получить доступ к соответствующим объектам и свойствам, специфичным для типа диаграммы, с которой вы работаете в Word Processing.
---
title: Настройка метки данных диаграммы
linktitle: Настройка метки данных диаграммы
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавлять и настраивать метки данных на диаграмме с помощью Aspose.Words для .NET, чтобы предоставить дополнительную информацию о точках данных.
type: docs
weight: 10
url: /ru/net/programming-with-charts/chart-data-label/
---

В этом руководстве объясняется, как добавлять и настраивать метки данных на диаграмме с помощью Aspose.Words для .NET. Метки данных предоставляют дополнительную информацию о точках данных на диаграмме.

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

## Шаг 3. Вставьте и настройте диаграмму
 Вставьте диаграмму в документ с помощью`InsertChart` метод`DocumentBuilder` Объект Object. Установите желаемый тип и размеры диаграммы.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## Шаг 4. Настройте метки данных
Получите доступ к коллекции меток данных серии диаграмм и измените различные свойства, чтобы настроить внешний вид меток данных.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## Шаг 5: Сохраните документ
 Сохраните документ в указанную директорию, используя команду`Save` метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithCharts.ChartDataLabel.docx».

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Пример исходного кода для метки данных диаграммы с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// По умолчанию, когда вы добавляете метки данных к точкам данных на круговой диаграмме, линии выноски отображаются для меток данных, которые
	// расположен далеко за пределами точек данных. Линии-выноски создают визуальную связь между меткой данных и ее
	// соответствующая точка данных.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

Вот и все! Вы успешно добавили и настроили метки данных на диаграмме с помощью Aspose.Words для .NET.

## Заключение
В этом руководстве вы узнали, как добавлять и настраивать метки данных на диаграмме с помощью Aspose.Words для .NET. Следуя пошаговому руководству, вы можете вставить диаграмму, получить доступ к коллекции меток данных и изменить свойства, чтобы настроить внешний вид меток данных. Aspose.Words for .NET предоставляет мощный API для обработки слов с документами и диаграммами Word, позволяющий создавать визуально интересные и информативные диаграммы с настраиваемыми метками данных.

### Часто задаваемые вопросы

#### Вопрос 1. Что такое метки данных на диаграмме?
Метки данных на диаграмме предоставляют дополнительную информацию о точках данных, представленных на диаграмме. Они могут отображать значения, категории, названия рядов, проценты или другие важные сведения в зависимости от типа диаграммы и конфигурации.

#### В2. Могу ли я настроить внешний вид меток данных?
Да, вы можете настроить внешний вид меток данных на диаграмме. Aspose.Words для .NET предоставляет возможности для изменения различных свойств меток данных, таких как отображение ключей легенды, линий выноски, названий категорий, названий серий, значений и т. д. Вы также можете установить разделители и отформатировать метки в соответствии с вашими конкретными требованиями.

#### Вопрос 3. Могу ли я добавлять метки данных к любому типу диаграммы?
Да, вы можете добавлять метки данных к различным типам диаграмм, включая гистограммы, круговые диаграммы, линейные диаграммы и т. д. Процесс добавления и настройки меток данных может незначительно отличаться в зависимости от типа диаграммы и используемой библиотеки или инструмента.

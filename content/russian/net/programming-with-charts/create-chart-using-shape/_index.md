---
title: Создание и настройка диаграммы с использованием формы
linktitle: Создание и настройка диаграммы с использованием формы
second_title: API обработки документов Aspose.Words
description: Узнайте, как создать и настроить диаграмму с помощью фигуры в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-charts/create-chart-using-shape/
---

В этом руководстве объясняется, как создать диаграмму с использованием фигуры в документе Word с помощью Aspose.Words для .NET.

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
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Шаг 4: Настройте диаграмму
Настройте диаграмму, изменив различные свойства, такие как заголовок и легенда диаграммы.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Шаг 5: Сохраните документ
 Сохраните документ в указанную директорию с помощью`Save` метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithCharts.CreateChartUsingShape.docx».

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Пример исходного кода для создания диаграммы с помощью формы с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Обратите внимание, если в качестве текста заголовка указано нулевое или пустое значение, будет отображаться автоматически сгенерированный заголовок.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

Вот и все! Вы успешно создали диаграмму, используя фигуру в документе Word, используя Aspose.Words для .NET.

## Заключение
В этом руководстве вы узнали, как создать диаграмму, используя фигуру в документе Word, используя Aspose.Words для .NET. Следуя пошаговому руководству, вы сможете вставлять и настраивать форму диаграммы, настраивать ее внешний вид и сохранять документ. Aspose.Words для .NET предоставляет полный набор функций для обработки Word документов и диаграмм Word, позволяя вам создавать профессионально выглядящие и визуально привлекательные диаграммы непосредственно в ваших приложениях .NET.

### Часто задаваемые вопросы

#### Q1. Могу ли я создавать диаграммы в документе Word, используя Aspose.Words для .NET?
Да, с помощью Aspose.Words для .NET вы можете программно создавать диаграммы в документе Word. Aspose.Words предоставляет API и функции для вставки различных типов диаграмм, настройки их внешнего вида и управления данными диаграмм.

#### Q2. Какие типы диаграмм поддерживаются Aspose.Words для .NET?
Aspose.Words для .NET поддерживает широкий спектр типов диаграмм, включая линейные диаграммы, гистограммы, круговые диаграммы, диаграммы с областями, точечные диаграммы и многое другое. Вы можете выбрать подходящий тип диаграммы на основе ваших данных и требований к визуализации.

#### Q3. Могу ли я настроить внешний вид созданной диаграммы?
Да, вы можете настроить внешний вид созданной диаграммы с помощью Aspose.Words for .NET. Вы можете изменить такие свойства, как заголовок диаграммы, положение легенды, метки данных, метки осей, цвета и другие визуальные элементы, чтобы удовлетворить ваши конкретные потребности в дизайне и форматировании.

---
title: Установите флажок «Выравнивание многострочной метки»
linktitle: Установите флажок «Выравнивание многострочной метки»
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как выровнять многострочные метки делений на оси диаграммы с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-charts/tick-multi-line-label-alignment/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для установки выравнивания многострочных меток в виде галочек на оси диаграммы. В предоставленном исходном коде показано, как создать диаграмму, получить доступ к оси и изменить выравнивание метки деления.

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

 Далее используйте`InsertChart` метод`DocumentBuilder` чтобы вставить точечную диаграмму в документ.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Шаг 3. Установите выравнивание галочки

 Чтобы настроить выравнивание многострочных меток в виде галочек, откройте`AxisX` свойство диаграммы и установить`TickLabelAlignment` свойство до желаемого выравнивания. В этом примере мы устанавливаем выравнивание на`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Шаг 4: Сохраните документ

 Наконец, сохраните документ в указанный каталог, используя`Save` метод`Document` объект.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

На этом реализация настройки выравнивания многострочных меток с помощью Aspose.Words for .NET завершена.

### Пример исходного кода для выравнивания меток Tick Multi Line с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Это свойство действует только для многострочных меток.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```
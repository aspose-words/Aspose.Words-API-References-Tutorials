---
title: Границы оси на диаграмме
linktitle: Границы оси на диаграмме
second_title: API обработки документов Aspose.Words
description: Узнайте, как установить границы оси на диаграмме с помощью Aspose.Words для .NET, управляющего диапазоном значений, отображаемых на оси.
type: docs
weight: 10
url: /ru/net/programming-with-charts/bounds-of-axis/
---

В этом руководстве объясняется, как установить границы оси на диаграмме с помощью Aspose.Words для .NET. Вставив диаграмму, добавив данные серии и настроив масштабирование оси, вы можете определить минимальное и максимальное значения для оси.

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
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Шаг 4. Добавьте данные серии
Очистите все существующие серии на диаграмме и добавьте данные новых серий. В этом примере мы добавляем серию с метками «Элемент 1» к «Элемент 5» и соответствующими значениями.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Шаг 5: Установите границы оси
 Настройте масштабирование оси Y, задав минимальное и максимальное значения с помощью кнопки`Scaling.Minimum` и`Scaling.Maximum` свойства оси.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Шаг 6: Сохраните документ
 Сохраните документ в указанную директорию, используя команду`Save` метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithCharts.BoundsOfAxis.docx».

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Пример исходного кода для Bounds Of Axis с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
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

Вот и все! Вы успешно установили границы оси диаграммы с помощью Aspose.Words для .NET.

## Заключение
В этом уроке вы узнали, как установить границы оси диаграммы с помощью Aspose.Words для .NET. Следуя пошаговому руководству, вы можете вставить и настроить диаграмму, добавить данные серии и определить минимальное и максимальное значения масштабирования оси. Aspose.Words for .NET предоставляет мощный и гибкий API для обработки слов с документами Word, позволяющий с легкостью создавать динамические и визуально привлекательные диаграммы.


### Часто задаваемые вопросы

#### Вопрос 1. Что такое Aspose.Words для .NET?
Aspose.Words for .NET — это библиотека, которая позволяет разработчикам программно работать с документами Word. Он предоставляет широкий спектр функций и возможностей для создания, управления и сохранения документов Word.

#### В2. Как установить Aspose.Words для .NET?
Чтобы установить Aspose.Words для .NET, вы можете использовать диспетчер пакетов NuGet в Visual Studio. Просто найдите «Aspose.Words» в менеджере пакетов NuGet и установите его в свой проект.

#### Вопрос 3. Могу ли я использовать Aspose.Words для .NET с другими языками программирования?
Нет, Aspose.Words for .NET специально разработан для .NET-приложений. Он работает с такими языками программирования, как C# и VB.NET.

#### Вопрос 4. Есть ли какие-либо другие предпосылки для использования Aspose.Words для .NET?
Помимо установки библиотеки Aspose.Words for .NET, вам необходимо иметь базовые знания в области программирования C# и обработки текстов с документами Word. Знакомство с .NET Framework также будет полезно.

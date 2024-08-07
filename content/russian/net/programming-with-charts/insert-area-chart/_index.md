---
title: Вставить диаграмму области в документ Word
linktitle: Вставить диаграмму области в документ Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить диаграмму с областями в документ с помощью Aspose.Words для .NET. Добавьте данные серии и сохраните документ с диаграммой.
type: docs
weight: 10
url: /ru/net/programming-with-charts/insert-area-chart/
---
## Введение

Добро пожаловать в это пошаговое руководство о том, как вставить диаграмму с областями в документ Word с помощью Aspose.Words для .NET. Независимо от того, являетесь ли вы опытным разработчиком или только начинаете, это руководство расскажет вам все, что вам нужно знать, чтобы создавать потрясающие и информативные диаграммы с областями в ваших документах Word. Мы рассмотрим предварительные требования, покажем, как импортировать необходимые пространства имен, и проведем вас через каждый этап процесса с помощью четких и простых инструкций.

## Предварительные условия

Прежде чем мы углубимся, давайте убедимся, что у вас есть все необходимое для начала:

1.  Aspose.Words для .NET: убедитесь, что у вас установлен Aspose.Words для .NET. Вы можете скачать его[здесь](https://releases.aspose.com/words/net/).
2. .NET Framework: убедитесь, что на вашем компьютере установлена .NET Framework.
3. IDE: Интегрированная среда разработки (IDE), такая как Visual Studio, для написания и выполнения вашего кода.
4. Базовые знания C#: базовое понимание программирования на C# будет полезно.

Если у вас есть все необходимые условия, вы готовы приступить к созданию красивых диаграмм с областями в документах Word.

## Импортировать пространства имен

Прежде всего, давайте импортируем необходимые пространства имен. Эти пространства имен предоставляют классы и методы, необходимые для работы с документами и диаграммами Word в Aspose.Words для .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System;
```

Теперь, когда мы импортировали основные пространства имен, давайте перейдем к созданию нашего документа и пошаговой вставке диаграммы с областями.

## Шаг 1. Создайте новый документ Word

Начнем с создания нового документа Word. Это будет основа, куда мы вставим нашу диаграмму областей.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

 На этом этапе мы инициализируем новый`Document` объект, который представляет наш документ Word.

## Шаг 2. Используйте DocumentBuilder для вставки диаграммы

 Далее мы будем использовать`DocumentBuilder` class, чтобы вставить диаграмму с областями в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
```

 Здесь мы создаем`DocumentBuilder` объект и используйте его, чтобы вставить в наш документ диаграмму с областями определенных размеров (432x252).

## Шаг 3. Доступ к объекту диаграммы

 После вставки диаграммы нам нужно получить доступ к`Chart` объект, чтобы настроить нашу диаграмму областей.

```csharp
Chart chart = shape.Chart;
```

 Эта строка кода извлекает`Chart` объект из фигуры, которую мы только что вставили.

## Шаг 4. Добавьте данные серии на диаграмму

Теперь пришло время добавить некоторые данные в нашу диаграмму. Мы добавим серию с датами и соответствующими значениями.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

На этом этапе мы добавляем серию с именем «Aspose Series 1» с набором дат и соответствующими значениями.

## Шаг 5: Сохраните документ

Наконец, мы сохраним наш документ со вставленной диаграммой с областями.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Эта строка кода сохраняет документ в указанный каталог с заданным именем файла.

## Заключение

Поздравляем! Вы успешно вставили диаграмму с областями в документ Word с помощью Aspose.Words для .NET. В этом руководстве описаны все этапы: от настройки среды до сохранения окончательного документа. С помощью Aspose.Words for .NET вы можете создавать самые разнообразные диаграммы и другие сложные элементы в документах Word, делая ваши отчеты и презентации более динамичными и информативными.

## Часто задаваемые вопросы

### Могу ли я использовать Aspose.Words для .NET с другими языками .NET?
Да, Aspose.Words for .NET поддерживает другие языки .NET, такие как VB.NET.

### Можно ли настроить внешний вид диаграммы?
Абсолютно! Aspose.Words for .NET предоставляет широкие возможности для настройки внешнего вида ваших диаграмм.

### Могу ли я добавить несколько диаграмм в один документ Word?
Да, вы можете вставить в один документ Word столько диаграмм, сколько вам нужно.

### Поддерживает ли Aspose.Words для .NET другие типы диаграмм?
Да, Aspose.Words for .NET поддерживает различные типы диаграмм, включая гистограммы, линии, круговые диаграммы и т. д.

### Где я могу получить временную лицензию на Aspose.Words для .NET?
 Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
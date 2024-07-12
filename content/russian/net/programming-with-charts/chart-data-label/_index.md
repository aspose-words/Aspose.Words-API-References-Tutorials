---
title: Настройка метки данных диаграммы
linktitle: Настройка метки данных диаграммы
second_title: API обработки документов Aspose.Words
description: Узнайте, как настроить метки данных диаграммы с помощью Aspose.Words для .NET, в пошаговом руководстве. Идеально подходит для разработчиков .NET.
type: docs
weight: 10
url: /ru/net/programming-with-charts/chart-data-label/
---
## Введение

Вы хотите усовершенствовать свои .NET-приложения с помощью динамических и настраиваемых возможностей обработки документов? Aspose.Words for .NET может стать вашим ответом! В этом руководстве мы углубимся в настройку меток данных диаграммы с помощью Aspose.Words для .NET, мощной библиотеки для создания, изменения и преобразования документов Word. Независимо от того, являетесь ли вы опытным разработчиком или только начинаете, это руководство проведет вас через каждый шаг, гарантируя, что вы поймете, как эффективно использовать этот инструмент.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующее:

1. Visual Studio: установите Visual Studio 2019 или новее.
2. .NET Framework: убедитесь, что у вас установлена .NET Framework 4.0 или более поздняя версия.
3.  Aspose.Words для .NET: Загрузите и установите Aspose.Words для .NET с сайта[ссылка для скачивания](https://releases.aspose.com/words/net/).
4. Базовые знания C#: Знание программирования на C# необходимо.
5.  Действующая лицензия: получите[временная лицензия](https://purchase.aspose.com/temporary-license/) или приобрести его в[Купить ссылку](https://purchase.aspose.com/buy).

## Импортировать пространства имен

Для начала вам необходимо импортировать необходимые пространства имен в ваш проект C#. Этот шаг имеет решающее значение, поскольку он гарантирует, что у вас есть доступ ко всем классам и методам, предоставляемым Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Charts;
```

## Шаг 1. Инициализируйте документ и DocumentBuilder

Чтобы создавать документы Word и манипулировать ими, нам сначала необходимо инициализировать экземпляр`Document` класс и`DocumentBuilder` объект.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Объяснение

- Документ документа: создает новый экземпляр класса Document.
- Построитель DocumentBuilder: DocumentBuilder помогает вставлять содержимое в объект Document.

## Шаг 2. Вставьте диаграмму

 Далее мы вставим в документ гистограмму, используя`DocumentBuilder` объект.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

### Объяснение

- Фигура: представляет диаграмму как фигуру в документе.
- builder.InsertChart(ChartType.Bar, 432, 252): вставляет гистограмму с указанными размерами.

## Шаг 3. Доступ к серии диаграмм

Чтобы настроить метки данных, нам сначала нужно получить доступ к рядам на диаграмме.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
```

### Объяснение

- ChartSeries series0: извлекает первую серию диаграммы, которую мы настроим.

## Шаг 4. Настройте метки данных

Метки данных можно настроить для отображения различной информации. Мы настроим метки так, чтобы они отображали ключ легенды, имя серии и значение, скрывая при этом имя категории и процентное соотношение.

```csharp
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

### Объяснение

- Ярлыки ChartDataLabelCollection: доступ к меткам данных серии.
- labels.ShowLegendKey: отображает ключ легенды.
- labels.ShowLeaderLines: показывает линии выноски для меток данных, расположенных далеко за пределами точек данных.
- labels.ShowCategoryName: скрывает имя категории.
- labels.ShowPercentage: скрывает процентное значение.
- labels.ShowSeriesName: отображает имя серии.
- labels.ShowValue: отображает значение точек данных.
- labels.Separator: устанавливает разделитель для меток данных.

## Шаг 5: Сохраните документ

Наконец, сохраните документ в указанном каталоге.

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Объяснение

- doc.Save: сохраняет документ с указанным именем в указанном каталоге.

## Заключение

 Поздравляем! Вы успешно настроили метки данных диаграммы с помощью Aspose.Words для .NET. Эта библиотека предлагает надежное решение для программной обработки документов Word, упрощая разработчикам создание сложных и динамических приложений для обработки документов. Погрузитесь в[документация](https://reference.aspose.com/words/net/) чтобы изучить больше функций и возможностей.

## Часто задаваемые вопросы

### Что такое Aspose.Words для .NET?
Aspose.Words for .NET — это мощная библиотека обработки документов, которая позволяет разработчикам программно создавать, изменять и конвертировать документы Word.

### Как установить Aspose.Words для .NET?
 Вы можете скачать и установить его с сайта[ссылка для скачивания](https://releases.aspose.com/words/net/). Следуйте предоставленным инструкциям по установке.

### Могу ли я попробовать Aspose.Words для .NET бесплатно?
 Да, вы можете получить[бесплатная пробная версия](https://releases.aspose.com/) или[временная лицензия](https://purchase.aspose.com/temporary-license/)оценить товар.

### Совместим ли Aspose.Words для .NET с .NET Core?
Да, Aspose.Words для .NET совместим с .NET Core, .NET Standard и .NET Framework.

### Где я могу получить поддержку Aspose.Words для .NET?
 Вы можете посетить[форум поддержки](https://forum.aspose.com/c/words/8) за помощь и содействие со стороны сообщества и экспертов Aspose.

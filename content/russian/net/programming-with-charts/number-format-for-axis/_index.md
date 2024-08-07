---
title: Числовой формат для оси диаграммы
linktitle: Числовой формат для оси диаграммы
second_title: API обработки документов Aspose.Words
description: Узнайте, как форматировать номера осей диаграммы с помощью Aspose.Words для .NET, с помощью этого пошагового руководства. Повысьте читаемость и профессионализм вашего документа без особых усилий.
type: docs
weight: 10
url: /ru/net/programming-with-charts/number-format-for-axis/
---
## Введение

Привет! Вы когда-нибудь работали с диаграммами в своих документах и хотели бы отформатировать числа на оси, чтобы они выглядели более профессионально? Что ж, вам повезло! В этом уроке мы углубимся в то, как этого можно добиться с помощью Aspose.Words для .NET. Эта мощная библиотека позволяет вам работать с документами Word проще простого. И сегодня мы сосредоточимся на том, чтобы преобразить эти оси диаграммы с помощью пользовательских числовых форматов.

## Предварительные условия

Прежде чем мы начнем, давайте убедимся, что у вас есть все необходимое. Вот краткий контрольный список:

-  Aspose.Words для .NET: убедитесь, что он у вас установлен. Если нет, вы можете[скачай это здесь](https://releases.aspose.com/words/net/).
- .NET Framework: убедитесь, что у вас установлена совместимая платформа .NET Framework.
- Среда разработки: IDE, такая как Visual Studio, будет работать отлично.
- Базовые знания C#: это поможет вам следовать примерам кодирования.

## Импортировать пространства имен

Прежде всего, вам необходимо импортировать необходимые пространства имен в ваш проект. Это похоже на закладку фундамента перед постройкой дома. Добавьте следующие директивы using в начало файла кода:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Reporting;
```

Теперь давайте разобьем весь процесс на простые и понятные шаги.

## Шаг 1. Настройка документа

Заголовок: Инициализируйте свой документ

Во-первых, вам нужно создать новый документ и построитель документов. Думайте об этом шаге как о подготовке холста и кисти перед тем, как приступить к созданию шедевра.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Здесь,`dataDir` — это путь к каталогу вашего документа, в котором вы сохраните окончательный файл.`Document`и`DocumentBuilder` — это классы из Aspose.Words, которые помогают создавать документы Word и манипулировать ими.

## Шаг 2. Вставка диаграммы

Заголовок: Добавьте диаграмму в документ

Далее давайте добавим диаграмму в ваш документ. Вот тут-то и начинается волшебство. Мы вставим столбчатую диаграмму, которая будет служить нашим чистым холстом.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

`InsertChart` Метод вставляет в документ диаграмму указанного типа (в данном случае столбца) и размеров.

## Шаг 3. Настройка серии диаграмм

Заголовок: Заполните диаграмму данными

Теперь нам нужно добавить некоторые данные в нашу диаграмму. Этот шаг сродни заполнению диаграммы значимой информацией.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

 Здесь мы добавляем новую серию под названием «Aspose Series 1» с пятью точками данных.`Series.Clear` Метод гарантирует, что все ранее существовавшие данные будут удалены перед добавлением новой серии.

## Шаг 4. Форматирование чисел по осям

Заголовок: Украсьте свои числа по осям

Наконец, давайте отформатируем числа по оси Y, чтобы сделать их более читабельными. Это похоже на нанесение последних штрихов на ваше произведение искусства.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

`FormatCode` Свойство позволяет установить собственный формат чисел на оси. В этом примере`#,##0`гарантирует, что большие числа отображаются с запятыми для тысяч.

## Шаг 5: Сохранение документа

Рубрика: Сохраните свой шедевр

Теперь, когда все настроено, пришло время сохранить документ. Этот шаг — грандиозное открытие вашей работы.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

 Здесь`Save` метод сохраняет документ по указанному пути с именем файла`WorkingWithCharts.NumberFormatForAxis.docx`.

## Заключение

И вот оно! Вы успешно отформатировали числа на оси Y диаграммы с помощью Aspose.Words для .NET. Это не только сделает ваши диаграммы более профессиональными, но и улучшит их читаемость. Aspose.Words предлагает множество функций, которые помогут вам программно создавать потрясающие документы Word. Итак, почему бы не изучить больше и посмотреть, что еще вы можете сделать?

## Часто задаваемые вопросы

### Что такое Aspose.Words для .NET?
Aspose.Words for .NET — это мощная библиотека, которая позволяет разработчикам программно создавать, манипулировать и конвертировать документы Word.

### Могу ли я отформатировать другие аспекты диаграммы, помимо номеров осей?
Абсолютно! Aspose.Words для .NET позволяет форматировать заголовки, метки и даже настраивать внешний вид диаграммы.

### Доступна ли бесплатная пробная версия Aspose.Words для .NET?
 Да, вы можете получить[бесплатная пробная версия здесь](https://releases.aspose.com/).

### Могу ли я использовать Aspose.Words для .NET с другими языками .NET, кроме C#?
Да, Aspose.Words for .NET совместим с любым языком .NET, включая VB.NET и F#.

### Где я могу найти более подробную документацию?
 Подробная документация доступна на сайте[Страница документации Aspose.Words для .NET](https://reference.aspose.com/words/net/).

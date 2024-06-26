---
title: Вставить диаграмму области в документ Word
linktitle: Вставить диаграмму области в документ Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить диаграмму с областями в документ с помощью Aspose.Words для .NET. Добавьте данные серии и сохраните документ с диаграммой.
type: docs
weight: 10
url: /ru/net/programming-with-charts/insert-area-chart/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для вставки диаграммы с областями в документ. Предоставленный исходный код демонстрирует, как создать диаграмму, добавить данные серии и сохранить документ.

## Шаг 1. Настройте проект

Убедитесь, что у вас есть следующие предварительные условия:

- Установлена библиотека Aspose.Words для .NET. Вы можете загрузить его, используя для установки диспетчер пакетов NuGet.
- Путь к каталогу документов, в котором будет сохранен выходной документ.

## Шаг 2. Создайте новый документ и вставьте диаграмму.

 Создать новый`Document` объект и`DocumentBuilder` для построения документа.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Далее используйте`InsertChart` метод`DocumentBuilder` чтобы вставить диаграмму с областями в документ.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Шаг 3. Добавьте данные серии на диаграмму

Добавьте данные серии на диаграмму. В этом примере мы добавим пять точек данных с соответствующими датами и значениями.

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

## Шаг 4. Сохраните документ.

 Наконец, сохраните документ в указанном каталоге, используя команду`Save` метод`Document` Объект Object.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

На этом реализация вставки диаграммы с областями с помощью Aspose.Words для .NET завершена.

### Пример исходного кода для вставки диаграммы с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### Заключение

В этом уроке вы узнали, как вставить диаграмму с областями в документ Word с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, вы можете создать новый документ, вставить диаграмму с областями, добавить данные серии и сохранить документ вместе с диаграммой.

Aspose.Words for .NET предоставляет мощный API для обработки слов с диаграммами в документах Word. Всего с помощью нескольких строк кода вы можете создавать профессионально выглядящие диаграммы с областями и настраивать их в соответствии со своими требованиями. Диаграммы с областями обычно используются для отображения величины и тенденций данных во времени или по категориям.

Используя Aspose.Words для .NET, вы можете автоматизировать процесс создания документов с диаграммами областей, экономя время и усилия при создании документов вручную. Библиотека предлагает широкий спектр типов диаграмм и возможностей настройки, позволяющих создавать визуально привлекательные и информативные диаграммы в документах Word.

### Часто задаваемые вопросы

#### Вопрос 1. Что такое Aspose.Words для .NET?
Aspose.Words for .NET — это мощная библиотека обработки документов, которая позволяет разработчикам программно создавать, изменять и конвертировать документы Word в приложениях .NET. Он предоставляет полный набор API-интерфейсов для обработки текстов с элементами документа, включая диаграммы, абзацы, таблицы и многое другое.

#### В2. Как установить Aspose.Words для .NET?
Чтобы установить Aspose.Words для .NET, вы можете использовать диспетчер пакетов NuGet в Visual Studio, чтобы установить библиотеку непосредственно в ваш проект. Просто найдите «Aspose.Words» в менеджере пакетов NuGet и установите пакет.

#### Вопрос 3. Могу ли я настроить внешний вид диаграммы с областями?
Да, используя Aspose.Words для .NET, вы можете настроить различные аспекты внешнего вида диаграммы с областями. Вы можете изменить такие свойства, как заголовок диаграммы, цвет ряда, метки осей и форматирование области диаграммы. Библиотека предоставляет богатый набор API-интерфейсов для управления визуальными элементами диаграммы и создания индивидуального внешнего вида, соответствующего вашим потребностям.

#### Вопрос 4. Могу ли я добавить несколько серий на диаграмму с областями?
Да, вы можете добавить несколько рядов в диаграмму с областями, используя Aspose.Words для .NET. Каждая серия представляет собой набор точек данных, нанесенных на диаграмму. Вы можете добавлять серии с разными наборами данных и индивидуально настраивать каждую серию, включая ее имя, точки данных и внешний вид.

#### Вопрос 5. Могу ли я сохранить документ со вставленной диаграммой с областями в разных форматах?
 Да, Aspose.Words for .NET позволяет сохранять документ со вставленной диаграммой областей в различных форматах, таких как DOCX, PDF, HTML и других. Вы можете выбрать желаемый формат вывода в соответствии с вашими требованиями и использовать`Save` метод`Document` объект для сохранения документа. Вставленная диаграмма с областями будет сохранена в сохраненном документе.

#### Вопрос 6. Могу ли я изменить данные и внешний вид диаграммы с областями после ее вставки?
Да, после вставки диаграммы с областями в документ вы можете изменить ее данные и внешний вид с помощью API, предоставляемых Aspose.Words для .NET. Вы можете обновить данные серии, изменить тип диаграммы, настроить свойства оси и применить параметры форматирования для создания динамических и интерактивных диаграмм в документах Word.
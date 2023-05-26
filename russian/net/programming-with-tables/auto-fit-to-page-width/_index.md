---
title: Автоподгонка по ширине страницы
linktitle: Автоподгонка по ширине страницы
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как автоматически подогнать таблицу под ширину страницы в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/auto-fit-to-page-width/
---

В этом руководстве мы узнаем, как использовать Aspose.Words для .NET для автоматического подбора таблицы по ширине страницы в документе Word. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. В конце этого руководства вы сможете программно манипулировать таблицами в документах Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2: Создание и настройка документа
Для начала работы с таблицей нам необходимо создать документ и настроить генератор документов. Следуй этим шагам:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Создайте документ и генератор документов
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов.

## Шаг 3: Вставка и настройка таблицы
Далее мы вставим в документ таблицу шириной, которая занимает половину ширины страницы. Используйте следующий код:

```csharp
// Вставьте таблицу и настройте ее ширину
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

Здесь мы используем конструктор документов, чтобы начать создание таблицы, вставить ячейки и установить предпочтительную ширину таблицы на 50% от ширины страницы. Затем мы добавляем текст в каждую ячейку.

## Шаг 4: Сохранение измененного документа
Наконец, нам нужно сохранить измененный документ с таблицей, адаптированной к ширине страницы. Используйте следующий код:

```csharp
// Сохраните измененный документ
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

Обязательно укажите правильный путь и имя файла для выходного документа.
  
### Пример исходного кода для автоматической подгонки под ширину страницы с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Вставьте таблицу шириной, равной половине ширины страницы.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## Заключение
В этом руководстве мы узнали, как автоматически подогнать таблицу под ширину страницы в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализовав предоставленный код C#, вы сможете управлять таблицами в документах Word программными средствами. Эта функция позволяет динамически адаптировать ширину таблицы в соответствии со страницей, предлагая профессиональный и визуально привлекательный документ.
---
title: Создать нижний колонтитул
linktitle: Создать нижний колонтитул
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как создавать верхние и нижние колонтитулы в документах Word с помощью Aspose.Words для .NET. Настройте верхние и нижние колонтитулы для каждой страницы.
type: docs
weight: 10
url: /ru/net/working-with-headers-and-footers/create-header-footer/
---

Вот пошаговое руководство, объясняющее следующий исходный код C# для создания верхних и нижних колонтитулов с использованием функций Aspose.Words for .NET. Перед использованием этого кода убедитесь, что вы включили библиотеку Aspose.Words в свой проект.

## Шаг 1. Установите путь к каталогу документов

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Обязательно укажите правильный путь к папке с документами, в которой будет сохранен отредактированный документ.

## Шаг 2: Создайте документ и генератор документов

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Здесь мы создаем экземпляр`Document` класс и экземпляр`DocumentBuilder` class, который позволит нам управлять документом и добавлять элементы.

## Шаг 3: Установите параметры страницы и первый заголовок

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// Укажите, хотим ли мы, чтобы верхние/нижние колонтитулы первой страницы отличались от других страниц.
// Вы также можете использовать свойство PageSetup.OddAndEvenPagesHeaderFooter, чтобы указать
// разные верхние/нижние колонтитулы для нечетных и четных страниц.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

Задаем параметры страницы, в том числе расстояние шапки, а затем переходим к основному шапке (`HeaderPrimary`). Мы используем генератор документов, чтобы добавить текст и отформатировать заголовок.

## Шаг 4: Вставьте изображение и текст в основной заголовок

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

Мы используем генератор документов, чтобы вставить изображение в верхний левый угол основного заголовка, затем добавляем текст, выровненный по правому краю.

## Шаг 5: Вставьте таблицу в основной нижний колонтитул

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();
```

## Шаг 6: Добавьте новую страницу и установите верхние/нижние колонтитулы

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
//В этом разделе не нужен другой верхний/нижний колонтитул для первой страницы, нам нужна только одна титульная страница в документе,
// и верхний/нижний колонтитул для этой страницы уже был определен в предыдущем разделе.
pageSetup.DifferentFirstPageHeaderFooter = false;

// В этом разделе по умолчанию отображаются верхние и нижние колонтитулы предыдущего раздела, вызовите currentSection.HeadersFooters.LinkToPrevious(false), чтобы разорвать эту ссылку,
// ширина страницы отличается для нового раздела, поэтому нам нужно установить другую ширину ячеек для таблицы нижнего колонтитула.
currentSection.HeadersFooters.LinkToPrevious(false);

// Если мы хотим использовать уже существующие верхние/нижние колонтитулы для этого раздела,
// но с небольшими изменениями может иметь смысл скопировать верхние/нижние колонтитулы
// из предыдущего раздела и примените необходимые изменения там, где мы этого хотим.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// Сохраните документ
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 Мы добавляем разрыв страницы и разрыв раздела, чтобы создать новую страницу, на которой будут видны основные верхние/нижние колонтитулы. Мы устанавливаем параметры для нового раздела, затем мы используем`CopyHeadersFootersFromPreviousSection`метод для копирования верхних/нижних колонтитулов из предыдущего раздела. Наконец, мы устанавливаем соответствующую ширину ячеек для основной таблицы нижнего колонтитула и сохраняем документ.

### Пример исходного кода для создания верхних и нижних колонтитулов с помощью Aspose.Words для .NET

```csharp
	// Путь к каталогу документов.
	string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	Section currentSection = builder.CurrentSection;
	PageSetup pageSetup = currentSection.PageSetup;
	// Укажите, хотим ли мы, чтобы верхние/нижние колонтитулы первой страницы отличались от других страниц.
	// Вы также можете использовать свойство PageSetup.OddAndEvenPagesHeaderFooter, чтобы указать
	// разные верхние/нижние колонтитулы для нечетных и четных страниц.
	pageSetup.DifferentFirstPageHeaderFooter = true;
	pageSetup.HeaderDistance = 20;

	builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.Font.Size = 14;

	builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

	pageSetup.HeaderDistance = 20;
	builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

	// Вставьте позиционированное изображение в верхний/левый угол заголовка.
	// Расстояние от верхнего/левого края страницы устанавливается равным 10 точкам.
	builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
		RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

	builder.Write("Aspose.Words Header/Footer Creation Primer.");

	builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

	// Мы используем таблицу с двумя ячейками, чтобы сделать одну часть текста на строке (с нумерацией страниц).
	// Выровнять по левому краю, а остальную часть текста (с копирайтом) по правому краю.
	builder.StartTable();

	builder.CellFormat.ClearFormatting();

	builder.InsertCell();

	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

	// Он использует поля PAGE и NUMPAGES для автоматического вычисления текущего номера страницы и количества страниц.
	builder.Write("Page ");
	builder.InsertField("PAGE", "");
	builder.Write(" of ");
	builder.InsertField("NUMPAGES", "");

	builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

	builder.InsertCell();

	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

	builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

	builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

	builder.EndRow();
	builder.EndTable();

	builder.MoveToDocumentEnd();

	// Сделайте разрыв страницы, чтобы создать вторую страницу, на которой будут видны основные верхние/нижние колонтитулы.
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertBreak(BreakType.SectionBreakNewPage);

	currentSection = builder.CurrentSection;
	pageSetup = currentSection.PageSetup;
	pageSetup.Orientation = Orientation.Landscape;
	//Для этого раздела не нужен другой верхний/нижний колонтитул первой страницы, нам нужна только одна титульная страница в документе,
	// и верхний/нижний колонтитул для этой страницы уже был определен в предыдущем разделе.
	pageSetup.DifferentFirstPageHeaderFooter = false;

	// В этом разделе отображаются верхние/нижние колонтитулы из предыдущего раздела.
	// по умолчанию вызовите currentSection.HeadersFooters.LinkToPrevious(false), чтобы отменить эту ширину страницы
	// отличается для нового раздела, и поэтому нам нужно установить разные ширины ячеек для таблицы нижнего колонтитула.
	currentSection.HeadersFooters.LinkToPrevious(false);

	// Если мы хотим использовать уже существующий верхний/нижний колонтитул для этого раздела.
	// Но с небольшими изменениями может быть целесообразно скопировать верхние/нижние колонтитулы
	// из предыдущего раздела и примените необходимые изменения там, где мы этого хотим.
	CopyHeadersFootersFromPreviousSection(currentSection);

	HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

	Row row = primaryFooter.Tables[0].FirstRow;
	row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
	row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

	doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

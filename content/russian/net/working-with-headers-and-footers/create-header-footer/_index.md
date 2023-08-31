---
title: Создать верхний колонтитул
linktitle: Создать верхний колонтитул
second_title: API обработки документов Aspose.Words
description: Узнайте, как создавать верхние и нижние колонтитулы в документах Word с помощью Aspose.Words для .NET. Настройте верхние и нижние колонтитулы для каждой страницы.
type: docs
weight: 10
url: /ru/net/working-with-headers-and-footers/create-header-footer/
---

Вот пошаговое руководство, объясняющее следующий исходный код C# для создания верхних и нижних колонтитулов с использованием функций Aspose.Words для .NET. Прежде чем использовать этот код, убедитесь, что вы включили библиотеку Aspose.Words в свой проект.

## Шаг 1. Установите путь к каталогу документов.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Обязательно укажите правильный путь к каталогу ваших документов, в котором будет сохранен отредактированный документ.

## Шаг 2. Создайте документ и генератор документов.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Здесь мы создаем экземпляр`Document` класс и экземпляр`DocumentBuilder` класс, который позволит нам манипулировать документом и добавлять элементы.

## Шаг 3. Установите параметры страницы и первый заголовок.

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// Укажите, хотим ли мы, чтобы колонтитулы первой страницы отличались от других страниц.
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

Задаем параметры страницы, включая расстояние заголовка, а затем переходим к основному заголовку (`HeaderPrimary`). Мы используем генератор документов для добавления текста и форматирования заголовка.

## Шаг 4. Вставьте изображение и текст в основной заголовок.

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

Мы используем генератор документов, чтобы вставить изображение в верхний левый угол основного заголовка, затем добавляем текст, выровненный по правому краю.

## Шаг 5. Вставьте таблицу в нижний колонтитул.

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

## Шаг 6. Добавьте новую страницу и настройте верхние и нижние колонтитулы.

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Этому разделу не нужен отдельный верхний/нижний колонтитул для первой страницы, нам нужен только один титульный лист в документе.
// а верхний/нижний колонтитул этой страницы уже определен в предыдущем разделе.
pageSetup.DifferentFirstPageHeaderFooter = false;

// В этом разделе по умолчанию отображаются верхние и нижние колонтитулы предыдущего раздела. Чтобы разорвать эту ссылку, вызовите currentSection.HeadersFooters.LinkToPrevious(false),
// ширина страницы в новом разделе разная, поэтому нам нужно установить разную ширину ячеек для таблицы нижнего колонтитула.
currentSection.HeadersFooters.LinkToPrevious(false);

//Если мы хотим использовать уже существующие верхние/нижние колонтитулы для этого раздела,
// но с небольшими изменениями, возможно, имеет смысл скопировать верхние и нижние колонтитулы
// из предыдущего раздела и примените необходимые изменения там, где мы хотим.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// Сохраните документ
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 Мы добавляем разрыв страницы и разрыв раздела, чтобы создать новую страницу, на которой будут видны основные верхние и нижние колонтитулы. Задаем параметры для нового раздела, затем используем`CopyHeadersFootersFromPreviousSection` метод для копирования верхних/нижних колонтитулов из предыдущего раздела. Наконец, мы устанавливаем соответствующую ширину ячеек для основной таблицы нижнего колонтитула и сохраняем документ.

### Пример исходного кода для создания верхних и нижних колонтитулов с помощью Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// Укажите, хотим ли мы, чтобы колонтитулы первой страницы отличались от других страниц.
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
// Расстояние от верхнего/левого края страницы установлено в 10 пунктов.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

//Используем таблицу с двумя ячейками, чтобы вынести одну часть текста на строку (с нумерацией страниц).
// Выровнять по левому краю, а оставшуюся часть текста (с учетом копирайта) по правому краю.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Он использует поля PAGE и NUMPAGES для автоматического расчета номера текущей страницы и множества страниц.
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

// Сделайте разрыв страницы, чтобы создать вторую страницу, на которой будут видны основные верхние и нижние колонтитулы.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Для этого раздела не требуется отдельный верхний/нижний колонтитул на первой странице, нам нужна только одна титульная страница в документе.
// а верхний/нижний колонтитул этой страницы уже определен в предыдущем разделе.
pageSetup.DifferentFirstPageHeaderFooter = false;

// В этом разделе отображаются верхние и нижние колонтитулы из предыдущего раздела.
// по умолчанию вызовите currentSection.HeadersFooters.LinkToPrevious(false), чтобы отменить эту ширину страницы
// для нового раздела отличается, поэтому нам нужно установить разную ширину ячеек для таблицы нижнего колонтитула.
currentSection.HeadersFooters.LinkToPrevious(false);

// Если мы хотим использовать уже существующий набор верхнего/нижнего колонтитула для этого раздела.
// Но с небольшими изменениями, возможно, будет целесообразно скопировать верхние/нижние колонтитулы.
//из предыдущего раздела и примените необходимые изменения там, где мы хотим.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### Часто задаваемые вопросы

#### Вопрос: Как добавить заголовок к документу в Aspose.Words?

 О: Чтобы добавить заголовок в документ в Aspose.Words, вы можете использовать команду`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` метод. Этот метод добавляет основной заголовок в первый раздел вашего документа.

#### Вопрос: Как добавить нижний колонтитул к документу в Aspose.Words?

 О: Чтобы добавить нижний колонтитул к документу в Aspose.Words, вы можете использовать`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)` метод. Этот метод добавляет основной нижний колонтитул в первый раздел вашего документа.

#### Вопрос: Как добавить текст в верхний или нижний колонтитул в Aspose.Words?

 О: Чтобы добавить текст в верхний или нижний колонтитул в Aspose.Words, вы можете использовать`HeaderFooter.Paragraphs` чтобы получить коллекцию абзацев верхнего или нижнего колонтитула, затем добавьте абзац, содержащий ваш текст, в эту коллекцию, используя`ParagraphCollection.Add` метод.

#### Вопрос: Могу ли я настроить содержимое верхнего или нижнего колонтитула с помощью изображений и номеров страниц в Aspose.Words?

О: Да, вы можете настроить содержимое верхнего или нижнего колонтитула с помощью изображений и номеров страниц в Aspose.Words. Вы можете использовать такие объекты, как`Shape` добавлять изображения и объекты, такие как`Field` чтобы добавить номера страниц в верхний или нижний колонтитул.

#### Вопрос: Могу ли я изменить шрифт, размер и цвет текста в верхнем или нижнем колонтитуле в Aspose.Words?

 О: Да, вы можете изменить шрифт, размер и цвет текста в верхнем или нижнем колонтитуле в Aspose.Words. Вы можете получить доступ к свойствам форматирования текста, таким как`Font` изменить шрифт,`Size` отрегулировать размер и`Color` чтобы установить цвет текста.
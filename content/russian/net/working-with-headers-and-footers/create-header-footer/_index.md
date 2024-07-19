---
title: Создать верхний колонтитул
linktitle: Создать верхний колонтитул
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавлять и настраивать верхние и нижние колонтитулы в документах Word с помощью Aspose.Words для .NET. Это пошаговое руководство обеспечивает профессиональное форматирование документов.
type: docs
weight: 10
url: /ru/net/working-with-headers-and-footers/create-header-footer/
---

Добавление верхних и нижних колонтитулов в ваши документы может повысить их профессионализм и читабельность. С помощью Aspose.Words для .NET вы можете легко создавать и настраивать верхние и нижние колонтитулы для своих документов Word. В этом руководстве мы шаг за шагом проведем вас через весь процесс, гарантируя, что вы сможете легко реализовать эти функции.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:

-  Aspose.Words для .NET: загрузите и установите с[ссылка для скачивания](https://releases.aspose.com/words/net/).
- Среда разработки: например, Visual Studio, для написания и запуска вашего кода.
- Базовые знания C#: Понимание C# и .NET framework.
- Образец документа: образец документа для применения верхних и нижних колонтитулов или создания нового, как показано в руководстве.

## Импортировать пространства имен

Во-первых, вам необходимо импортировать необходимые пространства имен для доступа к классам и методам Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System;
```

## Шаг 1. Определите каталог документов

Определите каталог, в котором будет сохранен ваш документ. Это помогает эффективно управлять маршрутом.

```csharp
// Путь к каталогу документов
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

## Шаг 2. Создайте новый документ

 Создайте новый документ и`DocumentBuilder` для облегчения добавления контента.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Настройте параметры страницы

Настройте параметры страницы, в том числе укажите, будет ли на первой странице другой верхний/нижний колонтитул.

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;
```

## Шаг 4. Добавьте заголовок на первую страницу

Перейдите в раздел заголовка первой страницы и настройте текст заголовка.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

## Шаг 5. Добавьте основной заголовок

Перейдите в основной раздел заголовка и вставьте изображение и текст.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Вставьте изображение в шапку
builder.InsertImage(dataDir + "Graphics Interchange Format.gif", 
    RelativeHorizontalPosition.Page, 10, RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Aspose.Words Header/Footer Creation Primer.");
```

## Шаг 6. Добавьте основной нижний колонтитул

Перейдите в основной раздел нижнего колонтитула и создайте таблицу для форматирования содержимого нижнего колонтитула.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

builder.StartTable();
builder.CellFormat.ClearFormatting();
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Добавить нумерацию страниц
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
```

## Шаг 7. Добавьте контент и разрывы страниц

Перейдите в конец документа, добавьте разрыв страницы и создайте новый раздел с другими настройками страницы.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
pageSetup.DifferentFirstPageHeaderFooter = false;

currentSection.HeadersFooters.LinkToPrevious(false);
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];
Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

## Шаг 8. Скопируйте верхние и нижние колонтитулы из предыдущего раздела.

Если вы хотите повторно использовать верхние и нижние колонтитулы из предыдущего раздела, скопируйте их и примените необходимые изменения.

```csharp
private static void CopyHeadersFootersFromPreviousSection(Section section)
{
    Section previousSection = (Section)section.PreviousSibling;
    if (previousSection == null) return;

    section.HeadersFooters.Clear();

    foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    {
        section.HeadersFooters.Add(headerFooter.Clone(true));
    }
}
```

## Заключение

Следуя этим шагам, вы сможете эффективно добавлять и настраивать верхние и нижние колонтитулы в своих документах Word с помощью Aspose.Words для .NET. Это улучшает внешний вид и профессионализм вашего документа, делая его более читабельным и привлекательным.

## Часто задаваемые вопросы

### Вопрос 1. Что такое Aspose.Words для .NET?

Aspose.Words for .NET — это библиотека, которая позволяет разработчикам программно создавать, редактировать и конвертировать документы Word в приложениях .NET.

### В2: Могу ли я добавлять изображения в верхний или нижний колонтитул?

 Да, вы можете легко добавлять изображения в верхний или нижний колонтитул, используя`DocumentBuilder.InsertImage` метод.

### Вопрос 3. Как настроить разные верхние и нижние колонтитулы для первой страницы?

 Вы можете установить разные верхние и нижние колонтитулы для первой страницы, используя`DifferentFirstPageHeaderFooter` собственность`PageSetup` сорт.

### Вопрос 4: Где я могу найти дополнительную документацию по Aspose.Words?

 Вы можете найти подробную документацию на[Страница документации API Aspose.Words](https://reference.aspose.com/words/net/).

### Вопрос 5: Доступна ли поддержка Aspose.Words?

 Да, Aspose предлагает поддержку через свою[форум поддержки](https://forum.aspose.com/c/words/8).

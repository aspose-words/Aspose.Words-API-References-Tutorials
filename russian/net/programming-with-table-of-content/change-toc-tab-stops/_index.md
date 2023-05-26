---
title: Изменить остановки табуляции оглавления
linktitle: Изменить остановки табуляции оглавления
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как изменить вкладки оглавления в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words for .NET — это мощная библиотека для создания, редактирования и управления документами Word в приложении C#. Среди функций, предлагаемых Aspose.Words, есть возможность изменения вкладок, используемых в оглавлении документа Word. В этом руководстве мы покажем вам, как использовать исходный код C# Aspose.Words для .NET для изменения вкладок в оглавлении документа.

## Понимание библиотеки Aspose.Words

Прежде чем погрузиться в код, важно понять библиотеку Aspose.Words для .NET. Aspose.Words — популярная библиотека, которая делает работу с документами Word простой и эффективной. Он предлагает широкий спектр функций для создания, редактирования и управления документами Word, включая изменение вкладок оглавления.

## Загрузка документа, содержащего оглавление

Первый шаг — загрузить документ Word, содержащий оглавление, которое вы хотите изменить. Используйте класс Document для загрузки документа из исходного файла. Вот пример:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

В этом примере мы загружаем документ «Оглавление.docx», расположенный в каталоге документов.

## Изменение вкладок в оглавлении

После загрузки документа мы просматриваем каждый абзац документа и проверяем, отформатирован ли он, используя стили результатов оглавления (TOC). Если это так, мы изменяем вкладки, используемые для выравнивания номеров страниц. Вот как:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

В этом примере мы используем цикл для просмотра каждого абзаца в документе. Затем мы проверяем, отформатирован ли абзац, используя стили результатов оглавления (TOC). Если это так, мы получаем доступ к первой вкладке, используемой в этом абзаце, и изменяем ее, удаляя старую вкладку и добавляя новую вкладку с измененным положением.

## Сохранить измененный документ

После того, как вы внесли необходимые изменения во вкладки в оглавлении, вы можете сохранить измененный документ, используя метод Save класса Document. Вот пример:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

В этом примере мы сохраняем измененный документ как «WorkingWithTableOfContent.ChangeTocTabStops.docx».

### Пример исходного кода для функции «Редактировать вкладки оглавления» с Aspose.Words для .NET

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ, содержащий оглавление
Document doc = new Document(dataDir + "Table of contents.docx");

// Изменить вкладки оглавления
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// Сохраните измененный документ
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Заключение

В этом руководстве мы рассмотрели, как использовать Aspose.Words для .NET для изменения вкладок в оглавлении документа Word, используя предоставленный исходный код C#. Следуя приведенным инструкциям, вы можете легко настроить вкладки оглавления в документах Word в приложении C#. Aspose.Words предлагает невероятную гибкость и мощность для работы со стилями и форматированием ваших документов, позволяя создавать привлекательные и профессиональные документы Word.
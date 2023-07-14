---
title: Перейти к разделу
linktitle: Перейти к разделу
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по использованию функции «Переместить в раздел» в Aspose.Words для .NET для управления разделами и абзацами в документах Word.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/move-to-section/
---

В этом примере мы шаг за шагом покажем вам, как использовать функцию «Переместить в раздел» Aspose.Words для .NET, используя предоставленный исходный код C#. Эта функция позволяет вам перемещаться и управлять различными разделами внутри документа Word. Выполните следующие шаги, чтобы интегрировать эту функцию в ваше приложение.

## Шаг 1. Создайте новый документ и добавьте раздел

Во-первых, нам нужно создать новый документ и добавить в него раздел. Используйте следующий код для выполнения этого шага:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

Этот код создает новый пустой документ и добавляет раздел в этот документ.

## Шаг 2: Переместите DocumentBuilder во второй раздел и добавьте текст

Далее нам нужно переместить DocumentBuilder во второй раздел документа и добавить туда текст. Используйте следующий код для выполнения этого шага:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

Этот код создает DocumentBuilder из существующего документа, затем перемещает курсор из DocumentBuilder во второй раздел документа. Наконец, он добавляет указанный текст в этот раздел.

## Шаг 3. Загрузите документ с существующими абзацами

Если вы хотите работать с существующим документом, содержащим абзацы, вы можете загрузить этот документ, используя следующий код:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

Этот код загружает указанный документ (замените «MyDir +» Paragraphs.docx""с фактическим путем к вашему документу) и получает доступ к коллекции абзацев из первого раздела документа. Линия`Assert.AreEqual(22, paragraphs.Count);` проверяет, что документ содержит 22 абзаца.

## Шаг 4: создайте DocumentBuilder для документа

Вы можете создать курсор DocumentBuilder для определенного абзаца, используя позиционные индексы.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## Шаг 5: Переместите курсор к определенному абзацу


Вы можете переместить курсор DocumentBuilder в определенный абзац, используя позиционные индексы. Вот как это сделать:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Этот код перемещает курсор DocumentBuilder в третий абзац второго раздела (абзац с индексом 2) и в позицию 10. Затем он добавляет новый абзац с некоторым текстом и проверяет правильность положения курсора в этом новом абзаце.

### Пример исходного кода для Move To Move To Section с использованием Aspose.Words для .NET

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// Переместите DocumentBuilder во второй раздел и добавьте текст.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// Создайте документ с абзацами.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

//Когда мы создаем DocumentBuilder для документа, его курсор по умолчанию находится в самом начале документа,
// и любой контент, добавленный DocumentBuilder, будет просто добавлен к документу.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

// Вы можете переместить курсор в любую позицию в абзаце.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Вот и все ! Теперь вы поняли, как использовать функцию перемещения в раздел Aspose.Words для .NET, используя предоставленный исходный код. Теперь вы можете интегрировать эту функцию в свое собственное приложение и динамически управлять разделами и абзацами документов Word.


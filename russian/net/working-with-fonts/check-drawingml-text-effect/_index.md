---
title: Проверьте текстовый эффект DrawingML
linktitle: Проверьте текстовый эффект DrawingML
second_title: Справочник по API Aspose.Words для .NET
description: Из этого руководства вы узнаете, как проверять текстовые эффекты DrawingML в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/check-drawingml-text-effect/
---

В этом руководстве мы расскажем, как проверить текстовые эффекты DrawingML в документе Word с помощью библиотеки Aspose.Words для .NET. Проверка текстовых эффектов DrawingML позволяет определить, применяется ли определенный эффект к части текста. Мы проведем вас шаг за шагом, чтобы помочь вам понять и реализовать код в вашем проекте .NET.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующие предметы:
- Знание языка программирования C# на рабочем уровне
- Библиотека Aspose.Words для .NET, установленная в вашем проекте
- Документ Word, содержащий текстовые эффекты DrawingML

## Шаг 1: Определите каталог документов
 Во-первых, вам нужно указать путь к каталогу, где находится ваш документ Word. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с соответствующим путем.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите документ и проверьте текстовые эффекты.
Затем мы загрузим документ Word и получим доступ к набору серий (последовательностей символов) в первом абзаце тела документа. Далее мы проверим, применяются ли какие-либо определенные текстовые эффекты DrawingML к шрифту первого запуска.

```csharp
//Загрузите документ
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Проверить текстовые эффекты DrawingML
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Пример исходного кода для проверки эффекта DMLText с использованием Aspose.Words для .NET 

```csharp

// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// К одному запуску может быть применено несколько текстовых эффектов Dml.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## Заключение
В этом руководстве мы увидели, как проверить текстовые эффекты DrawingML в документе Word с помощью Aspose.Words для .NET. Проверка текстовых эффектов DrawingML позволяет определить части текста, к которым применены определенные эффекты. Не стесняйтесь использовать эту функцию для управления и анализа текстовых эффектов в ваших документах Word.

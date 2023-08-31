---
title: Огороженный код
linktitle: Огороженный код
second_title: API обработки документов Aspose.Words
description: Узнайте, как использовать функцию изолированного кода с помощью Aspose.Words for .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/fenced-code/
---

В этом примере мы покажем вам, как использовать функцию изолированного кода с Aspose.Words для .NET. изолированный код используется для представления блоков кода с определенным форматированием.

## Шаг 1. Использование генератора документов

Сначала мы воспользуемся генератором документов, чтобы добавить контент в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Шаг 2. Добавление стиля для изолированного кода

 Мы добавим собственный стиль для изолированного кода, используя`Styles.Add` метод`Document` объект. В этом примере мы создаем стиль под названием «FencedCode» для изолированного кода.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Шаг 3. Добавление изолированного кода без информации

Теперь мы можем добавить изолированный блок кода без информационной строки, используя собственный стиль «FencedCode».

```csharp
builder.Writeln("This is an fenced code");
```

## Шаг 4. Добавьте изолированный код с информационной строкой

Мы также можем добавить изолированный блок кода со строкой информации, используя другой собственный стиль. В этом примере мы создаем стиль под названием «FencedCode.C#», который представляет блок кода C#.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Пример исходного кода для Fenced Code с использованием Aspose.Words для .NET

```csharp
// Используйте конструктор документов, чтобы добавить содержимое в документ.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Часто задаваемые вопросы

#### Вопрос: Что такое код с разделителями в Markdown?

Ответ: Код с разделителями в Markdown — это метод форматирования, используемый для отображения кода в документе Markdown. Он состоит из выделения кода определенными разделителями.

#### Вопрос: Каковы преимущества кода с разделителями в Markdown?

Ответ: Код с разделителями в Markdown улучшает читаемость кода и облегчает его понимание читателями. Это также позволяет сохранить подсветку синтаксиса в некоторых редакторах Markdown.

#### Вопрос: В чем разница между кодом с разделителями и отступом в Markdown?

О: В коде с разделителями для заключения кода используются специальные разделители, а в коде с отступом каждая строка кода включается с помощью пробелов или табуляции.

#### Вопрос: Поддерживается ли код с разделителями в Markdown всеми редакторами Markdown?

О: Поддержка кода с разделителями в Markdown может различаться в разных редакторах Markdown. Чтобы быть уверенным, проверьте документацию вашего издателя.


---
title: Цитировать
linktitle: Цитировать
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как использовать цитату с Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/quote/
---

В этом примере мы объясним, как использовать функцию кавычек с Aspose.Words for .NET Quote используются для выделения фрагментов текста, окружая их специальной рамкой.

## Шаг 1: Использование генератора документов

Во-первых, мы будем использовать генератор документов, чтобы добавить содержимое в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Шаг 2. Использование стиля цитирования по умолчанию

Мы будем использовать стиль абзаца по умолчанию под названием «Цитата», чтобы применить форматирование цитаты к тексту.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Шаг 3: Создание стилей для вложенных уровней

 Мы можем создавать стили для вложенных уровней, используя`Styles.Add` метод`Document` объект. В этом примере мы создаем стиль под названием «Quote1» для представления уровня вложенных котировок.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Пример исходного кода для цитат с помощью Aspose.Words для .NET


```csharp
// Используйте конструктор документов, чтобы добавить содержимое в документ.
DocumentBuilder builder = new DocumentBuilder();

// По умолчанию документ сохраняет стиль цитаты для первого уровня.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Создавайте стили для вложенных уровней посредством наследования стилей.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

Поздравляем! Теперь вы узнали, как использовать функцию цитирования в Aspose.Words для .NET.


### Часто задаваемые вопросы

#### В: Что такое цитата в Markdown?

О: Цитата в Markdown — это способ выделить фрагменты текста из других источников или сослаться на известные цитаты.

#### Q: Как использовать кавычки в Markdown?

О: Чтобы использовать цитату в Markdown, заключите текст цитаты в угловые скобки (`>`). Каждая строка цитаты должна начинаться с шеврона.

#### В: Поддерживают ли котировки Markdown атрибуты?

О: Цитаты с уценкой не поддерживают определенные атрибуты. Они просто выделяются форматированием цитируемого текста.

#### В: Можно ли вставлять цитаты в Markdown?

О: Да, в Markdown можно вкладывать кавычки, добавляя дополнительный уровень угловых скобок (`>`).
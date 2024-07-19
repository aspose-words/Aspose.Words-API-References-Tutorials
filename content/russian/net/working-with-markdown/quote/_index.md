---
title: Цитировать
linktitle: Цитировать
second_title: API обработки документов Aspose.Words
description: Узнайте, как использовать цитату с Aspose.Words for .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/quote/
---

В этом примере мы объясним, как использовать функцию кавычек с Aspose. Words for .NET Quote используются для выделения разделов текста путем окружения их специальной рамкой.

## Шаг 1. Использование генератора документов

Сначала мы воспользуемся генератором документов, чтобы добавить контент в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Шаг 2. Использование стиля цитирования по умолчанию

Мы будем использовать стиль абзаца по умолчанию под названием «Цитата», чтобы применить к тексту форматирование кавычек.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Шаг 3. Создание стилей для вложенных уровней

 Мы можем создавать стили для вложенных уровней, используя команду`Styles.Add` метод`Document`объект. В этом примере мы создаем стиль под названием «Quote1», который представляет собой вложенный уровень котировок.

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

// По умолчанию в документе сохраняется стиль блочных цитат первого уровня.
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

#### Вопрос: Что такое цитата в Markdown?

О: Цитата в Markdown — это способ выделить отрывки текста из других источников или сослаться на известные цитаты.

#### Вопрос: Как использовать кавычки в Markdown?

О: Чтобы использовать цитату в Markdown, заключите текст цитаты в угловые скобки (`>`). Каждая строка цитаты должна начинаться с шеврона.

#### Вопрос: Поддерживают ли котировки Markdown атрибуты?

О: Цитаты Markdown не поддерживают определенные атрибуты. Они просто выделяются форматированием цитируемого текста.

#### Вопрос: Можно ли вставлять кавычки в Markdown?

О: Да, в Markdown можно вкладывать кавычки, добавляя дополнительный уровень угловых скобок (`>`).
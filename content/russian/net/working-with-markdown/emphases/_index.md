---
title: Акценты
linktitle: Акценты
second_title: API обработки документов Aspose.Words
description: Узнайте, как использовать выделение (жирный шрифт и курсив) в Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/emphases/
---

В этом примере мы объясним, как использовать акценты с Aspose.Words для .NET. Акценты используются для выделения определенных частей текста, таких как полужирный шрифт и курсив.

## Шаг 1: Инициализация документа

 Во-первых, мы инициализируем документ, создав экземпляр`Document` сорт.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Шаг 2: Использование генератора документов

Далее мы будем использовать генератор документов, чтобы добавить содержимое в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3: Добавьте текст с акцентами

Мы можем добавить выделенный текст, изменив свойства шрифта генератора документов. В этом примере мы используем жирный шрифт и курсив, чтобы выделить разные части текста.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## Шаг 4: Сохранение документа

 Наконец, мы можем сохранить документ в нужном формате. В этом примере мы используем`.md` расширение для формата Markdown.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Поздравляем! Теперь вы узнали, как использовать акценты с Aspose.Words для .NET.

### Пример исходного кода для Emphases с использованием Aspose.Words для .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### Часто задаваемые вопросы

#### В: Как выделить текст с помощью Markdown?

О: Чтобы выделить текст с помощью Markdown, просто окружите текст соответствующими символами. Использовать`*` или`_` для курсива,`**` или`__` для смелых и`~~` для зачеркивания.

#### В: Можно ли совмещать разные выделения в одном тексте?

 О: Да, в одном тексте можно сочетать разные выделения. Например, вы можете выделить слово жирным шрифтом и курсивом, используя оба`**` и`*` вокруг слова.

#### В: Какие параметры выделения доступны в Markdown?

A: Параметры выделения, доступные в Markdown, выделены курсивом (`*` или`_`), смелый (`**` или`__`) и зачеркнуть (`~~`).

#### В: Как поступить в случаях, когда текст содержит специальные символы, используемые Markdown для выделения?

 О: Если ваш текст содержит специальные символы, используемые Markdown для выделения, вы можете избежать их, поставив перед ними символ`\` . Например,`\*` будет отображаться буквальная звездочка.

#### В: Можем ли мы настроить внешний вид выделения с помощью CSS?

A: Выделение в Markdown обычно отображается с использованием стилей браузера по умолчанию. Если вы конвертируете Markdown в HTML, вы можете настроить внешний вид выделения с помощью правил CSS.
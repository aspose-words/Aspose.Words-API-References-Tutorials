---
title: Акценты
linktitle: Акценты
second_title: API обработки документов Aspose.Words
description: Узнайте, как использовать выделения (жирный и курсив) в Aspose.Words for .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/emphases/
---

В этом примере мы объясним, как использовать акценты в Aspose.Words для .NET. Акцентирование используется для выделения определенных частей текста, например, жирного шрифта и курсива.

## Шаг 1. Инициализация документа

 Сначала мы инициализируем документ, создав экземпляр`Document` сорт.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Шаг 2. Использование генератора документов

Далее мы воспользуемся генератором документов, чтобы добавить контент в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Добавьте текст с акцентами

Мы можем добавить акцентный текст, изменив свойства шрифта генератора документов. В этом примере мы используем жирный шрифт и курсив, чтобы выделить разные части текста.

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

Поздравляем! Теперь вы узнали, как использовать акценты в Aspose.Words для .NET.

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

#### Вопрос: Как выделить текст с помощью Markdown?

 О: Чтобы выделить текст с помощью Markdown, просто окружите его соответствующими символами. Использовать`*` или`_` для курсива,`**` или`__` для смелых и`~~` для зачеркивания.

#### Вопрос: Можем ли мы объединить разные моменты в одном тексте?

 О: Да, в одном тексте можно комбинировать разные выделения. Например, вы можете выделить слово жирным шрифтом и курсивом, используя оба`**` и`*`вокруг слова.

#### Вопрос: Какие параметры выделения доступны в Markdown?

О: Параметры выделения, доступные в Markdown, выделены курсивом (`*` или`_`), смелый (`**` или`__`) и зачеркивание (`~~`).

#### Вопрос: Как действовать в случаях, когда текст содержит специальные символы, используемые Markdown для выделения?

 О: Если ваш текст содержит специальные символы, используемые Markdown для выделения, вы можете экранировать их, поставив перед ними знак.`\` . Например,`\*` отобразит буквальную звездочку.

#### Вопрос: Можем ли мы настроить внешний вид подсветки с помощью CSS?

О: Выделение в Markdown обычно отображается с использованием стилей браузера по умолчанию. Если вы конвертируете Markdown в HTML, вы можете настроить внешний вид выделения с помощью правил CSS.
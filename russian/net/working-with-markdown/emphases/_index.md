---
title: Акценты
linktitle: Акценты
second_title: Справочник по API Aspose.Words для .NET
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

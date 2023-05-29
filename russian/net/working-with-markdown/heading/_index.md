---
title: Заголовок
linktitle: Заголовок
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как использовать заголовок с Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/heading/
---

В этом примере мы собираемся показать вам, как использовать функцию заголовков с Aspose.Words для .NET. Заголовки используются для структурирования и определения приоритетности содержания документа.

## Шаг 1: Использование генератора документов

Во-первых, мы будем использовать генератор документов, чтобы добавить содержимое в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Шаг 2. Настройка стилей заголовков

По умолчанию стили заголовков в Word могут быть выделены полужирным шрифтом и курсивом. Если мы не хотим, чтобы эти свойства применялись, нам нужно явно установить для них значение «false».

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Шаг 3: Добавление заголовка уровня 1

 Мы можем добавить заголовок уровня 1, указав соответствующее имя стиля абзаца и используя`Writeln` способ написать содержание заголовка.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

### Пример исходного кода для заголовка с Aspose.Words для .NET


```csharp
// Используйте конструктор документов, чтобы добавить содержимое в документ.
DocumentBuilder builder = new DocumentBuilder();

// По умолчанию стили заголовков в Word могут иметь форматирование жирным шрифтом и курсивом.
//Если мы не хотим, чтобы нас подчеркивали, явно установите для этих свойств значение false.
builder.Font.Bold = false;
builder.Font.Italic = false;

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

Поздравляем! Теперь вы узнали, как использовать функцию заголовков с Aspose.Words для .NET.



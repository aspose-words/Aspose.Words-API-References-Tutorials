---
title: Заголовок сетекста
linktitle: Заголовок сетекста
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как использовать заголовки Setext для форматирования документов с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/setext-heading/
---

В этом руководстве мы расскажем вам, как использовать функцию заголовка Setext с Aspose.Words для .NET. Setext Heading — это альтернативный метод форматирования заголовков в документах Markdown.

## Шаг 1: Использование генератора документов

Во-первых, мы будем использовать генератор документов, чтобы добавить содержимое в наш документ.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Шаг 2. Использование стиля заголовка Setext

Мы собираемся использовать стиль абзаца по умолчанию «Заголовок 1», чтобы создать заголовок уровня 1 в нашем документе.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Шаг 3: Сброс стилей

Мы сбрасываем ранее примененные стили шрифтов, чтобы избежать нежелательных комбинаций стилей между абзацами.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Шаг 4: Настройка уровней заголовков Setext

Мы можем настроить уровни заголовков Setext, добавив новые стили абзаца на основе существующих стилей заголовков. В этом примере мы создаем стиль «SetextHeading1» на основе стиля «Заголовок 1» для представления заголовка уровня 1 в формате Setext.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Шаг 5: Сохранение документа

Наконец, мы можем сохранить документ в нужном формате.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Пример исходного кода для заголовков Setext с Aspose.Words для .NET

```csharp
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Используйте конструктор документов, чтобы добавить содержимое в документ.
	DocumentBuilder builder = new DocumentBuilder();

	builder.ParagraphFormat.StyleName = "Heading 1";
	builder.Writeln("This is an H1 tag");

	// Сбросить стили из предыдущего абзаца, чтобы не комбинировать стили между абзацами.
	builder.Font.Bold = false;
	builder.Font.Italic = false;

	Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
	builder.ParagraphFormat.Style = setexHeading1;
	builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
	builder.Writeln("Setext Heading level 1");

	builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
	builder.Writeln("This is an H3 tag");

	// Сбросить стили из предыдущего абзаца, чтобы не комбинировать стили между абзацами.
	builder.Font.Bold = false;
	builder.Font.Italic = false;

	Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
	builder.ParagraphFormat.Style = setexHeading2;
	builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

	// Уровень заголовка Setex будет сброшен на 2, если базовый абзац имеет уровень заголовка выше 2.
	builder.Writeln("Setext Heading level 2");
	

	builder.Document.Save(dataDir + "Test.md");
```




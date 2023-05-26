---
title: Код с отступом
linktitle: Код с отступом
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как использовать код с отступом в Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/indented-code/
---

В этом примере мы объясним, как использовать функцию кода с отступом в Aspose.Words для .NET. Код с отступом используется для визуального представления блоков кода с определенным форматированием.

## Шаг 1: Использование генератора документов

Во-первых, мы будем использовать генератор документов, чтобы добавить содержимое в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Шаг 2. Добавьте стиль для кода с отступом

 Мы добавим собственный стиль для кода с отступом, используя`Styles.Add` метод`Document` объект. В этом примере мы создаем стиль под названием «IndentedCode» для кода с отступом.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Шаг 3. Добавьте код с отступом

Теперь мы можем добавить блок кода с отступом, используя собственный стиль «IndentedCode».

```csharp
builder.Writeln("This is an indented code block");
```

### Пример исходного кода для кода с отступом в Aspose.Words для .NET

```csharp
	// Используйте конструктор документов, чтобы добавить содержимое в документ.
	DocumentBuilder builder = new DocumentBuilder();

	Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
	builder.ParagraphFormat.Style = indentedCode;
	builder.Writeln("This is an indented code");
            
```

Поздравляем! Теперь вы узнали, как использовать функцию кода с отступом в Aspose.Words для .NET.


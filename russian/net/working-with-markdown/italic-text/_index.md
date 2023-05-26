---
title: Курсив
linktitle: Курсив
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как выделить текст курсивом с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/italic-text/
---

В этом примере мы покажем вам, как использовать функцию курсивного текста с Aspose.Words для .NET. Курсив используется для выделения определенных частей документа.

## Шаг 1: Использование генератора документов

Во-первых, мы будем использовать генератор документов, чтобы добавить содержимое в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Шаг 2. Выделите текст курсивом

 Мы можем выделить текст курсивом, установив для шрифта`Italic` собственность на`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### Пример исходного кода для курсивного текста с Aspose.Words для .NET


```csharp
	// Используйте конструктор документов, чтобы добавить содержимое в документ.
	DocumentBuilder builder = new DocumentBuilder();

	// Сделайте текст курсивом.
	builder.Font.Italic = true;
	builder.Writeln("This text will be Italic");
            
```

Поздравляем! Теперь вы узнали, как использовать функцию курсивного текста с Aspose.Words для .NET.


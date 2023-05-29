---
title: Зачеркнутый
linktitle: Зачеркнутый
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как применить стиль перечеркнутого текста с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/strikethrough/
---


В этом примере мы покажем вам, как применить стиль перечеркнутого текста с помощью Aspose.Words для .NET. Зачеркнутый текст используется для обозначения того, что текст удален или более недействителен.

## Шаг 1: Использование генератора документов

Во-первых, мы будем использовать генератор документов, чтобы добавить содержимое в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Шаг 2. Примените стиль зачеркнутого текста

 Мы включим стиль зачеркнутого текста, установив`StrikeThrough` собственность`Font` Возражать`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Шаг 3. Добавьте зачеркнутый текст

 Теперь мы можем добавить зачеркнутый текст, используя инструмент генератора документов.`Writeln` метод.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Пример исходного кода для перечеркнутого текста с помощью Aspose.Words для .NET

```csharp
// Используйте конструктор документов, чтобы добавить содержимое в документ.
DocumentBuilder builder = new DocumentBuilder();

// Сделайте текст зачеркнутым.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

Поздравляем! Теперь вы узнали, как применить стиль перечеркнутого текста с помощью Aspose.Words для .NET.

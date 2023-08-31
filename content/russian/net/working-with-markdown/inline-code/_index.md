---
title: Встроенный код
linktitle: Встроенный код
second_title: API обработки документов Aspose.Words
description: Узнайте, как встроить код с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/inline-code/
---

В этом примере мы покажем вам, как использовать функцию встроенного кода в Aspose.Words для .NET. Встроенный код используется для визуального представления фрагментов кода внутри абзаца.

## Шаг 1. Использование генератора документов

Сначала мы воспользуемся генератором документов, чтобы добавить контент в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Шаг 2. Добавьте стиль для встроенного кода

 Мы добавим собственный стиль для встроенного кода, используя`Styles.Add` метод`Document` объект. В этом примере мы создаем стиль InlineCode для встроенного кода с обратной кавычкой по умолчанию.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Шаг 3. Добавьте встроенный код

Теперь мы можем добавить встроенный код, используя собственный стиль «InlineCode». В этом примере мы добавляем два фрагмента текста с разным количеством обратных кавычек.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Пример исходного кода для встроенного кода с помощью Aspose.Words для .NET

```csharp
// Используйте конструктор документов, чтобы добавить содержимое в документ.
DocumentBuilder builder = new DocumentBuilder();

// Количество обратных кавычек пропущено, по умолчанию будет использоваться один обратный кавычек.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// Будет 3 обратных кавычки.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

Поздравляем! Теперь вы узнали, как использовать встроенный код в Aspose.Words для .NET.


### Часто задаваемые вопросы

#### Вопрос: Как я могу использовать встроенный код в Aspose.Words?

 О: Чтобы использовать встроенный код в Aspose.Words, вы можете использовать соответствующие теги для окружения текста, который будет отформатирован как встроенный код. Например, вы можете использовать`<code>` или`<kbd>` тег для окружения текста, который будет отформатирован как встроенный код.

#### Вопрос: Можно ли указать шрифт или цвет встроенного кода в Aspose.Words?

 О: Да, вы можете указать шрифт или цвет встроенного кода в Aspose.Words. Вы можете использовать`Font.Name` и`Font.Color` свойства`Run` объект для установки шрифта и цвета встроенного кода. Например, вы можете использовать`run.Font.Name = "Courier New"` чтобы указать шрифт для встроенного кода и`run.Font.Color = Color.Blue`чтобы указать цвет.

#### Вопрос: Могу ли я использовать встроенный код в абзаце, содержащем другие текстовые элементы?

 О: Да, вы можете использовать встроенный код в абзаце, содержащем другие текстовые элементы. Вы можете создать несколько`Run` объекты для представления различных частей абзаца, а затем используйте теги встроенного кода для форматирования только определенных частей как встроенный код. Затем вы можете добавить их в абзац, используя`Paragraph.AppendChild(run)` метод.
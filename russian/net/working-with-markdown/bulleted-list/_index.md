---
title: Маркированный список
linktitle: Маркированный список
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как создать маркированный список с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/bulleted-list/
---

В этом уроке мы расскажем вам, как создать маркированный список с помощью Aspose.Words для .NET. Маркированный список используется для перечисления элементов без использования нумерации.

## Шаг 1: Использование генератора документов

Во-первых, мы будем использовать генератор документов, чтобы добавить содержимое в наш документ.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Шаг 2. Применение маркированного списка по умолчанию

 Мы можем применить маркированный список по умолчанию, используя конструктор документов.`ApplyBulletDefault` метод.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Шаг 3: Настройка формата маркера

 Мы можем настроить формат маркера, обратившись к свойствам`ListFormat.List.ListLevels[0]`. В этом примере мы используем тире «-» в качестве маркера.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Шаг 4: Добавление элементов в список

 Теперь мы можем добавлять элементы в маркированный список с помощью конструктора документов.`Writeln` метод.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Шаг 5: Удаление отступа из списка

 Если мы хотим создать подсписок, мы можем увеличить отступ, используя`ListFormat.ListIndent()` метод. В этом примере мы добавляем подсписок к элементам 2a и 2b.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Пример исходного кода для маркированного списка с использованием Aspose.Words для .NET


```csharp
// Используйте конструктор документов, чтобы добавить содержимое в документ.
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Поздравляем! Теперь вы узнали, как создать маркированный список с помощью Aspose.Words для .NET.


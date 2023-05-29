---
title: Упорядоченный список
linktitle: Упорядоченный список
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как создать упорядоченный список с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/working-with-markdown/ordered-list/
---

В этом примере мы объясним, как использовать функциональность упорядоченного списка с Aspose.Words для .NET. Упорядоченный список позволяет упорядочивать элементы последовательно с номерами.

## Шаг 1: Использование генератора документов

Во-первых, мы будем использовать генератор документов для создания нового документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Применение формата упорядоченного списка

Мы применим формат упорядоченного списка, используя конструктор документов.`ApplyBulletDefault` метод. Мы также можем настроить формат нумерации, перейдя на уровни списка и установив нужный формат.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Шаг 3: Добавление элементов в список

 Мы можем добавлять элементы в список, используя генератор документов`Writeln` метод.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Шаг 4: Сделайте отступ в списке

 Мы можем сделать отступ в списке, используя генератор документов`ListIndent` метод.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Шаг 5: Сохранение документа

Наконец, мы можем сохранить документ в нужном формате.

### Пример исходного кода для упорядоченного списка с Aspose.Words для .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Поздравляем! Теперь вы узнали, как использовать функцию упорядоченного списка с Aspose.Words для .NET.


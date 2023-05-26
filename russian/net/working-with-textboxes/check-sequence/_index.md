---
title: Проверить последовательность
linktitle: Проверить последовательность
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как проверить последовательность текстовых полей в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-textboxes/check-sequence/
---

## Шаг 1. Настройка документа и создание формы TextBox

 Для начала нам нужно настроить документ и создать фигуру TextBox. Следующий код инициализирует новый экземпляр класса`Document` класс и создает форму текстового поля:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Шаг 2. Проверка последовательности TextBox

 Теперь мы проверим последовательность TextBox, используя`if` условия. Предоставленный исходный код содержит три отдельных условия для проверки положения TextBox относительно предшествующей и последующей фигур.

## Шаг 3: Проверка заголовка последовательности:

```csharp
if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}
```

Если TextBox имеет следующую форму (`Next`), но без предыдущей формы (`Previous`), это означает, что это голова последовательности. Появится сообщение «Начало последовательности».

## Шаг 4: Проверка середины последовательности:

```csharp
if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}
```

Если TextBox имеет форму Next (`Next`) и Предыдущая фигура (`Previous`), это указывает на то, что он находится в середине последовательности. Появится сообщение «Середина последовательности».

## Шаг 5: Проверка конца последовательности:

```csharp
if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

Если TextBox не имеет следующей формы (`Next`), но имеет прежнюю форму (`Previous`), это означает, что это конец последовательности. Появится сообщение «Конец последовательности».

### Пример исходного кода для проверки последовательности с помощью Aspose.Words для .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}

if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}

if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```
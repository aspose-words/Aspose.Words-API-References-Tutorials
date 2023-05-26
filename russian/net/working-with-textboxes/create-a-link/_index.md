---
title: Создать ссылку
linktitle: Создать ссылку
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как создать связь между текстовыми полями в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-textboxes/create-a-link/
---

## Шаг 1. Настройка документа и создание фигур TextBox

 Для начала нам нужно настроить документ и создать две фигуры TextBox. Следующий код инициализирует новый экземпляр класса`Document` class и создает две формы текстового поля:

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;
```

## Шаг 2: Создание ссылки между текстовыми полями

 Теперь мы создадим связь между двумя текстовыми полями, используя`IsValidLinkTarget()` метод и`Next` свойство первого TextBox.

```csharp
if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```

`IsValidLinkTarget()` Метод проверяет, может ли второй TextBox быть допустимой целью для ссылки первого TextBox. Если проверка прошла успешно,`Next` Свойство первого TextBox устанавливается на второе TextBox, создавая связь между ними.

### Пример исходного кода для связи с Aspose.Words для .NET

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;

if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```
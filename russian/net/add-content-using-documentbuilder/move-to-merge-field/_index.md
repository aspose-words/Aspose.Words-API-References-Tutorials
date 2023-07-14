---
title: Переместить в поле слияния
linktitle: Переместить в поле слияния
second_title: API обработки документов Aspose.Words
description: Узнайте, как реализовать функцию «Переместить в поле слияния» в Aspose.Words для .NET, используя пошаговое руководство.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/move-to-merge-field/
---

В этом примере мы рассмотрим функцию «Переместить в поле слияния» Aspose.Words для .NET. Aspose.Words — это мощная библиотека для работы с документами, которая позволяет разработчикам программно создавать, изменять и преобразовывать документы Word. Функция «Переместить в поле слияния» позволяет нам переходить к полям слияния в документе и выполнять с ними различные операции.


## Пошаговое объяснение исходного кода

Давайте шаг за шагом рассмотрим исходный код, чтобы понять, как использовать функцию «Переместить в поле слияния» с помощью Aspose.Words для .NET.

## Шаг 1: Инициализация документа и построителя документов

Сначала инициализируйте объекты Document и DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2 Вставка поля слияния и добавление текста после него

Используйте метод InsertField класса DocumentBuilder, чтобы вставить поле слияния, а затем добавить текст после него:

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## Шаг 3: Курсор построителя в настоящее время находится в конце документа.

```csharp
Assert.Null(builder.CurrentNode);
```
## Шаг 4: Перемещение курсора конструктора документов в поле слияния

Чтобы переместить курсор конструктора документов в поле слияния, используйте метод MoveToField класса DocumentBuilder:

```csharp
builder.MoveToField(field, true);
```

## Добавление текста сразу после поля слияния

Как только курсор построителя документа окажется внутри поля слияния, вы можете добавить текст сразу после него с помощью метода Write:

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Пример исходного кода для перемещения в поле слияния с использованием Aspose.Words для .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставьте поле с помощью DocumentBuilder и добавьте текст после него.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// Курсор построителя в настоящее время находится в конце документа.
Assert.Null(builder.CurrentNode);
// Мы можем переместить конструктор в такое поле, поместив курсор сразу после поля.
builder.MoveToField(field, true);

// Обратите внимание, что курсор находится за узлом FieldEnd поля, что означает, что мы фактически не находимся внутри поля.
// Если мы хотим переместить DocumentBuilder внутрь поля,
// нам нужно будет переместить его в узел FieldStart или FieldSeparator поля, используя метод DocumentBuilder.MoveTo().
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## Заключение

мы изучили функцию «Переместить в поле слияния» в Aspose.Words для .NET. Мы узнали, как переходить к полям слияния в документе с помощью класса DocumentBuilder и выполнять над ними операции. Эта функция полезна при программной обработке слов со слиянием.


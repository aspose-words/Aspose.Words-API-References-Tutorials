---
title: Переместить в начало документа
linktitle: Переместить в начало документа
second_title: Справочник по API Aspose.Words для .NET
description: Из этого пошагового руководства вы узнаете, как использовать Aspose.Words для .NET для перехода к началу и концу документа в документах Word.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/move-to-document-start-end/
---

В этом примере мы рассмотрим функцию «Переместить в начало/конец документа» в Aspose.Words для .NET. Aspose.Words — это мощная библиотека для работы с документами, которая позволяет разработчикам программно создавать, изменять и преобразовывать документы Word. Функция «Переместить в начало/конец документа» позволяет нам перейти к началу или концу документа с помощью класса DocumentBuilder.

## Пошаговое объяснение исходного кода

Давайте шаг за шагом рассмотрим исходный код, чтобы понять, как использовать функцию «Переместить в начало/конец документа» с помощью Aspose.Words для .NET.


## Шаг 1: Инициализация документа и построителя документов

Затем инициализируйте объекты Document и DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2: Переход к началу документа

Чтобы переместить позицию курсора в начало документа, используйте метод MoveToDocumentStart класса DocumentBuilder:

```csharp
builder.MoveToDocumentStart();
```

## Шаг 3: Переход к концу документа

Чтобы переместить позицию курсора в конец документа, используйте метод MoveToDocumentEnd класса DocumentBuilder:

```csharp
builder.MoveToDocumentEnd();
```

## Шаг 4: Вывод позиции курсора

Вы можете вывести позицию курсора, используя Console.WriteLine или любой другой желаемый метод. Например:

```csharp
Console.WriteLine("\nThis is the beginning of the document.");
Console.WriteLine("\nThis is the end of the document.");
```

### Пример исходного кода для перемещения в начало/конец документа с использованием Aspose.Words для .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Переместите курсор в начало документа.
builder.MoveToDocumentStart();
Console.WriteLine("\nThis is the beginning of the document.");

// Переместите курсор в конец документа.
builder.MoveToDocumentEnd();
Console.WriteLine("\nThis is the end of the document.");
```

## Заключение

В этом примере мы рассмотрели функцию «Переместить в начало/конец документа» в Aspose.Words для .NET. Мы научились переходить к началу и концу документа с помощью класса DocumentBuilder. Эта функция полезна при программной работе с документами Word и необходимости манипулировать содержимым или вставлять его в определенные позиции в документе.
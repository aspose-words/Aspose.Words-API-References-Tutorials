---
title: Перейти к верхним колонтитулам
linktitle: Перейти к верхним колонтитулам
second_title: API обработки документов Aspose.Words
description: Узнайте, как использовать Aspose.Words для .NET для навигации и изменения верхних и нижних колонтитулов в документах Word с помощью этого пошагового руководства.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/move-to-headers-footers/
---

В этом примере мы рассмотрим функцию «Переместить в нижние колонтитулы» в Aspose.Words для .NET. Aspose.Words — это мощная библиотека для работы с документами, которая позволяет разработчикам программно создавать, изменять и преобразовывать документы Word. Функция «Переместить в верхние/нижние колонтитулы» позволяет нам переходить к различным верхним и нижним колонтитулам в документе и добавлять к ним контент.

Давайте шаг за шагом рассмотрим исходный код, чтобы понять, как использовать функцию «Переместить в верхние/нижние колонтитулы» с помощью Aspose.Words для .NET.



## Шаг 1: Инициализация документа и построителя документов

Сначала инициализируйте объекты Document и DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Настройка верхних и нижних колонтитулов

Укажите параметры верхнего/нижнего колонтитула для документа. В этом примере мы установили разные верхние и нижние колонтитулы для первой страницы и для нечетных/четных страниц:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## Шаг 3: Создание заголовков для разных страниц

Перейдите к каждому типу заголовков и добавьте к ним контент. В этом примере мы создаем заголовки для первой страницы, четных страниц и всех остальных страниц:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## Шаг 4: Создание страниц в документе
Добавьте содержимое в документ, чтобы создать несколько страниц. Например:

```csharp
// Создайте две страницы в документе.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## Шаг 5: Сохранение документа

Сохраните измененный документ в нужном месте:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

Обязательно укажите правильный путь к файлу и формат (например, DOCX).

### Пример исходного кода для перемещения в верхние/нижние колонтитулы с использованием Aspose.Words для .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Укажите, что мы хотим, чтобы верхние и нижние колонтитулы были разными для первой, четной и нечетной страниц.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Создайте заголовки.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// Создайте две страницы в документе.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

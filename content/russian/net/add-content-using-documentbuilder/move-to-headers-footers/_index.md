---
title: Переместить в верхние нижние колонтитулы в документе Word
linktitle: Переместить в верхние нижние колонтитулы в документе Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как использовать Aspose.Words для .NET для навигации и изменения верхних и нижних колонтитулов в документах Word, с помощью этого пошагового руководства.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/move-to-headers-footers/
---
В этом примере мы рассмотрим функцию «Переместить в нижние колонтитулы» Aspose.Words для .NET. Aspose.Words — это мощная библиотека для работы с документами, которая позволяет разработчикам программно создавать, изменять и конвертировать документы Word. Функция «Переместить в верхние и нижние колонтитулы» позволяет нам переходить к различным верхним и нижним колонтитулам в документе и добавлять к ним контент.

Давайте шаг за шагом рассмотрим исходный код, чтобы понять, как использовать функцию «Переместить в верхние/нижние колонтитулы» с помощью Aspose.Words для .NET.

## Шаг 1. Инициализация документа и построителя документов

Сначала инициализируйте объекты Document и DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Настройка верхних и нижних колонтитулов

Укажите настройки верхнего и нижнего колонтитула документа. В этом примере мы установили разные верхние и нижние колонтитулы для первой страницы и для нечетных/четных страниц:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## Шаг 3. Создание заголовков для разных страниц

Перейдите к каждому типу заголовков и добавьте к ним контент. В этом примере мы создаем заголовки для первой страницы, четных страниц и всех остальных страниц:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## Шаг 4. Создание страниц в документе
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

Обязательно укажите соответствующий путь и формат файла (например, DOCX).

### Пример исходного кода для перемещения в верхние/нижние колонтитулы с использованием Aspose.Words для .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//Укажите, что мы хотим, чтобы верхние и нижние колонтитулы были разными для первой, четной и нечетной страниц.
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

## Заключение

В этом примере мы исследовали функцию «Переместить в верхние/нижние колонтитулы» Aspose.Words для .NET. Мы узнали, как перемещаться по различным верхним и нижним колонтитулам в документе Word и добавлять к ним контент с помощью класса DocumentBuilder. Эта функция позволяет разработчикам настраивать верхние и нижние колонтитулы для определенных страниц или разделов, обеспечивая гибкость при создании профессиональных и структурированных документов. Aspose.Words for .NET предоставляет мощный набор инструментов для программного управления документами Word, что делает его незаменимой библиотекой для приложений обработки документов.

### Часто задаваемые вопросы по переходу к верхним и нижним колонтитулам в документе Word

#### Вопрос: Какова цель функции «Переместить в верхние/нижние колонтитулы» в Aspose.Words для .NET?

О: Функция «Переместить к верхним и нижним колонтитулам» в Aspose.Words for .NET позволяет разработчикам переходить к различным верхним и нижним колонтитулам в документе Word и добавлять к ним контент программным способом. Это полезно, когда вам нужно настроить верхние и нижние колонтитулы для разных страниц или разделов документа.

#### Вопрос: Могу ли я использовать разные верхние и нижние колонтитулы для разных страниц документа?

О: Да, вы можете указать разные верхние и нижние колонтитулы для первой, четных и нечетных страниц, используя свойства PageSetup.DifferentFirstPageHeaderFooter и PageSetup.OddAndEvenPagesHeaderFooter соответственно.

#### Вопрос: Как добавить контент в определенные верхние и нижние колонтитулы?

О. Чтобы добавить содержимое в определенные верхние и нижние колонтитулы, используйте метод MoveToHeaderFooter класса DocumentBuilder. В зависимости от ваших требований вы можете перейти к заголовкам HeaderFirst, HeaderEven и HeaderPrimary или к нижним колонтитулам FooterFirst, FooterEven и FooterPrimary.

#### Вопрос: Могу ли я создавать верхние и нижние колонтитулы для определенного раздела документа?

О: Да, вы можете использовать метод MoveToSection класса DocumentBuilder, чтобы перейти к определенному разделу документа, а затем создать верхние и нижние колонтитулы внутри этого раздела.

#### Вопрос: Как сохранить измененный документ в файл с помощью Aspose.Words for .NET?

О: Вы можете сохранить измененный документ в нужном месте и формате, используя метод Save класса Document. Обязательно укажите соответствующий путь к файлу и формат файла (например, DOCX).
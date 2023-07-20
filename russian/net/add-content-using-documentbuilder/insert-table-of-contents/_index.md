---
title: Вставить оглавление в документ Word
linktitle: Вставить оглавление в документ Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить оглавление в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/insert-table-of-contents/
---
В этом всеобъемлющем руководстве вы узнаете, как вставить оглавление в документ Word с помощью Aspose.Words для .NET. Мы проведем вас через весь процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете создать оглавление с соответствующими заголовками и номерами страниц.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1: Создайте новый документ и DocumentBuilder
Для начала создайте новый документ с помощью класса Document и инициализируйте объект DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Вставьте оглавление
Затем используйте метод InsertTableOfContents класса DocumentBuilder, чтобы вставить оглавление. Укажите необходимые параметры форматирования в методе:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Шаг 3: Добавьте содержимое документа
После вставки оглавления добавьте фактическое содержимое документа. Установите соответствующие стили заголовков с помощью StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Шаг 4. Обновите оглавление
Вновь вставленное оглавление изначально будет пустым. Для его заполнения обновите поля в документе:

```csharp
doc.UpdateFields();
```

## Шаг 5: Сохраните документ
После вставки оглавления и обновления полей сохраните документ в файл с помощью метода Save класса Document:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Пример исходного кода для вставки оглавления с использованием Aspose.Words для .NET
Вот полный исходный код для вставки оглавления с помощью Aspose.Words для .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Инициализировать DocumentBuilder с объектом Document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставить оглавлениеa
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Начните фактическое содержание документа на второй странице.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// Вновь вставленное оглавление изначально будет пустым.
// Его необходимо заполнить, обновив поля в документе.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## Заключение

Поздравляем! Вы успешно научились вставлять оглавление в документ Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и используя предоставленный исходный код, теперь вы можете создать оглавление с соответствующими заголовками и номерами страниц для своих документов.

### Часто задаваемые вопросы по вставке оглавления в документ Word

#### В: Могу ли я настроить внешний вид оглавления?

 О: Да, вы можете настроить внешний вид оглавления, изменив параметры форматирования, указанные в`InsertTableOfContents` метод. Параметры позволяют управлять номерами страниц, отступами и другими стилями.

#### В: Что делать, если я хочу включить определенные уровни заголовков в оглавление?

 О: Вы можете указать желаемые уровни заголовков для включения в оглавление, изменив значение в`InsertTableOfContents` метод. Например, используя`"\\o \"1-3\""` будет включать уровни заголовков с 1 по 3.

#### В: Могу ли я автоматически обновлять оглавление, если я вношу изменения в содержание документа?

 О: Да, вы можете автоматически обновить оглавление, вызвав`UpdateFields` метод в документе. Это гарантирует, что любые изменения, внесенные в содержимое документа, такие как добавление или удаление заголовков, будут отражены в оглавлении.

#### В: Как изменить стиль уровней заголовков в оглавлении?

 О: Вы можете стилизовать уровни заголовков по-разному, используя разные стили абзаца для каждого уровня заголовков. При назначении различных`StyleIdentifier` значения для`ParagraphFormat` принадлежащий`DocumentBuilder`, вы можете создавать отдельные стили для каждого уровня заголовка.

#### В: Можно ли добавить дополнительное форматирование к заголовкам в оглавлении?

 О: Да, вы можете добавить к заголовкам в оглавлении дополнительное форматирование, например стили шрифта, цвета или другие свойства. Регулируя`Font` свойства`DocumentBuilder`, вы можете применить пользовательское форматирование к заголовкам.
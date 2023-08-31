---
title: Вставить оглавление в документ Word
linktitle: Вставить оглавление в документ Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить оглавление в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/insert-table-of-contents/
---
В этом подробном руководстве вы узнаете, как вставить оглавление в документ Word с помощью Aspose.Words для .NET. Мы проведем вас через этот процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете создать оглавление с соответствующими заголовками и номерами страниц.

## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- Библиотека Aspose.Words for .NET, установленная в вашей системе.

## Шаг 1. Создайте новый документ и DocumentBuilder
Для начала создайте новый документ, используя класс Document, и инициализируйте объект DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Вставьте оглавление
Затем используйте метод InsertTableOfContents класса DocumentBuilder, чтобы вставить оглавление. Укажите необходимые параметры форматирования внутри метода:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Шаг 3. Добавьте содержимое документа
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
Вновь вставленное оглавление изначально будет пустым. Чтобы заполнить его, обновите поля в документе:

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

// Инициализируйте DocumentBuilder с помощью объекта Document
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

Поздравляем! Вы успешно научились вставлять оглавление в документ Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и используя предоставленный исходный код, вы теперь можете создать оглавление с соответствующими заголовками и номерами страниц для ваших документов.

### Часто задаваемые вопросы по вставке оглавления в документ Word

#### Вопрос: Могу ли я настроить внешний вид оглавления?

 О: Да, вы можете настроить внешний вид оглавления, изменив параметры форматирования, указанные в`InsertTableOfContents` метод. Параметры позволяют управлять номерами страниц, отступами и другими стилями.

#### Вопрос: Что делать, если я хочу включить в оглавление определенные уровни заголовков?

 О: Вы можете указать желаемые уровни заголовков, которые будут включены в оглавление, изменив значение в`InsertTableOfContents` метод. Например, используя`"\\o \"1-3\""` будет включать заголовки уровней с 1 по 3.

#### Вопрос: Могу ли я автоматически обновлять оглавление, если вношу изменения в содержимое документа?

 О: Да, вы можете обновить оглавление автоматически, вызвав`UpdateFields` метод в документе. Это гарантирует, что любые изменения, внесенные в содержимое документа, например добавление или удаление заголовков, будут отражены в оглавлении.

#### Вопрос: Как можно по-другому оформить уровни заголовков в оглавлении?

 О. Уровни заголовков можно стилизовать по-разному, используя разные стили абзацев для каждого уровня заголовков. Назначая разные`StyleIdentifier` ценности для`ParagraphFormat` принадлежащий`DocumentBuilder`, вы можете создавать отдельные стили для каждого уровня заголовков.

#### Вопрос: Можно ли добавить дополнительное форматирование к заголовкам в оглавлении?

 О: Да, вы можете добавить к заголовкам в оглавлении дополнительное форматирование, например стили шрифта, цвета или другие свойства. Регулируя`Font` свойства`DocumentBuilder`, вы можете применить к заголовкам собственное форматирование.
---
title: Добавить комментарии
linktitle: Добавить комментарии
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавлять комментарии к документам Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-comments/add-comments/
---

В этом подробном руководстве вы узнаете, как добавлять комментарии к документу Word с помощью Aspose.Words для .NET. Мы проведем вас через этот процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете вставлять комментарии и настраивать их содержимое в своих документах.

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

## Шаг 2. Добавьте контент в документ
Затем добавьте в документ желаемое содержимое с помощью объекта DocumentBuilder. В этом примере мы добавляем текст:

```csharp
builder.Write("Some text is added.");
```

## Шаг 3. Создайте комментарий и добавьте содержимое
Чтобы добавить комментарий, создайте экземпляр класса Comment, передав объект Document, имя автора, инициалы автора и текущую дату:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Затем добавьте комментарий к текущему абзацу:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Добавьте в комментарий содержимое, например абзац и текст:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Шаг 4. Сохраните документ
После добавления комментария и его содержимого сохраните документ в файл с помощью метода Save класса Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Пример исходного кода для добавления комментариев с использованием Aspose.Words для .NET
Вот полный исходный код для добавления комментариев с помощью Aspose.Words для .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Заключение
Поздравляем! Вы успешно научились добавлять комментарии к документу Word с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, вы теперь можете вставлять комментарии и настраивать их содержимое в своих документах.

Комментарии полезны для совместной работы, предоставления дополнительной информации или создания примечаний в документе. Поэкспериментируйте с разными именами авторов, инициалами и содержанием комментариев в соответствии с вашими конкретными требованиями.

### Часто задаваемые вопросы

#### Вопрос: Как добавить комментарий в документ Aspose.Words for .NET?

О: Чтобы добавить комментарий в документ Aspose.Words for .NET, вам необходимо выполнить шаги, упомянутые в руководстве.

#### Вопрос: Могу ли я форматировать текст комментариев в Aspose.Words для .NET?

О: Да, вы можете форматировать текст комментариев в Aspose.Words for .NET, используя доступные свойства форматирования.

#### Вопрос: Как получить все комментарии, имеющиеся в документе?

 О: Вы можете получить все комментарии, присутствующие в документе, с помощью`Document.Comments` свойство.

#### Вопрос: Могу ли я удалить конкретный комментарий в Aspose.Words for .NET?

 О: Да, вы можете удалить конкретный комментарий в Aspose.Words for .NET, используя команду`Comment.Remove` метод.

#### Вопрос: Как изменить текст существующего комментария в Aspose.Words для .NET?

 О: Чтобы изменить текст существующего комментария в Aspose.Words for .NET, вы можете получить доступ к`Comment.Text` собственность соответствующего`Comment` объект и измените текст по мере необходимости.
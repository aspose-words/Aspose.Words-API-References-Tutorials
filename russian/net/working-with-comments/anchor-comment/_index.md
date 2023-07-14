---
title: Якорный комментарий
linktitle: Якорный комментарий
second_title: API обработки документов Aspose.Words
description: Узнайте, как привязывать ответы на комментарии к определенному тексту в документах Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-comments/anchor-comment/
---

В этом всеобъемлющем руководстве вы узнаете, как привязывать ответы на комментарии к определенному тексту в документе Word с помощью Aspose.Words для .NET. Мы проведем вас через весь процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете связать комментарии с определенным текстом в ваших документах.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1: Создайте новый документ и добавьте текст
Для начала создайте новый документ с помощью класса Document и добавьте нужный текст:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## Шаг 2: Создайте комментарий и добавьте диапазон комментариев
Затем создайте комментарий и свяжите его с определенным текстом, используя объекты CommentRangeStart и CommentRangeEnd:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## Шаг 3: Сохраните документ
После привязки комментария к конкретному тексту сохраните документ в файл с помощью метода Save класса Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Пример исходного кода для ответа на якорный комментарий с использованием Aspose.Words для .NET
Вот полный исходный код для привязки ответа на комментарий с помощью Aspose.Words для .NET:

```csharp
// Создайте экземпляр документа.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Создайте три объекта Run.
// Первые два запускают некоторый текст, а третий запускает комментарий.

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// Каждый из объектов Run имеет связанный с ним объект CommentRangeStart и CommentRangeEnd.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### Часто задаваемые вопросы

#### В: Что такое якорь комментария в Aspose.Words для .NET?

О: В Aspose.Words для .NET якорь комментария — это маркер, который связывает комментарий с определенным местом в документе.

#### Вопрос. Как добавить якорь комментария в документ Aspose.Words for .NET?

О: Чтобы добавить якорь комментария в документ Aspose.Words для .NET, выполните шаги, описанные в руководстве.

#### Вопрос. Как получить доступ к существующей привязке комментариев в Aspose.Words для .NET?

 О: Вы можете получить доступ к существующей привязке комментария в Aspose.Words для .NET с помощью`Comment.Anchor` свойство.

#### В: Могу ли я заменить привязку комментария в Aspose.Words для .NET?

 О: Да, вы можете удалить якорь комментария в Aspose.Words для .NET с помощью`Comment.Remove` метод.

#### В: Как я могу редактировать текст комментария, связанного с якорем комментария в Aspose.Words для .NET?

 О: Чтобы изменить текст комментария, привязанного к якорю комментария в Aspose.Words для .NET, вы можете получить доступ к`Comment.Text` имущество соответствующего`Comment` объекта и изменить текст по мере необходимости.


---
title: Добавить Удалить Комментарий Ответить
linktitle: Добавить Удалить Комментарий Ответить
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как добавлять и удалять ответы на комментарии в документах Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-comments/add-remove-comment-reply/
---

В этом всеобъемлющем руководстве вы узнаете, как добавлять и удалять ответы на комментарии в документе Word с помощью Aspose.Words для .NET. Мы проведем вас через весь процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете управлять ответами на комментарии и настраивать их в соответствии со своими требованиями.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1: Загрузите документ
Для начала загрузите документ, содержащий комментарии, с помощью класса Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## Шаг 2: доступ к комментарию и управление ответами
Затем получите доступ к комментарию из документа с помощью метода GetChild с параметром NodeType.Comment:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

Чтобы удалить ответ из комментария, используйте метод RemoveReply и укажите нужный индекс ответа:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

Чтобы добавить новый ответ на комментарий, используйте метод AddReply и укажите имя автора, инициалы автора, дату и время, а также текст ответа:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## Шаг 3: Сохраните документ
После добавления или удаления ответов на комментарии сохраните документ в файл с помощью метода Save класса Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Пример исходного кода для добавления и удаления ответов на комментарии с использованием Aspose.Words для .NET
Вот полный исходный код для добавления и удаления ответов на комментарии с помощью Aspose.Words для .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Заключение
Поздравляем! Вы успешно научились добавлять и удалять ответы на комментарии в документе Word с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, теперь вы можете управлять ответами на комментарии и настраивать их в соответствии со своими требованиями.

Ответы на комментарии позволяют проводить совместные обсуждения и отзывы в документе. Поэкспериментируйте с разными авторами ответов, инициалами, датами и текстами, чтобы улучшить совместную работу и общение в ваших документах.
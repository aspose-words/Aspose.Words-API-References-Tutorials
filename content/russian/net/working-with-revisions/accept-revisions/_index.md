---
title: Принять изменения
linktitle: Принять изменения
second_title: API обработки документов Aspose.Words
description: Узнайте, как принять изменения в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/accept-revisions/
---

В этом руководстве мы покажем вам, как принять изменения к документу Word с помощью функции «Принять изменения» в Aspose.Words для .NET. Выполните следующие действия, чтобы понять исходный код и принять изменения в документе.

## Шаг 1. Добавление и редактирование содержимого документа

В этом примере мы создаем документ и добавляем контент. Мы используем несколько абзацев для иллюстрации изменений и исправлений. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//Добавьте текст в первый абзац, затем добавьте еще два абзаца.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Шаг 2. Отслеживайте отзывы и добавляйте отзывы

Включаем отслеживание ревизий и добавляем ревизию в документ. Вот как:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Этот абзац является редакцией, и ему будет установлен соответствующий флаг IsInsertRevision.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Шаг 3. Удаление абзаца и управление изменениями

Удаляем абзац и проверяем наличие сохраненных редакций. Вот как:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Поскольку мы отслеживаем изменения, этот абзац все еще существует в документе, и для него будет установлен флаг IsDeleteRevision.
// и будет отображаться как отзыв в Microsoft Word, пока мы не примем или не отклоним все отзывы.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Шаг 4. Примите изменения

Мы принимаем все изменения в документе. Вот как:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Шаг 5. Прекратите отслеживать отзывы

Мы собираемся прекратить отслеживание изменений, чтобы изменения в документе больше не отображались как исправления. Вот как:

```csharp
doc.StopTrackRevisions();
```
## Шаг 6: Сохранение документа

 После вставки поля формы ввода текста сохраните документ в нужное место с помощью кнопки`Save` метод. Обязательно укажите правильный путь к файлу:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Пример исходного кода для принятия изменений с использованием Aspose.Words для .NET

Вот полный исходный код для принятия изменений в документе с помощью Aspose.Words для .NET:


```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//Добавьте текст в первый абзац, затем добавьте еще два абзаца.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

// У нас есть три абзаца, ни один из которых не зарегистрирован как какой-либо пересмотр.
// Если мы добавляем/удаляем какой-либо контент в документе во время отслеживания изменений,
// они будут отображаться в документе как таковые и могут быть приняты/отклонены.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Этот абзац является версией, и для него будет установлен соответствующий флаг IsInsertRevision.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Получите коллекцию абзацев документа и удалите абзац.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Поскольку мы отслеживаем изменения, этот абзац все еще существует в документе и будет иметь установленный параметр IsDeleteRevision.
// и будет отображаться как версия в Microsoft Word, пока мы не примем или не отклоним все версии.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Параграф «Удалить редакцию» будет удален, как только мы примем изменения.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Если остановить отслеживание изменений, этот текст будет отображаться как обычный текст.
//Редакции не учитываются при изменении документа.
doc.StopTrackRevisions();

// Сохраните документ.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Заключение

В этом уроке мы узнали, как принимать изменения в документе Word, используя функцию «Принять изменения» в Aspose.Words для .NET. Мы выполнили действия по добавлению и редактированию содержимого документа, отслеживанию изменений, удалению исправленного абзаца, принятию всех изменений и прекращению отслеживания изменений. Теперь вы можете применить эти знания для эффективного управления изменениями в ваших собственных документах Word с помощью Aspose.Words для .NET.

### Часто задаваемые вопросы

#### Вопрос: Как включить отслеживание версий в Aspose.Words для .NET?

#### Решение 1:

 О: Чтобы включить отслеживание версий в Aspose.Words for .NET, используйте`StartTrackRevisions` метод`Document` объект и укажите имя автора и дату начала отслеживания изменений.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Решение 2:

 О: Вы также можете включить отслеживание изменений с помощью`Document` конструктор, который принимает`trackRevisions` и`author` параметры.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### Вопрос: Как принять все изменения в документе с помощью Aspose.Words for .NET?

 А: Используйте`AcceptAllRevisions` метод`Document` возразить, чтобы принять все изменения, внесенные в документ.

```csharp
doc.AcceptAllRevisions();
```

#### Вопрос: Как сохранить измененный документ с принятыми исправлениями?

 Использовать`Save` метод`Document` объект для сохранения измененного документа с принятыми редакциями. Обязательно укажите правильный путь к файлу.

```csharp
doc.Save("path/to/the/document.docx");
```

#### Вопрос: Как мне прекратить отслеживание изменений в Aspose.Words for .NET?

 А: Используйте`StopTrackRevisions` метод`Document` объект, чтобы остановить отслеживание изменений.

```csharp
doc.StopTrackRevisions();
```

#### Вопрос: Как удалить исправленный абзац в документе с помощью Aspose.Words for .NET?

 О: Чтобы удалить исправленный абзац в документе, вы можете использовать команду`Remove` метод сбора абзацев.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```
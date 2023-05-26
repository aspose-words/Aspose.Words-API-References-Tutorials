---
title: Принять изменения
linktitle: Принять изменения
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как принимать изменения в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/accept-revisions/
---

В этом руководстве мы покажем вам, как принимать изменения в документе Word с помощью функции «Принять изменения» в Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и принять изменения в документе.

## Шаг 1. Добавление и редактирование содержимого документа

В этом примере мы создаем документ и добавляем содержимое. Мы используем несколько абзацев для иллюстрации изменений и поправок. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Добавьте текст в первый абзац, затем добавьте еще два абзаца.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Шаг 2. Отслеживайте отзывы и добавляйте отзывы

Включаем отслеживание ревизий и добавляем ревизию в документ. Вот как:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

//Этот абзац является редакцией и будет иметь соответствующий установленный флаг «IsInsertRevision».
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Шаг 3. Удалите абзац и управляйте изменениями

Удаляем абзац и проверяем наличие сохраненных правок. Вот как:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Поскольку мы отслеживаем изменения, абзац все еще существует в документе, для него будет установлен флаг «IsDeleteRevision».
// и будет отображаться как отзыв в Microsoft Word, пока мы не примем или не отклоним все отзывы.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Шаг 4: Примите изменения

Мы принимаем все изменения в документе. Вот как:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Шаг 5. Прекратите отслеживать отзывы

Мы перестанем отслеживать версии, чтобы изменения в документе больше не отображались как версии. Вот как:

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

	// Добавьте текст в первый абзац, затем добавьте еще два абзаца.
	para.AppendChild(new Run(doc, "Paragraph 1. "));
	body.AppendParagraph("Paragraph 2. ");
	body.AppendParagraph("Paragraph 3. ");

	// У нас есть три абзаца, ни один из которых не зарегистрирован как редакция любого типа.
	//Если мы добавим/удалим какой-либо контент в документе во время отслеживания изменений,
	// они будут отображаться как таковые в документе и могут быть приняты/отклонены.
	doc.StartTrackRevisions("John Doe", DateTime.Now);

	// Этот абзац является редакцией и будет иметь соответствующий установленный флаг «IsInsertRevision».
	para = body.AppendParagraph("Paragraph 4. ");
	Assert.True(para.IsInsertRevision);

	// Получите коллекцию абзацев документа и удалите абзац.
	ParagraphCollection paragraphs = body.Paragraphs;
	Assert.AreEqual(4, paragraphs.Count);
	para = paragraphs[2];
	para.Remove();

	// Поскольку мы отслеживаем изменения, абзац все еще существует в документе, для него будет установлен параметр «IsDeleteRevision».
	// и будет отображаться как редакция в Microsoft Word, пока мы не примем или не отклоним все редакции.
	Assert.AreEqual(4, paragraphs.Count);
	Assert.True(para.IsDeleteRevision);

	// Параграф удаления редакции удаляется, как только мы принимаем изменения.
	doc.AcceptAllRevisions();
	Assert.AreEqual(3, paragraphs.Count);
	Assert.That(para, Is.Empty);

	// Если остановить отслеживание изменений, этот текст будет отображаться как обычный текст.
	// Редакции не учитываются при изменении документа.
	doc.StopTrackRevisions();

	// Сохраните документ.
	doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
            
```

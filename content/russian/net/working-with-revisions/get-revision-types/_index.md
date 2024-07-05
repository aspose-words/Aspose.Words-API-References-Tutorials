---
title: Получить типы редакций слов
linktitle: Получить типы редакций слов
second_title: API обработки документов Aspose.Words
description: Получите типы редакций слов в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/get-revision-types/
---

В этом пошаговом руководстве мы расскажем вам, как получить типы редакций слов в документе Word с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1: Загрузка документа

Первым шагом является загрузка документа, содержащего изменения.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Шаг 2. Пройдитесь по абзацам.

Далее мы пройдемся по абзацам документа и проверим типы изменений слов, связанные с каждым абзацем.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Пример исходного кода для получения типов ревизий с использованием Aspose.Words для .NET

Вот полный исходный код для получения типов изменений в документе с помощью Aspose.Words для .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## Заключение

В этом уроке мы узнали, как получить типы редакций слов в документе Word с помощью Aspose.Words для .NET. Мы выполнили шаги, чтобы загрузить документ, просмотреть абзацы и проверить типы словесных обзоров, связанных с каждым абзацем. Теперь вы можете применить эти знания для анализа обзоров слов в своих собственных документах Word, используя Aspose.Words для .NET.

### Часто задаваемые вопросы по типам слов для получения редакций

#### Вопрос: Как загрузить документ в Aspose.Words для .NET?

 А: Используйте`Document` класс Aspose.Words для .NET для загрузки документа из файла. Вы можете указать полный путь к документу.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Вопрос: Как перебирать абзацы в документе в Aspose.Words for .NET?

 А: Используйте`Paragraphs` свойство раздела документа для получения коллекции абзацев. Затем вы можете использовать цикл для просмотра каждого абзаца.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Обработайте каждый абзац здесь
}
```

#### Вопрос: Как проверить, был ли абзац перемещен (удален) в Aspose.Words for .NET?

 A: Используйте абзацы`IsMoveFromRevision`свойство, чтобы проверить, было ли оно перемещено (удалено).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // Абзац перенесен (удален)
}
```

#### Вопрос: Как проверить, был ли абзац перемещен (вставлен) в Aspose.Words for .NET?

 A: Используйте абзацы`IsMoveToRevision` свойство, чтобы проверить, было ли оно перемещено (вставлено).

```csharp
if (paragraph.IsMoveToRevision)
{
     // Абзац перенесен (вставлен)
}
```
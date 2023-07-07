---
title: Получить типы ревизий слов
linktitle: Получить типы ревизий слов
second_title: Справочник по API Aspose.Words для .NET
description: Получите типы редакций слов в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/get-revision-types/
---

В этом пошаговом руководстве мы расскажем вам, как получить типы редакций слов в документе Word с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1: Загрузка документа

Первым шагом является загрузка документа, содержащего исправления.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Шаг 2. Пройдитесь по абзацам

Далее мы пройдемся по абзацам документа и проверим типы исправлений слов, связанных с каждым абзацем.

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

### Пример исходного кода для получения типов изменений с использованием Aspose.Words для .NET

Вот полный исходный код для получения типов ревизий в документе с помощью Aspose.Words для .NET:

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

В этом руководстве мы узнали, как получить типы редакций слов в документе Word с помощью Aspose.Words для .NET. Мы выполнили шаги, чтобы загрузить документ, просмотреть абзацы и проверить типы обзоров слов, связанные с каждым абзацем. Теперь вы можете применить эти знания для анализа рецензий слов в ваших собственных документах Word с помощью Aspose.Words для .NET.

### Часто задаваемые вопросы для получения типов ревизии слов

#### В: Как загрузить документ в Aspose.Words для .NET?

 О: Используйте`Document` класс Aspose.Words для .NET для загрузки документа из файла. Вы можете указать полный путь к документу.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### В: Как перебирать абзацы в документе в Aspose.Words для .NET?

 О: Используйте`Paragraphs` свойство раздела документа, чтобы получить коллекцию абзацев. Затем вы можете использовать цикл для просмотра каждого абзаца.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Обработайте каждый абзац здесь
}
```

#### В: Как проверить, был ли перемещен (удален) абзац в Aspose.Words для .NET?

 A: Используйте абзац`IsMoveFromRevision` свойство, чтобы проверить, было ли оно перемещено (удалено).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // Абзац перемещен (удален)
}
```

#### В: Как проверить, был ли перемещен (вставлен) абзац в Aspose.Words для .NET?

 A: Используйте абзац`IsMoveToRevision`свойство, чтобы проверить, было ли оно перемещено (вставлено).

```csharp
if (paragraph.IsMoveToRevision)
{
     // Абзац перемещен (вставлен)
}
```
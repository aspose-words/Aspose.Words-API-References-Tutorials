---
title: Получить типы изменений
linktitle: Получить типы изменений
second_title: Справочник по API Aspose.Words для .NET
description: Получите типы изменений в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/get-revision-types/
---

В этом пошаговом руководстве мы расскажем вам, как получить типы редакций в документе Word с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1: Загрузка документа

Первым шагом является загрузка документа, содержащего исправления.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Шаг 2. Пройдитесь по абзацам

Далее мы пройдемся по абзацам документа и проверим типы изменений, связанных с каждым абзацем.

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

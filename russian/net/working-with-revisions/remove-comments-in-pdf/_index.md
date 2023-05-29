---
title: Удалить комментарии в PDF
linktitle: Удалить комментарии в PDF
second_title: Справочник по API Aspose.Words для .NET
description: Удалите комментарии в файле PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/remove-comments-in-pdf/
---

В этом пошаговом руководстве мы расскажем вам, как удалить комментарии в файле PDF с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1: Загрузка документа

Первым шагом является загрузка документа, содержащего комментарии.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Шаг 2. Скройте комментарии в PDF

Мы настроим параметр макета, чтобы скрыть комментарии при создании PDF-файла.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Шаг 3. Сохраните документ в формате PDF.

Наконец, мы сохраним документ в формате PDF, удалив комментарии.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Выходные форматы уценки

Вывод может быть отформатирован в уценке для улучшения читаемости. Например :

```markdown
- Comments are hidden in the generated PDF.
```

### Пример исходного кода для удаления комментариев в Pdf с использованием Aspose.Words для .NET

Вот полный исходный код для удаления комментариев в файле PDF с помощью Aspose.Words для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Скрыть комментарии в PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```
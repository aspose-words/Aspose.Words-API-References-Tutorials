---
title: Удалить комментарии в PDF-файле
linktitle: Удалить комментарии в PDF-файле
second_title: API обработки документов Aspose.Words
description: Удалите комментарии в PDF-файле с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/remove-comments-in-pdf/
---

В этом пошаговом руководстве мы расскажем вам, как удалить комментарии в файле PDF с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1: Загрузка документа

Первый шаг — загрузить документ, содержащий комментарии.

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

## Форматы вывода Markdown

Вывод может быть отформатирован в уценке для улучшения читаемости. Например :

```markdown
- Comments are hidden in the generated PDF.
```

### Пример исходного кода для удаления комментариев в PDF с использованием Aspose.Words для .NET

Вот полный исходный код для удаления комментариев в PDF-файле с помощью Aspose.Words для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Скрыть комментарии в PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Заключение

В этом уроке мы узнали, как удалить комментарии из PDF-файла с помощью Aspose.Words для .NET. Используя соответствующие параметры макета, мы смогли скрыть комментарии при создании PDF-файла. Aspose.Words for .NET предлагает большую гибкость для управления файлами Word и их преобразования в различные форматы, включая PDF. Теперь вы можете применить эти знания для удаления комментариев в своих PDF-файлах с помощью Aspose.Words для .NET.

### Часто задаваемые вопросы по удалению комментариев в файле PDF

#### Вопрос: Как загрузить документ в Aspose.Words для .NET?

 А: Используйте`Document` класс Aspose.Words для .NET для загрузки документа из файла. Вы можете указать полный путь к документу.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Вопрос: Как скрыть комментарии в PDF-файле, созданном с помощью Aspose.Words for .NET?

 А: Используйте`CommentDisplayMode` собственность`LayoutOptions` объект для настройки отображения комментариев при создании PDF-файла. Чтобы скрыть комментарии, установите для этого свойства значение`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### Вопрос: Как сохранить документ в формате PDF с помощью Aspose.Words для .NET?

 А: Используйте`Save` метод`Document` объект для сохранения документа в формате PDF. Укажите полный путь к файлу PDF.

```csharp
doc.Save("path/to/the/file.pdf");
```
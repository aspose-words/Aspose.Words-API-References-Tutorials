---
title: Удалить комментарии в файле PDF
linktitle: Удалить комментарии в файле PDF
second_title: API обработки документов Aspose.Words
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

## Заключение

В этом уроке мы узнали, как удалить комментарии из файла PDF с помощью Aspose.Words для .NET. Используя соответствующие параметры макета, мы смогли скрыть комментарии при создании PDF-файла. Aspose.Words для .NET предлагает большую гибкость для управления файлами Word и преобразования их в различные форматы, включая PDF. Теперь вы можете применить эти знания для удаления комментариев в ваших собственных PDF-файлах с помощью Aspose.Words для .NET.

### Часто задаваемые вопросы по удалению комментариев в файле PDF

#### В: Как загрузить документ в Aspose.Words для .NET?

 О: Используйте`Document` класс Aspose.Words для .NET для загрузки документа из файла. Вы можете указать полный путь к документу.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### В: Как скрыть комментарии в PDF, сгенерированном с помощью Aspose.Words для .NET?

 О: Используйте`CommentDisplayMode` собственность`LayoutOptions` объект для настройки отображения комментариев при создании PDF-файла. Чтобы скрыть комментарии, установите для этого свойства значение`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### В: Как сохранить документ в формате PDF с помощью Aspose.Words для .NET?

 О: Используйте`Save` метод`Document` объекта для сохранения документа в формате PDF. Укажите полный путь к файлу PDF.

```csharp
doc.Save("path/to/the/file.pdf");
```
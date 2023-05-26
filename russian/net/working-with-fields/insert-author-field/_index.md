---
title: Вставить поле автора
linktitle: Вставить поле автора
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставить поле AUTHOR в документы Word с помощью Aspose.Words для .NET. Укажите имя автора, чтобы персонализировать ваши документы.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-author-field/
---


Вот пошаговое руководство, объясняющее приведенный ниже исходный код C#, в котором используется функция «Вставить поле AUTHOR» Aspose.Words для .NET. Обязательно внимательно следуйте каждому шагу, чтобы получить желаемые результаты.

## Шаг 1: Настройка каталога документов

В предоставленном коде необходимо указать директорию ваших документов. Замените значение «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа и абзаца

Начнем с создания нового документа и извлечения первого абзаца.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Шаг 3: Вставьте поле AUTHOR

 Мы используем`AppendField()` способ вставки поля AUTHOR в абзац.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Затем мы настраиваем поле`AuthorName` свойство для указания имени автора.

```csharp
field. AuthorName = "Test1";
```

 Наконец, мы вызываем`Update()` способ обновления поля.

```csharp
field. Update();
```

### Пример исходного кода для вставки поля AUTHOR с Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создание документа.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Вставьте поле АВТОР.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

В этом примере мы создали новый документ, вставили поле AUTHOR, настроили имя автора и сохранили документ с указанным именем файла.

На этом мы завершаем наше руководство по использованию функции «Вставить поле AUTHOR» с Aspose.Words для .NET.

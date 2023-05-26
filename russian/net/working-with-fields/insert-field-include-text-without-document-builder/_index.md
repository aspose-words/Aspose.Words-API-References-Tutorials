---
title: Вставить FieldIncludeText без построителя документов
linktitle: Вставить FieldIncludeText без построителя документов
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставить поле FieldIncludeText в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Ниже приведено пошаговое руководство для объяснения приведенного ниже исходного кода C#, в котором используется функция «Вставить поле FieldIncludeText» Aspose.Words для .NET. Обязательно внимательно следуйте каждому шагу, чтобы получить желаемые результаты.

## Шаг 1: Настройка каталога документов

В предоставленном коде необходимо указать директорию ваших документов. Замените значение «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа и абзаца

Начнем с создания нового документа и инициализации абзаца.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Шаг 3: Вставка поля FieldIncludeText

 Мы используем`AppendField()` метод для вставки поля FieldIncludeText в абзац.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Затем мы настраиваем свойства поля FieldIncludeText, указав имя закладки и имя исходного файла.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Затем мы добавляем абзац в тело документа.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Наконец, мы вызываем`Update()` способ обновления поля.

```csharp
fieldIncludeText.Update();
```

### Пример исходного кода для вставки поля FieldIncludeText с помощью Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте документ и абзац.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Вставьте поле FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

В этом примере мы создали новый документ, инициализировали абзац, вставили FieldIncludeTexten, указав имя закладки и имя исходного файла, и сохранили документ с указанным именем файла.

На этом мы завершаем наше руководство по использованию функции «Вставить текст поля» с Aspose.Words для .NET.
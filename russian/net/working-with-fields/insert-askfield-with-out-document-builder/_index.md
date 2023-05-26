---
title: Вставить ASKField без Document Builder
linktitle: Вставить ASKField без Document Builder
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставить поле ASK в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, в котором используется функция «Вставить поле ASK без DocumentBuilder» в Aspose.Words для .NET. Обязательно внимательно следуйте каждому шагу, чтобы получить желаемые результаты.

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

## Шаг 3: Вставка поля ASK

 Мы используем`AppendField()` способ вставки поля ASK в абзац.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Затем мы настраиваем различные свойства поля ASK, указав нужные значения.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Наконец, мы вызываем`Update()` способ обновления поля.

```csharp
field. Update();
```

### Пример исходного кода для вставки поля ASK без DocumentBuilder с Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создание документа.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Вставьте поле ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

В этом примере мы создали новый документ, вставили поле ASK без использования DocumentBuilder, настроили различные свойства поля и сохранили документ с указанным именем файла.

На этом мы завершаем наше руководство по использованию функции «Вставить поле ASK без DocumentBuilder» с Aspose.Words для .NET.
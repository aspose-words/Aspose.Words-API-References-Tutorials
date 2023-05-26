---
title: Вставьте поле слияния с помощью DOM
linktitle: Вставьте поле слияния с помощью DOM
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставлять поля слияния настраиваемых полей в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-merge-field-using-dom/
---

Вот пошаговое руководство, объясняющее приведенный ниже исходный код C#, в котором используется функция «Вставить поле слияния» в Aspose.Words для .NET. Обязательно внимательно следуйте каждому шагу, чтобы получить желаемые результаты.

## Шаг 1: Настройка каталога документов

В предоставленном коде необходимо указать директорию ваших документов. Замените значение «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа и DocumentBuilder

Начнем с создания нового документа и инициализации DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3: Перемещение курсора к абзацу

 Мы используем`MoveTo()` метод DocumentBuilder, чтобы переместить курсор в абзац, куда мы хотим вставить поле слияния полей.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Шаг 4: Вставка поля слияния полей

 Мы используем DocumentBuilder`InsertField()` метод вставки поля слияния полей в абзац.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Затем мы настраиваем свойства поля слияния полей, указав соответствующие параметры, такие как имя поля, текст до и после поля и параметры вертикального форматирования.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Наконец, мы вызываем`Update()` способ обновления поля.

```csharp
field. Update();
```

### Пример исходного кода для вставки поля слияния полей с помощью Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте документ и DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Подведите курсор к абзацу.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Вставить поле слияния полей.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Обновите поле.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

В этом примере мы создали новый документ, переместили курсор в нужный абзац, а затем вставили в документ поле слияния полей.